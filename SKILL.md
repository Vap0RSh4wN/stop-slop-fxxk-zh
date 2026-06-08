---
name: stop-slop
description: Remove AI writing patterns from prose. Use when drafting, editing, or reviewing text to eliminate predictable AI tells.
metadata:
  trigger: Writing prose, editing drafts, reviewing content for AI patterns
  author: Hardik Pandya (https://hvpandya.com)
---

# Stop Slop

Eliminate predictable AI writing patterns from prose.

## Core Rules

1. **Cut filler phrases.** Remove throat-clearing openers, emphasis crutches, and all adverbs. See [references/phrases.md](references/phrases.md).

2. **Break formulaic structures.** Avoid binary contrasts, negative listings, dramatic fragmentation, rhetorical setups, false agency. See [references/structures.md](references/structures.md).

3. **Use active voice.** Every sentence needs a human subject doing something. No passive constructions. No inanimate objects performing human actions ("the complaint becomes a fix").

4. **Be specific.** No vague declaratives ("The reasons are structural"). Name the specific thing. No lazy extremes ("every," "always," "never") doing vague work.

5. **Put the reader in the room.** No narrator-from-a-distance voice. "You" beats "People." Specifics beat abstractions.

6. **Vary rhythm.** Mix sentence lengths. Two items beat three. End paragraphs differently. No em dashes.

7. **Trust readers.** State facts directly. Skip softening, justification, hand-holding.

8. **Cut quotables.** If it sounds like a pull-quote, rewrite it.

## Chinese Technical Notes

Use these additions when editing Chinese technical notes, source-code reading notes, protocol analysis, or engineering documentation.

1. **Write mechanisms directly.** Prefer concrete execution flow, inputs, outputs, and code relationships. Avoid loose claims such as "本质上", "真正", "核心", "非常", "其实", "简单来说" when the sentence can name the mechanism.

2. **Use sequence words only when they carry structure.** Words like "首先", "其次", "最后" are fine for real ordered steps. Do not use them as a default paragraph rhythm or as filler before every point.

3. **Avoid mechanical contrast in Chinese.** Rewrite "不是……而是……", "不只是……还……", "并非……而是……" by stating the positive claim directly.

4. **Reduce quotation marks around concepts.** Do not wrap ordinary technical terms in Chinese quotes or double quotes. Keep quotes for source strings, UI text, exact wording under analysis, direct citations, Mermaid syntax, or code snippets.

5. **Keep code and formulas in their own lanes.** Use Markdown LaTeX for formulas, inline `\( ... \)` and display `$$ ... $$`. Use code blocks for real code or literal examples. Do not put explanatory prose inside a Rust code block unless it is a source comment.

6. **Explain code by role, not line by line.** After a code excerpt, explain what it proves about the mechanism, which function called into it, and what downstream object consumes its result.

7. **Use examples that match the real object.** A simplified example must return to the actual engineering object before the paragraph ends. For example, a Boolean-table intuition for a selector should connect back to random-point evaluation of the selector polynomial.

8. **Prefer source-anchored symbols.** In protocol notes, align notation with official docs or papers when available. If no stable notation exists, tie symbols to source variable names so later code reading stays consistent.

## Quick Checks

Before delivering prose:

- Any adverbs? Kill them.
- Any passive voice? Find the actor, make them the subject.
- Inanimate thing doing a human verb ("the decision emerges")? Name the person.
- Sentence starts with a Wh- word? Restructure it.
- Any "here's what/this/that" throat-clearing? Cut to the point.
- Any "not X, it's Y" contrasts? State Y directly.
- Three consecutive sentences match length? Break one.
- Paragraph ends with punchy one-liner? Vary it.
- Em-dash anywhere? Remove it.
- Vague declarative ("The implications are significant")? Name the specific implication.
- Narrator-from-a-distance ("Nobody designed this")? Put the reader in the scene.
- Meta-joiners ("The rest of this essay...")? Delete. Let the essay move.
- Chinese concept quotes around ordinary terms? Remove them unless they are source strings, exact wording, citations, Mermaid syntax, or code.
- Chinese sequence words everywhere? Keep "首先/其次/最后" only when the paragraph has a real ordered sequence.
- Chinese technical paragraph after code missing upstream/current/downstream context? Add the calling function, local mechanism, and consumed result.

## Scoring

Rate 1-10 on each dimension:

| Dimension | Question |
|-----------|----------|
| Directness | Statements or announcements? |
| Rhythm | Varied or metronomic? |
| Trust | Respects reader intelligence? |
| Authenticity | Sounds human? |
| Density | Anything cuttable? |

Below 35/50: revise.

## Examples

See [references/examples.md](references/examples.md) for before/after transformations.

## License

MIT
