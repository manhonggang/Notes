---
title: "视频字幕整理优化Skill"
description: "自动化清理和优化视频字幕文本的流程，移除时间戳、填充词，重组内容结构，显著降低token使用量"
author: "Claudian"
created: 2026-04-25
tags:
  - skill
  - 文本处理
  - 字幕整理
  - token优化
  - 自动化
---

# 视频字幕整理优化Skill

## 概述

这个Skill提供了一套完整的自动化流程，用于整理从视频中剪切出来的字幕文本。通过移除时间戳、清理口语化填充词、重组内容结构，可以显著降低文本的token使用量，同时提升可读性和专业性。

## 适用场景

- GDC等会议演讲字幕整理
- 教学视频字幕处理
- 访谈记录清理
- 播客转录文本优化
- 任何包含时间戳和口语化表达的视频字幕

## 核心功能

### 1. 时间戳移除
自动识别并移除各种格式的时间戳：
- `**0:01** ·` 格式
- `[00:00:01]` 格式  
- `00:01` 格式
- 其他常见时间戳变体

### 2. 填充词清理
移除中文口语中常见的填充词：
- 呃、嗯、啊、哦
- 那个、这个、然后
- 就是、其实、反正
- 好吧、那么、所以

### 3. 文本结构化
将连续的文本流重新组织为：
- 逻辑清晰的段落
- 适当的标题层次
- 技术术语保留
- 核心内容突出

### 4. Token优化
通过以下方式减少token使用：
- 删除冗余信息
- 简化重复表达
- 保持核心含义
- 提升信息密度

## 完整处理流程

### 步骤1：原始文本输入
```python
# 示例输入文本
raw_text = """
**0:01** · [音乐] 下午好，GDC，呃，GDC 2010，好吧，有史以来最好的GDC，嗯，下午好，呃，欢迎来到
**0:17** · "朋友之间"，呃，以及《神秘海域2：纵横四海》开发后记。呃，请将您的移动设备设置为静音...
"""
```

### 步骤2：时间戳移除
```python
import re

def remove_timestamps(text):
    # 移除 **0:01** · 格式
    text = re.sub(r'\*\*[0-9]+:[0-9]+\*\* · ', '', text)
    # 移除 [00:00:01] 格式
    text = re.sub(r'\[[0-9]+:[0-9]+:[0-9]+\] ', '', text)
    # 移除 00:01 格式
    text = re.sub(r'[0-9]+:[0-9]+ ', '', text)
    return text
```

### 步骤3：填充词清理
```python
def remove_filler_words(text):
    filler_words = [
        '呃', '嗯', '啊', '哦',
        '那个', '这个', '然后',
        '就是', '其实', '反正',
        '好吧', '那么', '所以',
        '呃，', '，呃', '嗯，', '，嗯',
        '好吧，', '，好吧', '那么，', '，那么'
    ]
    
    for word in filler_words:
        text = text.replace(word, '')
    
    # 清理多余的标点
    text = re.sub(r'，，', '，', text)
    text = re.sub(r'，。', '。', text)
    text = re.sub(r'。。', '。', text)
    text = re.sub(r'  ', ' ', text)
    
    return text.strip()
```

### 步骤4：文本重组
```python
def reorganize_text(text):
    # 按句子分割
    sentences = text.split('。')
    
    # 重组逻辑段落
    paragraphs = []
    current_para = []
    sentence_count = 0
    
    for sentence in sentences:
        sentence = sentence.strip()
        if not sentence:
            continue
            
        current_para.append(sentence)
        sentence_count += 1
        
        # 每3-5个句子组成一个段落
        if sentence_count >= 4 or len(sentence) > 100:
            paragraphs.append('。'.join(current_para) + '。')
            current_para = []
            sentence_count = 0
    
    # 添加最后的段落
    if current_para:
        paragraphs.append('。'.join(current_para) + '。')
    
    return '\n\n'.join(paragraphs)
```

