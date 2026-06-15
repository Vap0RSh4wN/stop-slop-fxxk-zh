---
name: stop-slop
description: Use when drafting, editing, or reviewing prose to remove predictable AI patterns, especially in Chinese-native technical writing, notes, and source-reading material.
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

5. **Write as the author, not as a guide.** No narrator-from-a-distance voice. No second-person coaching. No lines that stage the explanation, describe the writing act, or tell the reader how to read.

6. **Vary rhythm.** Mix sentence lengths. Two items beat three. End paragraphs differently. No em dashes.

7. **Trust readers.** State facts directly. Skip softening, justification, hand-holding.

8. **Cut quotables.** If it sounds like a pull-quote, rewrite it.

9. **Cut empty framing words.** Words like "intuition," "essence," "core," "mechanism," or "logic" do not explain anything by themselves. Keep them only when the sentence immediately names the concrete object, action, or claim.

10. **Name the operation.** Ban vague transport and compression verbs when they hide the real action. Replace "compress," "drop into," "feed into," "flatten," "bucket," "pipeline," or similar filler with the actual operation.

11. **Keep formatting quiet.** Do not use backticks, quotation marks, bold, or italics as rhythm substitutes or emphasis crutches.

12. **Prefer paragraphs and diagrams over tables.** Use prose by default. Use diagrams for flow, dependency, or containment. Use tables only when alignment is necessary for comparison.
## Chinese Technical Notes

Use these additions when editing Chinese technical notes, source-code reading notes, protocol analysis, or engineering documentation.

Apply these rules directly to Chinese prose. Preserve Chinese as the working language. Treat native Chinese technical writing as the default priority. Do not translate the text into English, do not insert English rhetorical scaffolding into Chinese notes, and do not shape Chinese prose around common AI bilingual habits.

1. **Write mechanisms directly.** Prefer concrete execution flow, inputs, outputs, and code relationships. Avoid loose claims such as "本质上", "真正", "核心", "非常", "其实", "简单来说" when the sentence can name the mechanism.

2. **Use sequence words only when they carry structure.** Words like "首先", "其次", "最后" are fine for real ordered steps. Do not use them as a default paragraph rhythm or as filler before every point.

3. **Avoid mechanical contrast in Chinese.** Rewrite "不是……而是……", "不只是……还……", "并非……而是……" by stating the positive claim directly.

4. **Reduce quotation marks around concepts.** Do not wrap ordinary technical terms in Chinese quotes or double quotes. Keep quotes for source strings, UI text, exact wording under analysis, direct citations, Mermaid syntax, or code snippets.

5. **Keep code and formulas in their own lanes.** Use Markdown LaTeX for formulas and code blocks for real code or literal examples. Do not put explanatory prose inside a Rust code block unless it is a source comment.

6. **Explain code by role and state transition.** Do not paraphrase obvious lines just to mirror the source. For code excerpts and source comments, attach upstream input, local transformation, and downstream consumer to the exact line, field, or function that needs explanation.

7. **Use examples that match the real object.** A simplified example must return to the actual engineering object before the paragraph ends. For example, a Boolean-table intuition for a selector should connect back to random-point evaluation of the selector polynomial.

8. **Prefer source-anchored symbols.** In protocol notes, align notation with official docs or papers when available. If no stable notation exists, tie symbols to source variable names so later code reading stays consistent.

9. **Remove casual metaphors from technical mechanisms.** Replace phrases like "事件桶", "黑盒", "跑一遍", "压成", "落成", "塞进", "喂给", "吃掉", "打通", "串起来", "这条链压成", "event bucket", "black box", "run eval", "squash into", "drop into", or "feed into" with the actual source object or protocol action.

10. **Follow the real execution order in source-reading notes.** When a function calls another function, enter the callee, explain the local state transition, then return to the caller. Avoid detached overviews that list modules without showing execution order. Avoid placeholder words such as "调用链", "时间线", "这条链", or "这一层" when the exact sequence can be written directly.

11. **Preserve good existing prose and comments.** Edit only the part that is vague, misleading, too colloquial, or missing necessary context. Do not rewrite a stable paragraph just to make the style uniform.

12. **Make long technical sections locally readable.** When a section introduces a symbol, variable dimension, challenge, structure field, or protocol object, define it near first use or point to the exact earlier section. Do not force the reader to remember a long front-loaded glossary.

13. **Use exact source nouns for data containers.** Prefer `ExecutionRecord` event collection, trace matrix, column MLE, padded row, padding column, dense representation, prover data, verifier key, and opening claim over loose terms like "bucket", "list of things", "the packed data", or "the proof stuff".

