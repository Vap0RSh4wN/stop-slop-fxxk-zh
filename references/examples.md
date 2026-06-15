# Before/After Examples

## English Examples

### Example 1: Throat-Clearing + Binary Contrast

**Before:**
> "Here's the thing: building products is hard. Not because the technology is complex. Because people are complex. Let that sink in."

**After:**
> "Building products is hard. Technology is manageable. People aren't."

**Changes:** Removed opener, binary contrast structure, and emphasis crutch.

---

### Example 2: Filler + Unnecessary Reassurance

**Before:**
> "It turns out that most teams struggle with alignment. The uncomfortable truth is that nobody wants to admit they're confused. And that's okay."

**After:**
> "Teams struggle with alignment. Nobody admits confusion."

**Changes:** Cut hedging, opener, and permission-granting ending.

---

## Chinese Technical Writing Examples

### Example 3: Narrator Voice

**Before:**
> 下面我们先来看这一部分的核心逻辑。

**After:**
> 这一部分先处理列方向折叠，再把结果交给下一层验证。

**Changes:** Removed narrator setup and moved straight to the mechanism.

---

### Example 4: Mechanical Contrast

**Before:**
> 这里不是在验证原始列值，而是在验证折叠后的opening claim。

**After:**
> 这里验证的是折叠后的opening claim，不再直接验证原始列值。

**Changes:** Stated the positive claim directly instead of using a negation-first turn.

---

### Example 5: Vague Structure Labels

**Before:**
> 接下来把这条调用链压成一个更清晰的时间线。

**After:**
> 顺序是 commit_multilinears -> commit_multilinear -> commit_mles。

**Changes:** Replaced empty structure words with the actual sequence.

---

### Example 6: Vague Verbs

**Before:**
> Jagged把这些列值压成一个总claim，再喂给下一层。

**After:**
> Jagged先用列方向随机点把这些列值折成一个标量claim，再把这个claim交给下一层PCS证明。

**Changes:** Replaced blurry transport verbs with the actual reduction and handoff.

---

### Example 7: Empty Summary Words

**Before:**
> 这里的核心是一个直觉：它本质上是在做压缩。

**After:**
> 这里把多个列值按随机权重折成一个标量，因此验证对象从多列opening变成一个opening claim。

**Changes:** Removed empty summary nouns and named the actual transformation.

---

### Example 8: Reader Coaching

**Before:**
> 你可以把它理解成一个事件桶。

**After:**
> 这个结构收集执行阶段产生的事件记录，后面会被整理成trace列。

**Changes:** Removed second-person coaching and named the source object.

---

### Example 9: Punctuation Over-Splitting

**Before:**
> SKILL.md放核心规则。references/phrases.md记录短语层面的检查清单。references/structures.md记录结构层面的常见问题。references/examples.md保留示例。

**After:**
> SKILL.md放核心规则，references/phrases.md记录短语层面的检查清单，references/structures.md记录结构层面的常见问题，references/examples.md保留示例。

**Changes:** Tight parallel clauses use commas instead of a chain of short full stops.

---

### Example 10: Chinese-English AI Spacing

**Before:**
> 这个 proof 会在 verifier 侧继续检查。

**After:**
> 这个proof会在verifier侧继续检查。

**Changes:** Removed mechanical bilingual spacing.

---

### Example 11: Summary Heading Instead of Object

**Before:**
> ## 这版额外解决的问题

**After:**
> ## 这个版本新增的中文写作约束

**Changes:** Replaced a self-summarizing heading with a heading that names the actual content.

---

### Example 12: Container Verb in File Description

**Before:**
> SKILL.md放核心规则，references/examples.md放示例。

**After:**
> `SKILL.md`定义改写时要遵守的规则，`references/examples.md`收录坏句子和对应改写。

**Changes:** Replaced the vague verb "放" with exact document actions and named the payload in each file.

---

### Example 13: Status Word Instead of Action

**Before:**
> 我先收一遍，再直接落地。

**After:**
> 我先检查这几处标题和说明句，再把改动写进`SKILL.md`和`README.md`。

**Changes:** Replaced progress-report wording with the actual operations.

**Diagnostic:**
- object missing in the first version
- action replaced by progress-report wording
- result and destination both absent

**Rewrite frame:** object -> action -> result -> destination

---

### Example 14: Deletion Test

**Before:**
> 这里我先兜一下整体思路。

**After:**
> 这一节先列出三个检查点：标题、文件说明句、检查命令。

**Changes:** The original sentence only staged the explanation. Deleting it lost no real information. The rewrite names the actual section payload.

**Diagnostic:**
- deleting the first sentence loses only pacing
- the rewrite makes deletion costly because the three objects disappear

---

### Example 15: Verb Substitution Test

**Before:**
> 我再带一下 README 这一段。

**After:**
> 我再重写 README 里安装说明后面的两段，把标题改成对象名，把说明句改成文件承载的信息。

**Changes:** The original verb could be swapped with many vague neighbors. The rewrite names the exact edit scope and operation.

**Diagnostic:**
- `带一下` could be replaced by `过一下`, `顺一下`, `看一下`, `收一下`
- `重写` cannot be swapped out without changing the work itself

---

### Example 16: List Intro Framed by Posture

**Before:**
> 这个版本专门删这些写法：

**After:**
> 删除以下写法：

**Changes:** Removed the writer-facing setup and named the list payload directly.

**Diagnostic:**
- the original line only staged the list
- the rewrite tells the reader what the list contains in four characters

---

### Example 17: Rule Explanation Written as Praise

**Before:**
> 这套判据比黑名单更稳。就算以后冒出新的 AI 词，只要句子还在拿状态、姿态、节奏冒充信息，这里照样会把它拦下来。

**After:**
> 黑名单只能覆盖已经列出的词。四个槽位、删除测试、动词替换测试直接检查句子有没有写出对象、动作、结果、落点；词变了，只要这些信息仍然缺失，这里仍然会把它判成低信息句。

**Changes:** Replaced praise and metaphor with the actual coverage condition and decision rule.

**Diagnostic:**
- `更稳` only evaluates, it does not explain
- `冒出` and `拦下来` are scene-building verbs, not criteria
- the rewrite names the boundary: listed words may change, missing information does not