### 步骤5：标题识别与添加
```python
def add_headings(text):
    # 识别可能的标题（包含关键词的短句）
    heading_keywords = ['概述', '介绍', '目标', '方法', '结果', '结论', 
                       '技术', '设计', '开发', '测试', '优化']
    
    lines = text.split('\n')
    result = []
    
    for line in lines:
        if any(keyword in line for keyword in heading_keywords) and len(line) < 50:
            result.append(f'### {line}')
        else:
            result.append(line)
    
    return '\n'.join(result)
```

### 步骤6：完整处理函数
```python
def process_subtitle(raw_text):
    # 1. 移除时间戳
    text = remove_timestamps(raw_text)
    
    # 2. 清理填充词
    text = remove_filler_words(text)
    
    # 3. 重组文本
    text = reorganize_text(text)
    
    # 4. 添加标题
    text = add_headings(text)
    
    # 5. 最终清理
    text = re.sub(r'\n{3,}', '\n\n', text)  # 移除多余空行
    text = text.strip()
    
    return text
```

## Obsidian集成方案

### 方案1：使用Templater插件
```javascript
// 在Templater中创建模板
<%*
// 获取剪贴板内容
let rawText = await tp.system.clipboard();

// 调用处理函数
function processSubtitle(text) {
    // 这里插入上面的Python处理逻辑的JavaScript版本
    // ...
    return processedText;
}

let processedText = processSubtitle(rawText);

// 创建新笔记
await tp.file.create(processedText);
%>
```

### 方案2：使用QuickAdd插件
1. 安装QuickAdd插件
2. 创建新的宏
3. 添加JavaScript代码处理剪贴板内容
4. 绑定快捷键

### 方案3：Python脚本独立运行
```bash
# 保存为clean_subtitle.py
python clean_subtitle.py input.txt output.md
```

## Token优化策略

### 1. 词汇层面优化
```python
def optimize_vocabulary(text):
    # 替换长表达为简短表达
    replacements = {
        '也就是说': '即',
        '换句话说': '换言之',
        '与此同时': '同时',
        '尽管如此': '但',
        '基于这个原因': '因此'
    }
    
    for long, short in replacements.items():
        text = text.replace(long, short)
    
    return text
```

### 2. 句子层面优化
```python
def optimize_sentences(text):
    # 分割句子
    sentences = re.split(r'[。！？]', text)
    optimized = []
    
    for sentence in sentences:
        sentence = sentence.strip()
        if not sentence:
            continue
        
        # 删除重复信息
        if len(optimized) > 0 and sentence in optimized[-1]:
            continue
        
        # 简化复杂句子
        if len(sentence) > 100:
            # 这里可以添加更复杂的句子简化逻辑
            pass
        
        optimized.append(sentence)
    
    return '。'.join(optimized) + '。'
```

### 3. 段落层面优化
```python
def optimize_paragraphs(text):
    paragraphs = text.split('\n\n')
    optimized = []
    
    for para in paragraphs:
        para = para.strip()
        if not para:
            continue
        
        # 计算信息密度
        sentences = para.split('。')
        if len(sentences) < 2:
            # 单句段落可能不需要
            continue
        
        optimized.append(para)
    
    return '\n\n'.join(optimized)
```

## 效果评估

### Token减少示例
| 处理阶段 | 原始字符数 | 处理后字符数 | 减少比例 |
|---------|-----------|------------|----------|
| 原始文本 | 10,000 | - | - |
| 移除时间戳 | - | 8,500 | 15% |
| 清理填充词 | - | 7,200 | 15% |
| 结构优化 | - | 6,500 | 10% |
| **总计** | **10,000** | **6,500** | **35%** |

### 可读性提升
- 段落结构更清晰
- 技术术语更突出
- 核心信息更易提取
- 适合快速浏览和深度阅读

## 高级功能

### 1. 主题提取
```python
def extract_topics(text, num_topics=5):
    from collections import Counter
    import jieba
    
    # 使用jieba分词
    words = jieba.cut(text)
    
    # 过滤停用词
    stopwords = ['的', '了', '在', '是', '我', '有', '和', '就']
    filtered_words = [w for w in words if w not in stopwords and len(w) > 1]
    
    # 统计词频
    word_freq = Counter(filtered_words)
    
    return word_freq.most_common(num_topics)
```