14. **Keep protocol boundaries explicit.** Say whether a mechanism belongs to execution witness generation, AIR/constraint evaluation, PIOP, PCS commitment/opening, transcript binding, or recursion verification. This prevents prose from merging constraint validity with commitment binding.

15. **Prefer diagrams over tables for structure.** Use prose by default. Use Mermaid diagrams when they clarify data flow, containment, execution order, or verification dependency. Use tables only when the reader must compare aligned dimensions side by side. If a diagram uses arrows, keep one arrow meaning per diagram and make the prose match it.

16. **Avoid inline code styling by default.** Do not use backticks for emphasis, routine identifiers, repeated conceptual nouns, or ordinary English terms inside Chinese prose. Keep them only for exact literals, commands, paths, syntax that would become ambiguous without marking, or executable text copied verbatim.

17. **For source comments, attach context to the right item.** Function-level and struct-field teaching comments should describe upstream input, local role, and downstream consumer. Keep Rust `///` comments attached to the item they document; do not let macro-level comments drift onto the next field or function.

18. **Remove narrator voice and self-talk.** Cut lines such as "下面", "接下来", "这里可以看到", "我们先看", "再看", "本文", "本节", "这一段", "let us", "we now", or "as we will see" when they describe the explanation instead of the subject.

19. **Do not instruct the reader.** Remove phrases such as "你可以把它看成", "读者需要注意", "可以先记住", "想象一下". State the object, relation, or operation directly.

20. **Replace vague structure labels with explicit sequences.** Do not use words like "调用链", "时间线", "流程线", "这部分逻辑", or "这一块内容" as stand-ins for actual structure. Write the functions, events, fields, or state transitions in order.

21. **Ban empty summary nouns unless they resolve locally.** Words such as "直觉", "本质", "核心", "机制", "逻辑", "图景", or "语义" must resolve to a concrete sentence immediately after they appear. Otherwise delete them.

22. **Cut AI cadence and stock scaffolding.** Avoid formulas such as "一方面……另一方面……", "从A到B", "先……再……最后……" when they are only rhythmic scaffolding. Avoid "X负责……Y负责……" unless responsibility is the actual structure being described.

23. **Keep Chinese-English typography tight.** Do not add AI-style visual padding around English words inside Chinese prose unless the text is a command, URL, exact syntax string, or copied literal.

24. **Reduce quotation marks.** Avoid quotation marks around ordinary terms, labels, or emphasis. Use them only for exact source text, UI text, citations, literal strings, or material under analysis.

25. **Reduce formatting noise.** Do not use backticks, bold, italics, or quotation marks as substitutes for sentence control. Let nouns and verbs carry the emphasis.

26. **Keep prose local and assertive.** Start each paragraph with the object, action, or claim it exists to describe. Remove warm-up sentences, recap sentences, transition padding, and commentary about the explanation itself.

27. **Prefer exact nouns over summary labels.** Replace words such as "这个东西", "这部分内容", "这个过程", "这块逻辑" with the exact function, field, file, event, request, record, proof object, or state transition.
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
- Narrator-from-a-distance or self-conscious setup? Remove it and state the subject directly.
- Meta-joiners ("The rest of this essay...")? Delete. Let the essay move.
- Chinese concept quotes around ordinary terms? Remove them unless they are source strings, exact wording, citations, Mermaid syntax, or code.
- Chinese sequence words everywhere? Keep "首先/其次/最后" only when the paragraph has a real ordered sequence.
- Chinese technical paragraph after code missing upstream/current/downstream context? Add the calling function, local mechanism, and consumed result.
- Technical metaphor hiding a real object? Replace it with the source type, field, function, or protocol step.
- Source-reading section jumps across modules without execution order? Rewrite it as caller -> callee -> return-to-caller.
- Long section relies on a glossary from many pages earlier? Add a local definition or precise back-reference.
- Protocol layer blurred? Name the layer: witness generation, AIR, PIOP, PCS, transcript, verifier, or recursion.
- Diagram arrows mean multiple things? Split the diagram or rewrite labels until every arrow has one meaning.
- Any line talking about the explanation instead of the subject? Delete it.
- Any line telling the reader what to notice, imagine, compare, or keep in mind? Delete it.
- Any vague structure word such as "调用链" or "时间线" without the explicit sequence? Replace it with the actual sequence.
- Any vague transport or compression verb such as "压成", "塞进", or "串起来"? Name the real operation.
- Any word such as "直觉", "核心", "本质", or "机制" without a concrete statement right after it? Delete it or complete it.
- Any AI-style spacing around English words inside Chinese prose? Remove it.
- Backticks around ordinary concepts or routine identifiers? Remove them unless the text needs exact syntax.
- Table where a paragraph or diagram would read better? Rewrite it.
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
