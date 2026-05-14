---
name: note-deepen
description: Deepen and tighten a structured note by distinguishing insight from common knowledge, trimming hollow content, elevating buried insights, and ensuring structural integrity. Use when the user asks to refine, tighten, or audit the insight density of a note.
---

# Note Deepen

A systematic workflow for deepening structured notes — especially framework documents, principle lists, argumentative essays, and any note organized around discrete claims. The core premise: a note's value is not in how many true things it says, but in how many non-obvious, action-guiding things it says.

## Scope

**This skill works on:**

| Note type | Examples | Why it fits |
|-----------|----------|-------------|
| Framework / principle documents | 游戏设计原则体系, 写作原则十条 | Organized around numbered, discrete claims with internal hierarchy |
| Argumentative long-form notes | 为什么免费游戏比买断制更适合长线运营 | A central thesis supported by layered claims |
| Comparison / analysis notes | 塔科夫 vs 暗区突围 | Discrete comparative claims that can be audited for depth |
| Method / process notes | 怎样构思一个游戏系统 | Step-by-step claims where some steps may be hollow |

**This skill does NOT work on:**

| Note type | Why not |
|-----------|---------|
| Narrative / journal entries | No claim structure to audit |
| Pure reference / literature notes | Value is in faithful recording, not insight density |
| Stream-of-consciousness / brainstorming | Structure is intentionally absent |
| Notes whose primary value is emotional or poetic | Insight/noise framing is wrong lens |

When in doubt, ask the user before applying this skill.

## Key Concepts Defined

Before auditing, understand these terms:

**Section** — The smallest self-contained unit the author intended as a discrete point. In a structured note, this is typically one numbered subsection or one `###` heading block. In a prose note, it may be one paragraph that makes a single claim. If a paragraph makes three distinct claims, treat it as three sections for audit purposes.

**Claim** — A statement the author asserts as true or prescriptive. "规则维度应该正交" is a claim. "围棋只有一种棋子" is a fact supporting a claim. Do not audit bare facts — audit the claims.

**Insight (positive definition)** — A claim is an insight if, after reading it, a practitioner would make a *different decision* than they would have without it. It rules out a path that was previously plausible. "限制创造策略" is an insight because without it, a designer might build an unrestricted system. "取舍很重要" is NOT an insight because no designer would build without trade-offs — it rules out nothing.

**"正确的废话" (negative definition)** — A claim is hollow if any of these is true:
1. **Its negation is absurd.** "取舍很重要" → who would say 取舍不重要?
2. **It applies identically to any domain.** "要看底层结构" applies equally to software architecture, urban planning, and cooking.
3. **It is fully subsumed** by another claim already in the note.

**Structural load** — A claim carries structural load if removing it would break something: a taxonomy would be incomplete (2 of 3 items), a logical chain would have a missing link, or a later claim would lose its prerequisite. Common-knowledge claims with structural load should be **kept**; those without should be **trimmed**.

**Insight spine** — The vertical chain of original claims that, if extracted and read in sequence, still communicates the note's core contribution. Typically 2-5 claims. Everything else in the note exists to support, connect to, or execute from this spine. If a note has no identifiable spine, it may be a flat list — in that case, the audit should focus on per-item depth rather than spine integrity.

## When to Use

**User triggers (explicit requests):**
- User says a note "lacks insight" or "is too full of common knowledge"
- User asks to "tighten", "deepen", "compact", or "audit" a note
- User asks "what's the insight density of this note?"

**Agent-side judgment (proactive use):**
- A note has many subsections but some feel thin or repetitive on reading
- A note is organized as a numbered list of principles/claims
- The user is iteratively refining the same note and has expressed dissatisfaction with its depth

**Do NOT use when:**
- The note is under 100 words (too short for structural audit)
- The note is a daily journal, log, or stream-of-consciousness
- The user has just created the note and hasn't expressed dissatisfaction with it
- The note's primary function is to link to or quote other sources

## Workflow

### Phase 1: Audit (read-only — no edits)

1. **Read the full note.** Follow wikilinks to linked notes only if they are essential to understanding the current note's claims. Do not audit linked notes.

2. **Identify sections.** Partition the note into auditable units. For structured notes, follow the author's own section boundaries. For prose, split at claim boundaries.

3. **Classify each section** into one of four tiers:

| Tier | Label | What it means | Default action |
|------|-------|---------------|----------------|
| **A** | Core insight | Would change a practitioner's decisions. Its removal would noticeably weaken the note. | Keep. Possibly elevate in prominence. |
| **B** | Structural common knowledge | Individually unremarkable but load-bearing — removing it would break a taxonomy, leave a logical gap, or orphan a downstream claim. | Keep. Note its structural role. |
| **C** | Buried insight | Contains a genuine insight but it's buried under a weak label, hidden in a subordinate clause, or overshadowed by surrounding fluff. The wrapper is weak; the content is strong. | Excavate: extract the insight, discard the wrapper. |
| **D** | Hollow / redundant | Correct but empty (fails the 正确废话 test), or fully covered by another section. | Remove. |

