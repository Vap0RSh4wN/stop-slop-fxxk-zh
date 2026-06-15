# Stop Slop 中文增强版

这是一个面向AI写作痕迹清理的Codex/LLM技能。它的基础思想和初始结构fork自[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)，在此基础上加入了中文技术笔记、源码阅读笔记、协议分析文档的写作规则，以及整理中文底层技术笔记时沉淀出的风格约束。

原版stop-slop关注英文AI写作里的套路表达，例如空泛开场、机械转折、夸张短句、假深刻、被动语态和过度强调。这个版本保留这些思想，并补充中文场景里更常见的问题：概念被引号包起来、不是……而是……式转折、首先/其次/最后的滥用、源码解释只做逐行翻译、公式和代码块混在一起、例子停留在模糊层面而没有回到真实工程对象。

## 适用场景

- 中文技术博客、源码阅读笔记、协议分析笔记
- 编译器、系统、数据库、工程架构等需要准确表达的长文
- 需要减少AI感、减少概念引号、减少空泛连接词的中文稿件
- 需要在代码片段后解释上游、本层、下游关系的文档
- 需要把旁白式讲解改成作者式直写的说明文

## 技能结构

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

SKILL.md放核心规则。references/phrases.md记录短语层面的检查清单。references/structures.md记录结构层面的常见问题。examples.md保留原版示例。

## Quick start

选择环境，打开终端，复制一条命令执行。

### Codex

安装到 `~/.codex/skills/stop-slop`：

```bash
mkdir -p ~/.codex/skills && rm -rf ~/.codex/skills/stop-slop && git clone git@github.com:Vap0RSh4wN/stop-slop-fxxk-zh.git ~/.codex/skills/stop-slop
```

执行后开启新的Codex会话。如果Codex已经打开，结束当前会话后重新开一个新的。

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

如果技能已经存在，直接拉取最新版本：

```bash
git -C ~/.codex/skills/stop-slop pull
git -C ~/.claude/skills/stop-slop pull
git -C ~/.cursor/skills/stop-slop pull
```

### 验证安装

确认入口文件存在：

```bash
ls ~/.codex/skills/stop-slop/SKILL.md
ls ~/.claude/skills/stop-slop/SKILL.md
ls ~/.cursor/skills/stop-slop/SKILL.md
```

安装完成后，在对应客户端的新会话里直接要求使用stop-slop即可。

## 中文增强内容

### 1. 中文技术笔记规则

新增Chinese Technical Notes小节，用于约束中文源码阅读笔记和协议分析文档：

- 机制直接写，少用本质上、真正、核心、非常、其实这类弱表达。
- 首先、其次、最后可以用于真实顺序，不能变成每段默认节奏。
- 普通技术概念不加中文引号或双引号，源码字符串、UI文本、直接引用、Mermaid语法和代码除外。
- 公式使用Markdown LaTeX，源码块只放真实源码或字面示例。
- 源码片段之后解释上一跳、本层变换、下一跳，不做低信号复述。
- 段落默认写成作者式直述，不写旁白，不教读者怎么看。

### 2. 中文短语检查

references/phrases.md加入了中文检查目标，例如：

```text
本文
本次分享将
值得注意的是
需要注意的是
简单来说
换句话说
可以理解为
本质上
核心
真正
非常
其实
只需要
就能
也就是
```

这些词不是绝对禁用。审稿时把它们当作信号：如果句子能写成具体函数、字段、claim、proof step或工程对象，就删掉弱表达。

### 3. 中文结构检查

references/structures.md加入了中文技术文档常见结构问题：

- 不是X，而是Y：直接写Y，再解释机制。
- 不只是X，还Y：分别写清两个角色。
- 可以理解为X：解释后必须映射回源码变量、函数或proof claim。
- 所谓X：直接定义X。
- 普通概念加引号：删掉引号。
- 代码后只逐行复述：改成解释调用方、本层变换、下游消费。
- 公式混进Rust代码块：公式放LaTeX，Rust块保留真实源码。
- 调用链、时间线、这部分逻辑、这条链这类空结构词：改成具体顺序或具体对象。

### 4. 写法姿态

这个版本额外强调：

- 不写旁白式句子
- 不写自言自语式过渡
- 不使用第二人称指导读者
- 少用反引号和引号
- 少用表格，流程和依赖关系优先画图
- 避免事件桶、压成、落成、塞进、串起来这类模糊动词

## 推荐检查命令

中文技术文档可以先跑这些检查，再人工判断是否需要修改：

```bash
rg -n '不是|而是|首先|其次|最后|综上|本文|本次分享将|原笔记|建议关注|学习主线|调用链|时间线|直觉' <file>
rg -n '[“”‘’]|所谓|可以理解为|换句话说|本质上|非常|其实|值得注意|需要注意|核心|真正|完全|只需要|就能|也就是|事件桶|压成|落成|塞进|串起来' <file>
```

序列词有真实顺序时可以保留。源码字符串、Mermaid节点、直接引用、代码片段里的引号也可以保留。

## 来源和授权

本项目fork并改写自[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)。基础思想、初始技能结构、英文AI写作清理规则来自原项目。中文技术笔记规则、中文短语清单、中文结构清单、安装说明和作者式写法规则为本版本新增内容。

原项目使用MIT License。本项目继续保留MIT License。
