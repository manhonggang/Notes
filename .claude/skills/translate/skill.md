---
name: translate
description: Translate English notes into polished, natural-sounding Chinese. Creates a new translated note in the same folder and bidirectionally links both notes via wikilinks. Use when the user asks to translate an English note, or says "翻译" with a note open.
---

# Translate

A workflow for translating English notes in the Obsidian vault into fluent, natural Chinese — not stiff machine translation, but polished prose that reads as if it were originally written in Chinese. The original note and the translated note are connected via bidirectional wikilinks.

## Scope

**This skill works on:**

| Source type | Examples | Notes |
|-------------|----------|-------|
| English articles / essays | Blog posts, tutorials, opinion pieces | Primary use case |
| English reference notes | Documentation excerpts, textbook sections | Preserve technical terms carefully |
| English literature notes | Book highlights, paper summaries | Maintain the original's tone |

**This skill does NOT work on:**

| Source type | Why not |
|-------------|---------|
| Notes already in Chinese | No translation needed |
| Pure code / config files | Translation is meaningless |
| Notes under ~20 words | Too short; translate inline instead |

## Key Principles

1. **信 (Fidelity)** — Do not add, omit, or distort the author's meaning. Every claim, caveat, and nuance in the original must be preserved.
2. **达 (Fluency)** — The Chinese text must flow naturally. Break long English sentences into shorter Chinese ones. Rearrange clauses to match Chinese word order. Use Chinese rhetorical patterns (e.g., parallelism, topic-comment structure) where they improve readability.
3. **雅 (Elegance)** — Avoid translationese (翻译腔). Do not mechanically mirror English syntax. Use idiomatic Chinese phrasing. Prefer four-character idioms (成语) only when they genuinely fit — do not force them.

### What "polished" means concretely