4. **Identify the insight spine.** List the 2-5 claims that form the note's vertical core — the minimum set that, if extracted, still communicates the note's contribution.

5. **Present the audit report.** Format:

```
## Audit: [note name]

### Insight spine
1. [claim A] — because [why it changes decisions]
2. [claim B] — ...

### Tier breakdown
| Tier | Count | Sections |
|------|-------|----------|
| A | N | 1.1, 2.3, ... |
| B | N | 1.2 (structural: completes 3-part taxonomy), ... |
| C | N | 2.4 (buried: the 技巧 about X is sharper than the parent 原则) |
| D | N | 1.3 (hollow: applies to any domain), ... |

### Structural dependencies
- 1.2 carries load: removing it would leave 2.1 without its prerequisite
- ...

### Recommendations summary
- Remove: [D-tier items]
- Excavate: [specific C-tier gems and where to relocate them]
- Reframe: [specific weak labels and proposed alternatives]
```

6. **Wait for user confirmation** before any edits. Do not skip this step.

### Phase 2: Restructure (edits with approval)

Based on the approved audit, execute changes. Available operations:

**1. Remove hollow content**
- Delete Tier D sections
- If a D section has one salvageable sentence, extract it and merge into the nearest relevant section, then delete the D section

**2. Elevate buried insights**
- If a subordinate element (sub-bullet, 技巧, footnote, parenthetical) is sharper than its parent section, promote it into the parent's core claim
- If a section has a weak title but strong body, rewrite the title to match the body's actual insight

**3. Merge overlapping claims**
- When two sections make the same point from different angles, combine into one section that captures both perspectives
- When one section is strictly a subset of another, either make the hierarchy explicit or absorb the subset

**4. Split overloaded sections**
- When one section packs multiple independent insights, split into separate sections
- Indicators: the section has multiple 依据 bullets that don't all support the same claim, or the reader would cite different parts for different purposes

**5. Reorder for logical flow**
- After removals and splits, check if the remaining sections are in the best order
- Preferred orders: foundation → application, simple → complex, diagnosis → prescription, or the author's explicit hierarchy

**6. Reframe weak labels**
- A label is weak if it states a truism (its negation is absurd), is too vague to be actionable, or doesn't match the section's actual content
- Proposed replacement must be specific enough that its negation is a defensible position

**7. Fill gaps**
- After removal, check if any remaining sections now reference a missing prerequisite
- If a gap is created, either: restore the minimum necessary content, or add a brief bridging sentence

**8. Tighten references**
- After any renumbering or removal, search for all old references (numbering, section names, wikilinks) and update them
- Remove cross-references that pointed to deleted content
- If the note has a relationship diagram or graph, update it to reflect the new structure

### Phase 3: Verify

After all edits, confirm:

1. **Reference integrity** — grep for orphaned references (old numbering, deleted section names, broken wikilinks). Fix any found.

2. **Insight spine coherence** — read only the A-tier claims in sequence. Do they still form a coherent argument? If not, the spine was damaged during restructuring.

3. **No hollow residue** — re-apply the 正确废话 test to every remaining section. If any new hollow content was exposed by restructuring, flag it.

4. **Structural completeness** — for each B-tier item, confirm: is the thing it was supporting still present? If the dependent was removed, the B-tier item may now be removable too.

5. **Question answered** — re-read the note's title and opening. Does the restructured note still answer the question or fulfill the purpose it was created for? If not, something essential was removed.

6. **Preserve original** — before destructive edits, the original file should have been preserved. If the user did not explicitly say to overwrite, ensure a backup exists (e.g., as `笔记名（原版）.md` or via git).

## Calibration

**Iterate; don't strip-mine.** This skill is designed for one pass at a time. After Phase 3, the user may request another pass. Do not attempt to remove every possible weakness in one pass — the risk of over-trimming is higher than the risk of under-trimming.

**When in doubt, keep.** A section that is borderline B/D should default to B (keep). The user can always remove it in a second pass. A section that is removed cannot be recovered unless a backup exists.

**Stop condition.** A note is "deep enough" when:
- No D-tier sections remain
- All C-tier insights have been excavated (promoted or relocated)
- Remaining B-tier items have a verified structural role
- The insight spine reads coherently without gaps

After this point, further passes will produce diminishing returns. Stop and tell the user the note has been deepened to the extent this framework can offer.

## Language

Audit reports and recommendations should be written in the same language as the note being audited. For Chinese notes, write everything in Chinese. Tier labels (A/B/C/D) may be kept in English for concision.
