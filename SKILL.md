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

Apply these rules directly to Chinese prose. Preserve Chinese as the working language; do not translate the text into English, and do not force English rhetorical patterns onto Chinese technical writing.

1. **Write mechanisms directly.** Prefer concrete execution flow, inputs, outputs, and code relationships. Avoid loose claims such as "本质上", "真正", "核心", "非常", "其实", "简单来说" when the sentence can name the mechanism.

2. **Use sequence words only when they carry structure.** Words like "首先", "其次", "最后" are fine for real ordered steps. Do not use them as a default paragraph rhythm or as filler before every point.

3. **Avoid mechanical contrast in Chinese.** Rewrite "不是……而是……", "不只是……还……", "并非……而是……" by stating the positive claim directly.

4. **Reduce quotation marks around concepts.** Do not wrap ordinary technical terms in Chinese quotes or double quotes. Keep quotes for source strings, UI text, exact wording under analysis, direct citations, Mermaid syntax, or code snippets.

5. **Keep code and formulas in their own lanes.** Use Markdown LaTeX for formulas, inline `\( ... \)` and display `$$ ... $$`. Use code blocks for real code or literal examples. Do not put explanatory prose inside a Rust code block unless it is a source comment.

6. **Explain code by role, not line by line.** After a code excerpt, explain what it proves about the mechanism, which function called into it, and what downstream object consumes its result.

7. **Use examples that match the real object.** A simplified example must return to the actual engineering object before the paragraph ends. For example, a Boolean-table intuition for a selector should connect back to random-point evaluation of the selector polynomial.

8. **Prefer source-anchored symbols.** In protocol notes, align notation with official docs or papers when available. If no stable notation exists, tie symbols to source variable names so later code reading stays consistent.

9. **Remove casual metaphors from technical mechanisms.** Replace phrases like "event bucket", "black box", "run eval", "squash into", "drop into", or "feed into" with the actual source object or protocol action: event collection, verifier logic, call `Air::eval`, random linear combination, reduction, mapping, commitment, opening claim.

10. **Follow the real call chain in source-reading notes.** When a function calls another function, enter the callee, explain the local state transition, then return to the caller. Avoid detached overviews that list modules without showing execution order.

11. **Preserve good existing prose and comments.** Edit only the part that is vague, misleading, too colloquial, or missing necessary context. Do not rewrite a stable paragraph just to make the style uniform.

12. **Make long technical sections locally readable.** When a section introduces a symbol, variable dimension, challenge, structure field, or protocol object, define it near first use or point to the exact earlier section. Do not force the reader to remember a long front-loaded glossary.

13. **Use exact source nouns for data containers.** Prefer `ExecutionRecord` event collection, trace matrix, column MLE, padded row, padding column, dense representation, prover data, verifier key, and opening claim over loose terms like "bucket", "list of things", "the packed data", or "the proof stuff".

14. **Keep protocol boundaries explicit.** Say whether a mechanism belongs to execution witness generation, AIR/constraint evaluation, PIOP, PCS commitment/opening, transcript binding, or recursion verification. This prevents prose from merging constraint validity with commitment binding.

15. **Use diagrams and tables selectively.** Prefer prose or Mermaid diagrams when they clarify data flow, containment, or verification dependency. If a diagram uses arrows, keep one arrow meaning per diagram and make the prose match it.

16. **Avoid unnecessary inline code styling.** Use backticks for real code identifiers, paths, commands, and source strings. Do not wrap ordinary English terms or repeated conceptual nouns in backticks for emphasis.

17. **For source comments, attach context to the right item.** Function-level and struct-field teaching comments should describe upstream input, local role, and downstream consumer. Keep Rust `///` comments attached to the item they document; do not let macro-level comments drift onto the next field or function.

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
- Technical metaphor hiding a real object? Replace it with the source type, field, function, or protocol step.
- Source-reading section jumps across modules without execution order? Rewrite it as caller -> callee -> return-to-caller.
- Long section relies on a glossary from many pages earlier? Add a local definition or precise back-reference.
- Protocol layer blurred? Name the layer: witness generation, AIR, PIOP, PCS, transcript, verifier, or recursion.
- Diagram arrows mean multiple things? Split the diagram or rewrite labels until every arrow has one meaning.
- Backticks around ordinary concepts? Remove them unless the text names code, commands, paths, source strings, or exact literals.
- Rust doc comment added? Check it still attaches to the intended function, struct, enum variant, or field.

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