### 2. 关键句提取
```python
def extract_key_sentences(text, num_sentences=10):
    from sklearn.feature_extraction.text import TfidfVectorizer
    
    sentences = text.split('。')
    if len(sentences) <= num_sentences:
        return sentences
    
    # 计算TF-IDF
    vectorizer = TfidfVectorizer()
    tfidf_matrix = vectorizer.fit_transform(sentences)
    
    # 计算句子重要性
    sentence_scores = tfidf_matrix.sum(axis=1)
    
    # 选择最重要的句子
    important_indices = sentence_scores.argsort()[-num_sentences:][::-1]
    key_sentences = [sentences[i] for i in important_indices]
    
    return key_sentences
```

### 3. 自动摘要生成
```python
def generate_summary(text, ratio=0.3):
    """
    生成文本摘要
    ratio: 摘要长度占原文的比例
    """
    import jieba.analyse
    
    # 提取关键词
    keywords = jieba.analyse.extract_tags(text, topK=20)
    
    # 基于关键词选择句子
    sentences = text.split('。')
    scored_sentences = []
    
    for i, sentence in enumerate(sentences):
        score = sum(1 for keyword in keywords if keyword in sentence)
        scored_sentences.append((score, i, sentence))
    
    # 按分数排序
    scored_sentences.sort(reverse=True)
    
    # 选择前N个句子
    num_selected = max(1, int(len(sentences) * ratio))
    selected = sorted(scored_sentences[:num_selected], key=lambda x: x[1])
    
    return '。'.join([s[2] for s in selected]) + '。'
```

## 使用建议

### 1. 批量处理
```bash
# 处理文件夹中的所有字幕文件
for file in *.txt; do
    python clean_subtitle.py "$file" "${file%.txt}_cleaned.md"
done
```

### 2. 质量控制
- 首次使用时检查处理结果
- 根据需要调整填充词列表
- 保留原始文件备份
- 对重要内容进行人工校对

### 3. 自定义配置
创建配置文件`subtitle_config.json`：
```json
{
  "timestamp_patterns": [
    "\\*\\*[0-9]+:[0-9]+\\*\\* · ",
    "\\[[0-9]+:[0-9]+:[0-9]+\\] ",
    "[0-9]+:[0-9]+ "
  ],
  "filler_words": [
    "呃", "嗯", "啊", "哦",
    "那个", "这个", "然后"
  ],
  "optimization_level": "balanced",
  "output_format": "markdown"
}
```

## 故障排除

### 常见问题
1. **时间戳未完全移除**
   - 检查正则表达式是否匹配所有格式
   - 添加自定义时间戳模式

2. **重要内容被误删**
   - 调整填充词列表
   - 使用白名单保护重要术语

3. **结构混乱**
   - 调整段落分割逻辑
   - 手动添加章节标题

### 调试模式
```python
def process_with_debug(raw_text, debug=False):
    steps = []
    
    # 记录每一步的结果
    steps.append(("原始文本", raw_text))
    
    text1 = remove_timestamps(raw_text)
    steps.append(("移除时间戳后", text1))
    
    text2 = remove_filler_words(text1)
    steps.append(("清理填充词后", text2))
    
    if debug:
        for step_name, step_text in steps:
            print(f"\n=== {step_name} ===")
            print(step_text[:500])
    
    return steps[-1][1]
```

## 扩展可能性

### 1. 多语言支持
扩展以支持英文、日文等其他语言的字幕处理。

### 2. AI增强
集成GPT等大语言模型进行智能摘要和重组。

### 3. 实时处理
开发浏览器扩展或桌面应用，实时处理视频字幕。

### 4. 云服务
部署为Web服务，提供API接口。

---

## 总结

这个Skill提供了一套完整的视频字幕整理优化流程，可以显著降低token使用量，提升文本质量。通过自动化处理重复性任务，让用户能够更专注于内容本身，而不是文本格式的整理工作。

**核心优势：**
- 节省时间：自动化处理节省大量手动整理时间
- 降低成本：减少token使用，降低AI处理成本
- 提升质量：结构化文本更易读、更专业
- 灵活定制：可根据需要调整处理参数

将这套流程集成到您的工作流中，可以大幅提升视频字幕处理的效率和质量。