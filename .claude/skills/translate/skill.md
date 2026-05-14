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
- **Natural connectives**: Replace mechanical "此外/另外/而且" chains with varied Chinese transitions that fit the logic (况且、与此同时、不仅如此、反之、然而、结果……).
- **Sentence rhythm**: Alternate short punchy sentences with longer explanatory ones. Chinese prose benefits from rhythmic variation (长短句交替).
- **Technical terms**: Keep widely-accepted English terms in their common Chinese form (e.g., NP-Hard → NP困难问题). If no standard Chinese translation exists, keep the English term and add a brief parenthetical explanation on first use.
- **Proper nouns**: Keep personal names in English (e.g., Raph Koster stays as Raph Koster). Place names and well-known brands use their standard Chinese names (e.g., Google → 谷歌).
- **Formatting preservation**: Maintain the original's headings, lists, bold, italic, blockquotes, callouts, and code blocks. Translate text *within* these structures, not the structures themselves.

## Workflow

### Step 1: Read and understand the source

1. Read the full source note, including frontmatter and any embedded images.
2. Follow critical wikilinks to understand context if the source references other notes.
3. Identify the note's **tone** (academic? conversational? persuasive? tutorial?), **audience**, and **domain-specific terminology**.
4. Note any cultural references, idioms, or humor that may need adaptation rather than literal translation.

### Step 2: Translate — first pass

Translate the full content section by section. During this pass:

- Preserve **all** frontmatter fields. Add a `translation_of` field pointing to the original note (as a wikilink). Add `lang: zh` if the original has `lang: en`.
- Translate the title. If the original title is a proper noun or widely known in English, you may keep it in English and add a Chinese subtitle: `游戏设计基础 (The Fundamentals of Game Design)`.
- For each paragraph, translate meaning first, then polish phrasing. Do not translate word-by-word.
- Keep markdown formatting intact (headings, lists, bold, italic, blockquotes, callout syntax, code blocks, etc.).
- Translate alt text in image embeds if present.
- Do NOT translate code blocks (content inside ``` ```). Only translate code comments within code blocks if they are explanatory.

### Step 3: Polish — second pass

Re-read the full Chinese translation end-to-end and polish:

1. **Rhythm check** — Read aloud in your head. Does it flow? Break overly long sentences. Merge choppy ones.
2. **Redundancy check** — Remove filler words that English needs but Chinese doesn't (e.g., excessive 的, 了的, 在……方面).
3. **Cohesion check** — Ensure transitional phrases are natural and varied. Chinese uses fewer explicit connectors than English; sometimes omitting a connector is more natural.
4. **Terminology consistency** — The same English term should always be translated the same way throughout. Build a mini glossary as you go.
5. **Tone match** — If the original is witty, preserve the wit. If formal, stay formal. If tutorial-style, stay clear and direct.

### Step 4: Create the translated note

1. **Determine the location**: Place the translated note in the **same folder** as the original. Name it by translating the title, or using the original English title with a Chinese translation appended. If the original is `见闻资料/The Fundamentals of Game Design.md`, the translation could be `见闻资料/游戏设计基础.md`.
2. **Write the translated file** with the polished content.
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

### Step 5: Verify

1. **Completeness** — Compare original and translation paragraph by paragraph. Ensure no section was accidentally skipped.
2. **Link integrity** — Open both notes and verify the wikilinks resolve correctly in Obsidian.
3. **Frontmatter** — Confirm `translation_of` points correctly and `lang` is set.
4. **No orphaned formatting** — Check that no markdown syntax was broken during translation (unclosed bold, broken list indentation, etc.).

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
