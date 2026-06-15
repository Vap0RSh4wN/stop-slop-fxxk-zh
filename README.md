# Stop Slop 中文增强版

这是一个面向AI写作痕迹清理的技能。原始版本来自[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)。当前版本专门处理中文技术写作、源码阅读笔记、协议分析文档、工程说明文里的表达问题。

删除以下写法：空泛开场、机械转折、假深刻、被动语态、旁白式讲解、自言自语式过渡、第二人称指导、空结构词、空洞模糊词、AI常见句式、概念乱加引号、反引号滥用、中英文字之间的AI空格、短句乱断导致的句号过密、表格滥用、模糊动词掩盖真实操作。

## 适用场景

- 中文技术博客
- 源码阅读笔记
- 协议分析笔记
- 架构设计说明
- 需要降低AI痕迹的长文
- 需要把讲解改成作者式直写的文档

## 安装

选择一个环境，打开终端，复制对应命令执行。

### Codex

安装到 `~/.codex/skills/stop-slop`：

```bash
mkdir -p ~/.codex/skills && rm -rf ~/.codex/skills/stop-slop && git clone git@github.com:Vap0RSh4wN/stop-slop-fxxk-zh.git ~/.codex/skills/stop-slop
```

执行后开启新的Codex会话。如果Codex已经打开，结束当前会话后再开新会话。

### Claude Code

安装到 `~/.claude/skills/stop-slop`：

```bash
mkdir -p ~/.claude/skills && rm -rf ~/.claude/skills/stop-slop && git clone git@github.com:Vap0RSh4wN/stop-slop-fxxk-zh.git ~/.claude/skills/stop-slop
```

执行后开启新的Claude Code会话。如果Claude Code已经在运行，安装后重新开一个新会话。

### Cursor

安装到 `~/.cursor/skills/stop-slop`：

```bash
mkdir -p ~/.cursor/skills && rm -rf ~/.cursor/skills/stop-slop && git clone git@github.com:Vap0RSh4wN/stop-slop-fxxk-zh.git ~/.cursor/skills/stop-slop
```

执行后开启新的Cursor会话或新聊天。如果Cursor已经打开但没有立即识别到技能，重启Cursor后再开新聊天。

### 更新已安装版本

```bash
git -C ~/.codex/skills/stop-slop pull
git -C ~/.claude/skills/stop-slop pull
git -C ~/.cursor/skills/stop-slop pull
```

### 验证安装

```bash
ls ~/.codex/skills/stop-slop/SKILL.md
ls ~/.claude/skills/stop-slop/SKILL.md
ls ~/.cursor/skills/stop-slop/SKILL.md
```

安装完成后，在对应客户端的新会话里直接要求使用stop-slop即可。

## 中文写作约束

- 中文母语写作优先，不套英文修辞骨架
- 不写旁白，不写自言自语，不指导读者
- 不写“不是……而是……”这类机械转折
- 不写“调用链、时间线、这部分逻辑、这条链”这类空结构词
- 不写“事件桶、压成、落成、塞进、串起来”这类模糊动词
- 不写“收一遍、过一遍、直接落地”这类只交代推进感、不交代动作的状态词
- 不写“直觉、核心、本质、机制、逻辑”这类空总结词，除非后面立即落到具体对象
- 不乱加反引号和引号
- 不在中文和英文之间插入AI常见空格
- 不把每个短分句都断成句号
- 不默认用表格，结构和流向优先用图

## 如何判断新坏句子

词表只负责报警，不负责判定。真正的判定看句子有没有把信息写出来。

四个槽位：

- 对象：这一句在说什么文件、段落、函数、规则、改动或 proof object
- 动作：这一句到底做什么
- 结果：动作之后新增了什么信息或改动
- 落点：谁会用这个结果，或者结果落到哪里

两个测试：

- 删除测试：删掉这句以后，如果损失的只有节奏、态度、推进感，这句就该删。
- 动词替换测试：如果一个动词可以随便换成“收一遍、带一下、过一下、兜一下、顺一下”，句意几乎不变，这个动词就没有写出真实操作。

改写顺序如下：

`对象 -> 动作 -> 结果 -> 落点`

这套判据比黑名单更稳。就算以后冒出新的 AI 词，只要句子还在拿状态、姿态、节奏冒充信息，这里照样会把它拦下来。

## 目录里每个文件各自负责什么

```text
stop-slop/
├── SKILL.md
├── references/
│   ├── phrases.md
│   ├── structures.md
│   └── examples.md
├── README.md
└── LICENSE
```

`SKILL.md`定义改写时要遵守的规则，`references/phrases.md`列出高风险短语，`references/structures.md`整理高风险句型，`references/examples.md`收录坏句子和对应改写。

## 中文技术笔记里常见的坏句子

### 例 1：旁白式开场

反面：

> 下面我们先来看这一部分的核心逻辑。

改写：

> 这一部分先处理列方向折叠，再把结果交给下一层验证。