- **No stilted phrasing**: "这是一个非常重要的事情" → "这件事至关重要"
- **No passive abuse**: Chinese prefers active voice. "It is considered that..." → "人们认为……" or rephrase to active.
- **No dangling ellipsis**: English routinely elides verbs to avoid repetition. Chinese lacks this mechanism — every clause must be semantically complete. Always **reconstruct the elided verb or meaning** explicitly, or rephrase to avoid the gap. Example: "…and ensure that China does not" → the "does not" refers back to "win the race". Bad: "确保中国不会" (won't… what?). Good: "确保中国不会赢得这场竞赛" or "绝不让中国反超". Apply this systematically to all auxiliary ellipsis (do/did/can/will/so/neither/not).
- **No noun-stack transplant**: English piles nouns before a head noun, with prepositions indicating their relationship ("the race **to** global AI technological superiority"). Chinese cannot mirror this — it creates incoherent modifier chains. The key is to **read the preposition**: "to" signals a purpose/direction (verb-object), "of" signals possession, "for" signals a goal. Example: "the race **to** global AI technological superiority" → the race aims **to achieve** superiority, so the relationship is verb-object, not modification. Bad: "全球AI技术优势的竞赛" (superiority's race — makes no sense). Good: "争夺全球AI技术优势的竞赛" (race to **compete for** superiority — verb-object made explicit) or simply "全球AI技术竞赛" (drop the unpacked intermediary when context is clear).
- **Natural connectives**: Replace mechanical "此外/另外/而且" chains with varied Chinese transitions that fit the logic (况且、与此同时、不仅如此、反之、然而、结果……).
- **Sentence rhythm**: Alternate short punchy sentences with longer explanatory ones. Chinese prose benefits from rhythmic variation (长短句交替).
- **Technical terms**: Keep widely-accepted English terms in their common Chinese form (e.g., NP-Hard → NP困难问题). If no standard Chinese translation exists, keep the English term and add a brief parenthetical explanation on first use.
- **Proper nouns**: Keep personal names in English (e.g., Raph Koster stays as Raph Koster). Place names and well-known brands use their standard Chinese names (e.g., Google → 谷歌).
- **Formatting preservation**: Maintain the original's headings, lists, bold, italic, blockquotes, callouts, and code blocks. Translate text *within* these structures, not the structures themselves.

## Workflow

> **执行纪律（MUST follow）：**
>
> 1. 五个步骤**必须严格按顺序逐一执行**，不得合并、跳过或打乱顺序。
> 2. **Step 2（初译）和 Step 3（润色）是两个独立步骤，绝不可合并为一步完成。** 初译关注"译出"，润色关注"译好"——二者目的不同，必须在初译完成后**重新通读全篇译文**再进行润色。
> 3. 每完成一个步骤，**必须**用 TodoWrite 将该步骤标记为 completed，再将下一步标记为 in_progress，然后才执行下一步。这是执行的硬约束，不是建议。
> 4. **静默执行**：Step 1–4 的分析过程不向用户输出。Step 1 的语调/术语分析、Step 3 的七项检查详情均在内部完成，仅通过 TodoWrite 追踪进度。**静默仅指不输出，不等于可以跳过任何步骤或检查项。** 全部完成后，Step 5 向用户发送一句简短的结果摘要。

### Step 1: Read and understand the source

1. Read the full source note, including frontmatter and any embedded images.
2. Follow critical wikilinks to understand context if the source references other notes.
3. Identify the note's **tone** (academic? conversational? persuasive? tutorial?), **audience**, and **domain-specific terminology**.
4. Note any cultural references, idioms, or humor that may need adaptation rather than literal translation.

**Step 1 完成**：已读取全文，已记录语调/受众/术语清单（内部，不输出）。标记 TodoWrite 后进入 Step 2。

### Step 2: Translate — first pass

Translate the full content section by section. During this pass:

- Preserve **all** frontmatter fields. Add a `translation_of` field pointing to the original note (as a wikilink). Add `lang: zh` if the original has `lang: en`.
- Translate the title. If the original title is a proper noun or widely known in English, you may keep it in English and add a Chinese subtitle: `游戏设计基础 (The Fundamentals of Game Design)`.
- For each paragraph, translate meaning first, then polish phrasing. Do not translate word-by-word.
- Keep markdown formatting intact (headings, lists, bold, italic, blockquotes, callout syntax, code blocks, etc.).
- Translate alt text in image embeds if present.
- Do NOT translate code blocks (content inside ``` ```). Only translate code comments within code blocks if they are explanatory.
- **本步骤的目标是"译出完整内容"，不是"译出完美译文"。** 不要在本步骤中试图同时完成 Step 3 的润色工作。

**Step 2 完成**：初译全文已写入文件。标记 TodoWrite 后进入 Step 3。

### Step 3: Polish — second pass

> **此步骤为强制独立步骤。** 必须在初译文件已写入之后，**重新通读全文译文**，逐项执行以下七项检查。不可跳过任何一项。每项检查必须明确产出结果（找到的问题 + 修改方案），然后统一写入文件。

**重新通读译文**：先 Read 已写入的译文文件全篇，再逐项检查。

1. **Rhythm check** — Read aloud in your head. Does it flow? Break overly long sentences. Merge choppy ones. 记录需要调整的长句/碎句位置。
2. **Ellipsis check** — Scan for any clause ending in an auxiliary (会/能/将/是/做了) without a main verb. Every Chinese sentence must be semantically complete. If the original used English verb ellipsis, reconstruct the missing verb or rephrase entirely. (e.g., "ensure that China does not" → "确保中国不会赢得这场竞赛", not "确保中国不会"). 逐一对照原文中的 do/did/can/will/so/neither/not 省略，确认译文已补全。
3. **Noun-stack check** — Scan for long modifier chains ending in 的+Noun. Look back at the English original: what preposition connected those nouns? If "to" or "for" was used, the relationship is likely verb-object or purpose — insert a verb to unpack it. (e.g., "the race **to** superiority" → "争夺优势的竞赛", not "优势的竞赛"; "regulation **for** privacy" → "保障隐私的法规", not "隐私法规" when context means regulations *that protect* privacy). 列出找到的名词堆叠及拆解方案。
4. **Redundancy check** — Remove filler words that English needs but Chinese doesn't (e.g., excessive 的, 了的, 在……方面). 标记需删减的位置。
5. **Cohesion check** — Ensure transitional phrases are natural and varied. Chinese uses fewer explicit connectors than English; sometimes omitting a connector is more natural. 标记需调整的衔接处。
6. **Terminology consistency** — The same English term should always be translated the same way throughout. Build a mini glossary as you go. 列出术语对照表，检查全篇一致性。
7. **Tone match** — If the original is witty, preserve the wit. If formal, stay formal. If tutorial-style, stay clear and direct. 对照 Step 1 记录的语调，确认译文是否匹配。

**七项检查完成后**，将所有修改统一写入译文文件。

**Step 3 完成**：七项检查全部执行完毕，修改已写入文件。标记 TodoWrite 后进入 Step 4。

### Step 4: Create the translated note

1. **Determine the location**: Place the translated note in the **same folder** as the original. Name it by translating the title, or using the original English title with a Chinese translation appended. If the original is `见闻资料/The Fundamentals of Game Design.md`, the translation could be `见闻资料/游戏设计基础.md`.
2. **Write the translated file** with the polished content (if not already written in Step 2).
3. **Add frontmatter**:
   ```yaml
   ---
   created: <current datetime>
   tags: <same tags as original>
   source: <original source URL if present>
   translation_of: "[[Original Note Name]]"
   lang: zh
   ---
   ```
4. **Add a link to the original** at the top of the translated note (after the title heading):
   ```markdown
   > 原文：[[Original Note Name]]
   ```
5. **Add a link to the translation** in the original note. Insert after the title heading (or at the top if no heading):
   ```markdown
   > 译文：[[Translated Note Name]]
   ```

**Step 4 完成**：译文文件已创建，双向链接已添加。标记 TodoWrite 后进入 Step 5。

### Step 5: Verify

1. **Completeness** — Compare original and translation paragraph by paragraph. Ensure no section was accidentally skipped.
2. **Link integrity** — Open both notes and verify the wikilinks resolve correctly in Obsidian.
3. **Frontmatter** — Confirm `translation_of` points correctly and `lang` is set.
4. **No orphaned formatting** — Check that no markdown syntax was broken during translation (unclosed bold, broken list indentation, etc.).
5. **Step 3 checklist review** — Re-confirm that all 7 polish checks from Step 3 were applied (not just planned). If any were skipped, go back and execute them now.

**Step 5 完成**：所有验证通过。向用户发送一句简短的结果摘要（仅此时输出）。

## Handling Special Cases

### Blockquotes and callouts
Translate the content inside callouts. Keep the callout type keyword in English (e.g., `[!warning]`, `[!tip]`) — Obsidian uses these for rendering. Translate the custom title if one is provided:
```markdown
> [!warning] 注意
> 这里的翻译内容
```

### Tables
Translate header rows and cell content. Keep alignment syntax (`|---|---|`) intact.

### Footnotes
Translate footnote content. Keep the reference markers (`[^1]`) matching.

### Embedded content (`![[note]]` or `![[image]]`)
Do NOT translate the embed target (filename). If the embedded note also needs translation, that is a separate invocation of this skill. Add a brief note below the embed:
```markdown
![[Some English Note]]
> ^上方嵌入的笔记尚未翻译
```

### Mixed-language content
If the original already contains Chinese (e.g., a bilingual note), preserve the existing Chinese and only translate the English portions.

## Language

The translated note is in Chinese. The skill's own status messages and confirmations to the user should be in Chinese (matching the user's language preference). Audit notes about translation choices may be written in either language.
