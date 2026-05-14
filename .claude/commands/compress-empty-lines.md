# 压缩文档多余空行

压缩 Markdown 文档中连续的多个空行，保留合理的段落间距（单个空行），使文档更紧凑易读。适用于微信读书导出笔记等含有多余空行的文档。

## 参数

- `$ARGUMENTS`：要处理的文件或文件夹路径（Vault 内相对路径）。如未提供，则处理当前笔记。

## 执行步骤

### 1. 确定处理目标

根据用户输入确定处理范围：
- 若 `$ARGUMENTS` 指向单个 `.md` 文件 → 处理该文件
- 若 `$ARGUMENTS` 指向文件夹 → 批量处理该文件夹下所有 `.md` 文件（含子目录）
- 若 `$ARGUMENTS` 为空 → 询问用户要处理哪个文件或文件夹

### 2. 备份原文件

对每个目标文件，先创建 `.backup` 备份：

```bash
cp "文件名.md" "文件名.md.backup"
```

### 3. 执行空行压缩

使用 Perl 脚本压缩连续空行：

**单文件处理：**
```bash
perl -ne 'if (/\S/) { print; $prev_empty = 0 } else { print unless $prev_empty; $prev_empty = 1 }' "文件名.md" > "文件名.new" && mv "文件名.new" "文件名.md"
```

**批量处理（文件夹）：**
```bash
find "目标文件夹" -name "*.md" -type f -exec bash -c '
  for file; do
    echo "处理: $file"
    cp "$file" "$file.backup"
    perl -ne "if (/\S/) { print; \$prev_empty = 0 } else { print unless \$prev_empty; \$prev_empty = 1 }" "$file" > "$file.new" && mv "$file.new" "$file"
  done
' bash {} +
```

### 4. 验证结果

对每个处理后的文件进行验证：
```bash
# 对比处理前后行数
wc -l "文件名.md" "文件名.md.backup"

# 检查文件开头、中段、结尾是否正常
head -20 "文件名.md"
sed -n '50,70p' "文件名.md"
tail -20 "文件名.md"
```

### 5. 汇报结果

向用户报告：
- 处理了哪些文件
- 每个文件处理前后的行数对比
- 移除了多少空行
- 备份文件的位置（`.backup` 后缀）

### 恢复方法（告知用户）

如不满意，可恢复原文件：
```bash
mv "文件名.md.backup" "文件名.md"
```

批量恢复：
```bash
find . -name "*.backup" -exec bash -c 'mv "$0" "${0%.backup}"' {} \;
```

## 注意事项

- **务必先备份**：脚本会自动创建 `.backup` 文件
- **格式保留**：保留段落间单个空行、所有非空白内容、Markdown 标记；仅压缩连续 2 个及以上空行为 1 个
- **中文路径**：使用引号包裹文件名以支持中文路径
- **安全性**：建议先在小文件上测试，确认效果后再批量处理