问题在于整句先讲讲解动作，没有先讲对象；“下面”只是表面信号。

### 例 2：机械转折

反面：

> 这里不是在验证原始列值，而是在验证折叠后的 opening claim。

改写：

> 这里验证的是折叠后的opening claim，不再直接验证原始列值。

句子一开头就应给出正面断言，不需要先否定再揭示。

### 例 3：空结构词

反面：

> 接下来把这条调用链压成一个更清晰的时间线。

改写：

> 顺序是 `commit_multilinears -> commit_multilinear -> commit_mles`。

“调用链”“时间线”“这条链”都不是内容。内容是实际顺序。

### 例 4：模糊动词

反面：

> Jagged把这些列值压成一个总claim，再喂给下一层。

改写：

> Jagged先用列方向随机点把这些列值折成一个标量claim，再把这个claim交给下一层PCS证明。

“压成”“喂给”都没有写出真实操作。

### 例 5：空总结词

反面：

> 这里的核心是一个直觉：它本质上是在做压缩。

改写：

> 这里把多个列值按随机权重折成一个标量，因此验证对象从多列opening变成一个opening claim。

“核心”“直觉”“本质上”本身不解释任何东西。

### 例 6：读者指导句

反面：

> 你可以把它理解成一个事件桶。

改写：

> 这个结构收集的是执行阶段产生的事件记录，后面会被整理成trace列。

不要把说明文写成讲解员对读者说话。

### 例 7：标点滥用

反面：

> SKILL.md放核心规则。references/phrases.md记录短语层面的检查清单。references/structures.md记录结构层面的常见问题。examples.md保留原版示例。

改写：

> `SKILL.md`定义改写规则，`references/phrases.md`列出短语层面的高风险位置，`references/structures.md`整理常见坏句型，`references/examples.md`收录坏句子和对应改写。

这些分句属于并列列举。中文里优先用逗号；并列项更长、内部已有逗号时，再考虑分号。不要为了制造停顿把每个短分句都断成句号。

### 例 8：AI常见空格

反面：

> 这个 proof 会在 verifier 侧继续检查。

改写：

> 这个proof会在verifier侧继续检查。

中英文混排需要看语义，不需要按AI默认节奏机械留白。

### 例 9：自我概括型标题

反面：

> ## 这版额外解决的问题

改写：

> ## 这个版本新增的中文写作约束

标题要直接写这一节的对象，不能先写作者对这一节的概括。

### 例 10：文件说明句只说位置不说内容

反面：

> `SKILL.md`放核心规则，`examples.md`放示例。

改写：

> `SKILL.md`定义改写时要遵守的规则，`references/examples.md`收录坏句子和对应改写。

文件说明句要写清文件承载什么信息，读者为什么要看它。

### 例 11：状态词冒充动作

反面：

> 我先收一遍，再直接落地。

改写：

> 我先检查这几处标题和说明句，再把改动写进`SKILL.md`和`README.md`。

句子要写真实动作，不能只写一种“我在推进”的感觉。

### 例 12：删掉后几乎不损失信息

反面：

> 这里我先兜一下整体思路。

改写：

> 这一节先列出三个检查点：标题、文件说明句、检查命令。

删掉前一句，信息几乎不损失；删掉后一句，这一节到底列什么就没了。

### 例 13：动词换一批近义词，句意几乎不变

反面：

> 我再带一下 README 这一段。

改写：

> 我再重写 README 里安装说明后面的两段，把标题改成对象名，把说明句改成文件承载的信息。

“带一下”可以随便换成“过一下、顺一下、收一下、兜一下”；“重写”不能。前一类词只在交代推进感。

### 例 14：列表前先摆姿态

反面：

> 这个版本专门删这些写法：

改写：

> 删除以下写法：

列表前面直接写列表内容，不要先写作者姿态。

## 先抓高风险位置的命令

```bash
rg -n '不是|而是|首先|其次|最后|综上|本文|本次分享将|原笔记|建议关注|学习主线|调用链|时间线|直觉|核心|本质|机制|目标很直接|这版额外解决的问题|核心原则|这一节讲|这里讲|这里放|收一遍|过一遍|直接落地|兜一下|带一下' <file>
rg -n '[“”‘’]|所谓|可以理解为|换句话说|本质上|非常|其实|值得注意|需要注意|真正|完全|只需要|就能|也就是|事件桶|压成|落成|塞进|串起来|放核心规则|放示例' <file>
```

这些命令不是自动判错器，只会先标出高风险位置，后面仍然要人工判断。

真正的判定还是回到上面的四个槽位和两个测试：对象、动作、结果、落点；删除测试；动词替换测试。

## 来源和授权

本项目fork并改写自[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)。基础思想、初始技能结构、英文AI写作清理规则来自原项目。本版本补入了中文技术笔记规则、中文短语清单、中文结构清单、中文标点建议、安装说明和作者式写法规则。

原项目使用MIT License。本项目继续保留MIT License。
