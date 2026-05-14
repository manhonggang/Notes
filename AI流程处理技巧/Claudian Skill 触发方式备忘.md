---
title: "Claudian Skill 触发方式备忘"
description: "汇总所有可用 Skill 的触发命令与简要说明，方便快速查阅"
created: 2026-05-14
tags:
  - skill
  - 备忘
  - 自动化
---

# Claudian Skill 触发方式备忘

在 Claude Code 中输入 `/技能名` 即可触发对应 Skill。部分 Skill 支持追加参数。

## 📝 文本处理

| Skill | 触发命令 | 说明 |
|-------|---------|------|
| 压缩空行 | `/compress-empty-lines` | 压缩 Markdown 文档中连续多余空行，保留合理段落间距。可追加文件或文件夹路径，如 `/compress-empty-lines 资料及书影音笔记` |
| 字幕整理 | 详见 [[视频字幕整理优化Skill]] | 移除时间戳、清理填充词、重组结构，优化视频字幕文本（目前为文档记录，尚未注册为斜杠命令） |

## 🔧 Obsidian 工具

| Skill | 触发命令 | 说明 |
|-------|---------|------|
| Markdown 编辑 | `/obsidian-markdown` | 创建和编辑 Obsidian 风格 Markdown，处理 wikilinks、callouts、frontmatter 等 |
| Bases 视图 | `/obsidian-bases` | 创建和编辑 `.base` 文件，构建数据库式笔记视图（表格/卡片/筛选/公式） |
| Canvas 画布 | `/json-canvas` | 创建和编辑 `.canvas` 文件，构建可视化画布、思维导图、流程图 |
| Obsidian CLI | `/obsidian-cli` | 通过命令行与 Obsidian 交互：搜索、创建笔记、管理任务、调试插件等 |

## 📖 笔记处理

| Skill | 触发命令 | 说明 |
|-------|---------|------|
| 笔记深化 | `/note-deepen` | 审计笔记的信息密度，区分洞见与常识，修剪空洞内容，提升结构完整性 |
| 翻译笔记 | `/translate` | 将英文笔记翻译为中文，创建双向 wikilink 关联的新笔记 |

## 🌐 网页与代码

| Skill | 触发命令 | 说明 |
|-------|---------|------|
| 网页提取 | `/defuddle` | 从网页中提取干净的 Markdown 内容，去除杂乱的导航和广告。比 WebFetch 更适合阅读网页文章 |
| 代码简化 | `/simplify` | 审查已修改的代码，检查复用性、质量和效率问题并修复 |
| Claude API | `/claude-api` | 构建、调试和优化使用 Anthropic SDK 的应用，处理模型迁移、缓存等问题 |

## ⚙️ 系统与配置

| Skill | 触发命令 | 说明 |
|-------|---------|------|
| 配置更新 | `/update-config` | 配置 Claude Code 的 settings.json：权限、环境变量、自动化钩子等 |
| 快捷键 | `/keybindings-help` | 自定义键盘快捷键、修改按键绑定 |
| 减少权限弹窗 | `/fewer-permission-prompts` | 扫描历史命令，自动添加常用只读操作的权限白名单 |
| 循环执行 | `/loop` | 以固定间隔重复运行命令，如 `/loop 5m /compress-empty-lines` 每 5 分钟执行一次 |
| 初始化 | `/init` | 为代码库创建 `CLAUDE.md` 文档 |

## 🔍 代码审查

| Skill | 触发命令 | 说明 |
|-------|---------|------|
| PR 审查 | `/review` | 审查 Pull Request |
| 安全审查 | `/security-review` | 对当前分支的待合并变更进行安全审查 |

---

> [!tip] 使用提示
> - 输入 `/` 后会自动弹出 Skill 列表供选择，无需完整输入名称
> - 部分 Skill 支持参数，在命令后空格追加即可，如 `/compress-empty-lines 某个文件夹`
> - 不带参数触发时，Skill 通常会主动询问你需要的具体信息
