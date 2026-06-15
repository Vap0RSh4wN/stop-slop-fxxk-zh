# Structures to Avoid

## Binary Contrasts

These create false drama. State the point directly.

| Pattern | Problem |
|---------|---------|
| "Not because X. Because Y." / "Not because X, but because Y." | Telegraphed reversal |
| "[X] isn't the problem. [Y] is." | Formulaic reframe |
| "The answer isn't X. It's Y." | Predictable pivot |
| "It feels like X. It's actually Y." | Setup/reveal cliche |
| "The question isn't X. It's Y." | Rhetorical misdirection |
| "Not X. But Y." / "not X, it's Y" / "isn't X, it's Y" | Mechanical contrast |
| "It's not this. It's that." | Same formula, different words |
| "stops being X and starts being Y" | False transformation arc |
| "doesn't mean X, but actually Y" | Negation-then-assertion crutch |
| "is about X but not Y" | False distinction |
| "not just X but also Y" | Additive hedge |

**Instead:** State Y directly. "The problem is Y." "Y matters here." Drop the negation entirely.

## Negative Listing

Listing what something is *not* before revealing what it *is*. A rhetorical striptease.

| Pattern | Problem |
|---------|---------|
| "Not a X... Not a Y... A Z." | Dramatic buildup through negation |
| "It wasn't X. It wasn't Y. It was Z." | Same structure, past tense |

**Instead:** State Z. The reader doesn't need the runway.

## Dramatic Fragmentation

Sentence fragments for emphasis read as manufactured profundity.

| Pattern | Problem |
|---------|---------|
| "[Noun]. That's it. That's the [thing]." | Performative simplicity |
| "X. And Y. And Z." | Staccato drama |
| "This unlocks something. [Word]." | Artificial revelation |

**Instead:** Complete sentences. Trust content over presentation.

## Rhetorical Setups

These announce insight rather than deliver it.

| Pattern | Problem |
|---------|---------|
| "What if [reframe]?" | Socratic posturing |
| "Here's what I mean:" | Redundant preview |
| "Think about it:" | Condescending prompt |
| "And that's okay." | Unnecessary permission |

**Instead:** Make the point. Let readers draw conclusions.

## Formulaic Constructions

| Pattern | Problem |
|---------|---------|
| "By the time X, I was Y." | Narrative template |
| "X that isn't Y" | Indirect. Say "X is broken" |

## False Agency

Giving inanimate things human verbs. Complaints don't "become" fixes. Bets don't "live or die." Decisions don't "emerge." A person does something to make those things happen. AI loves this because it avoids naming the actor.

| Pattern | Problem |
|---------|---------|
| "a complaint becomes a fix" | The complaint did nothing. Someone fixed it. |
| "a bet lives or dies in days" | Bets don't have lifespans. Someone kills the project or ships it. |
| "the decision emerges" | Decisions don't emerge. Someone decides. |
| "the culture shifts" | Cultures don't shift on their own. People change behavior. |
| "the conversation moves toward" | Conversations don't move. Someone steers. |
| "the data tells us" | Data sits there. Someone reads it and draws a conclusion. |
| "the market rewards" | Markets don't reward. Buyers pay for things. |

**Instead:** Name the human. "The team fixed it that week" beats "the complaint becomes a fix." If no specific person fits, use "you" to put the reader in the seat.

## Narrator-from-a-Distance

Floating above the scene instead of putting the reader in it.

| Pattern | Problem |
|---------|---------|
| "Nobody designed this." | Disembodied observation |
| "This happens because..." | Lecturer voice |
| "This is why..." | Same |
| "People tend to..." | Armchair sociologist |

**Instead:** Put the reader in the room. "You don't sit down one day and decide to..." beats "Nobody designed this."

## Passive Voice

Every sentence needs a subject doing something. Passive voice hides the actor and drains energy.

| Pattern | Fix |
|---------|-----|
| "X was created" | Name who created it |
| "It is believed that" | Name who believes it |
| "Mistakes were made" | Name who made them |
| "The decision was reached" | Name who decided |

**Instead:** Find the actor. Put them at the front of the sentence.

## Sentence Starters to Avoid

| Pattern | Fix |
|---------|-----|
| Sentences starting with What, When, Where, Which, Who, Why, How | Restructure. Lead with the subject or the verb. |
| Paragraphs starting with "So" | Start with content |
| Sentences starting with "Look," | Remove |

Wh- openers become a crutch. "What makes this hard is..." becomes "The constraint is..." or better, name the specific constraint.

## Rhythm Patterns

| Pattern | Fix |
|---------|-----|
| Three-item lists | Use two items or one |
| Questions answered immediately | Let questions breathe or cut them |
| Every paragraph ends punchily | Vary endings |
| Em-dashes | Remove. Use commas or periods. No em dashes at all. |
| Staccato fragmentation | Don't stack short punchy sentences |
| "Not always. Not perfectly." | Hedging disguised as reassurance |

## Word Patterns

| Pattern | Problem |
|---------|---------|
| Lazy extremes (every, always, never, everyone, everybody, nobody) | False authority. Use specifics instead of sweeping claims. |
| All adverbs (-ly words, "really," "just," "literally," "genuinely," "honestly," "simply," "actually") | Empty emphasis. See phrases.md for full list. |

## Low-Information Sentences

These failures are broader than any fixed blacklist. Use the checks below to catch new AI-sounding wording before it settles into a draft.

### Four Information Slots

A sentence should usually reveal these items near the surface:

- object: what file, function, section, claim, proof step, review target, or artifact is being discussed
- action: what operation happens to that object
- result: what changes, appears, or becomes available after the action
- destination: who reads, uses, consumes, or depends on that result

If two or more slots are missing, the sentence often turns into posture, rhythm, or process-theater.

### Deletion Test

Delete the sentence and ask what disappears.

- If you lose an object, action, result, condition, or dependency, keep the sentence.
- If you lose only tone, transition, pacing, reassurance, or a vague sense of progress, cut it or fuse the real information into a nearby sentence.

### Verb Substitution Test

Swap the main verb with several neighbors.

- If `检查` can become `看一下`, `过一遍`, `带一下`, `收一遍`, `兜一下`, or `处理一下` with almost no meaning change, the sentence does not name the operation yet.
- Keep rewriting until changing the verb would change the actual work.

### Rewrite Frame

When a sentence fails the checks above, rewrite it with this frame:

`对象 -> 动作 -> 结果 -> 落点`

Examples:

- `这一节列出高风险句型，改稿时对照这里检查。`
- `我先检查这几处标题，再把修改写进README.md。`
- `references/examples.md`收录坏句子和对应改写，卡住时先对照这里。

## Chinese Technical Note Structures

Use these checks when editing Chinese source-reading notes, protocol notes, and engineering documentation.

| Pattern | Problem | Fix |
|---------|---------|-----|
| "不是 X，而是 Y" / "并非 X，而是 Y" | Mechanical contrast delays the claim. | State Y directly, then explain the mechanism. |
| "不只是 X，还 Y" | Additive hedge often hides the main role. | Name the roles separately if both matter. |
| "可以理解为 X" without returning to source objects | The simplified image may replace the real protocol object in the reader's head. | Explain the intuition, then map it back to the source variable, function, or proof claim. |
| "所谓 X" | Adds distance and weakens confidence. | Name X and define it. |
| Ordinary technical terms inside Chinese quotes | Makes every concept look provisional or slogan-like. | Remove quotes unless quoting source text, UI text, Mermaid syntax, code, or a citation. |
| Code excerpt followed by line-by-line paraphrase | Low signal; the reader can read the code. | Explain upstream caller, local mechanism, downstream consumer, and why this snippet changes the proof or execution state. |
| Formula mixed into Rust code fences | Confuses code with math. | Put formulas in Markdown LaTeX and keep Rust fences for real source code. |
| Sequence words before every paragraph | Creates artificial ordering. | Use "首先/其次/最后" only for actual ordered steps. |
| "目标很直接" / "核心原则" / "这版额外解决的问题" | The heading summarizes the writer's attitude instead of naming the object. | Turn the heading into the object, changed behavior, or review target: "这个版本会删掉的写法", "新增的中文写作约束", "安装步骤". |
| "`X`放Y" / "这一节讲X" / "这里写X" | Container verbs hide what the file or section actually contains. | Replace `放/讲/写` with `定义/列出/解释/对比/给出/收录`, then name the payload. |
| "`SKILL.md`放核心规则" / "`examples.md`放示例" | The sentence points to a location but not to the information or when to use it. | State payload plus use moment: "`SKILL.md`定义改写规则，改稿前先看这里" or "`references/examples.md`收录坏句子和对应改写，卡住时先对照这里". |
| "我先收一遍" / "这个直接落地" | The sentence reports pace or attitude instead of the actual operation. | Replace it with the real action: "我先检查这几处差异" or "我现在把这条规则补进SKILL.md和README". |

### Source-Reading Paragraph Shape

A strong Chinese technical paragraph after a code excerpt usually answers these questions without announcing them:

- Which caller or data object brought execution here?
- Which fields, variables, or claims does this layer create or transform?
- Which downstream function, proof, verifier step, or commitment consumes the result?
- If a simplified example appears, how does it map back to the real source object?
