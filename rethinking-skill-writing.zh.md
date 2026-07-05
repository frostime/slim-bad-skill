---
title: "重新思考SKILL写作：为什么很多SKILL在今天其实很“烂”"
language: "zh-CN"
source: "rethinking-skill_from-workflow-to-contract-blog.docx"
---

前几天，我在整理一个叫作 `arrogant-objectivist` 的 SKILL。它的用途很简单：收到外部评审、审查意见或反馈时，不被对方的语气、身份和权威带着走，先看论证本身是否成立。

我Vibe出来了一个核心 Prompt，然后丢给 GPT，本来只想着帮我加个 frontmatter 就好，结果他擅自帮我一通“优化”，拿到成品之后瞬间血压飙升。

## 一、两个版本，你觉得哪一个更好？

我弄出来两个版本。为了不让篇幅失控，这里只截取最能说明问题的部分。

Ver A：

```text
## First Principle

Distrust the source; obey the argument.

- Arrogance applies to the source: external claims must earn acceptance.
- Objectivity applies to the truth: once an argument closes in the actual
  context, update without defending the existing design.

## License to Be Arrogant

Suspend arrogance until the current assumptions, scope, constraints,
excluded alternatives, and reasons for exclusion are understood.

## Feedback Classification

Convincing → fully update.
Valid insight, incompatible proposal → preserve the insight and adapt.
Valid but out of scope → reject for an explicit scope reason.
Noise → discard.
```

Ver B ：

```text
## Evaluation Procedure

1. Remove social metadata.
2. Extract the claim, premises, causal chain, context, and proposed action.
3. Reconstruct the strongest reasonable interpretation.
4. Test observation, diagnosis, principle, and implementation separately.
5. Check scope, lifecycle, compatibility, maintenance, migration, and recovery.
6. Assign a classification.

## Decision Discipline
## Output Format
## Communication Rules
...
```

只看单句，Ver B 几乎挑不出错。去掉社会压力、区分现象和诊断、检查生命周期、明确不确定性——这些都很正确，甚至显得比 Ver A 更严谨。

但我的判断很极端：Ver A 是优秀的，Ver B 是垃圾。

原因并不是我偏爱短文，也不是多写几百个 token 就犯了什么原罪。真正的问题是：Ver A 定义了这项任务的判断原则、适用边界和决策结果；Ver B 则把一个有能力的 Agent 本来可以自行完成的思考过程，拆成了必须表演一遍的标准动作。两者看起来只差一些段落，但差别是：前者规定什么必须成立；后者却约束了 Agent 必须以什么姿势抵达目的地。

## 二、「×」写作洁癖，「√」执行 SKILL 的模型变了

Agent Skills 是 2025 年 10 月才正式发布的，12 月才成为开放标准。按技术产品的年龄算，它甚至还没有走出婴儿期。[1]

但有趣的地方也正在这里：SKILL 很新，它依赖的能力假设却已经开始变旧 —— 原因是，在这半年里，模型走过了一个重要的能力阈值。

SKILL 诞生时，前沿模型当然已经会写代码、调用工具、执行多步任务。可它们在长程任务里仍然很容易迷路。2025 年 11 月，Anthropic 还在专门讨论如何用初始化 Agent、进度文件和显式任务清单，让模型跨上下文窗口持续工作。[2] 换句话说，当时的 Agent 像一个能力很强、但记性和持续性都不稳定的执行者。你最好把路标插得密一点。

所以，「先理解、再计划、再执行、最后验证」这类 workflow 并不愚蠢。它是那个阶段很合理的脚手架。

问题是，过去半年多，模型能力不是沿着一条平缓曲线慢慢挪动。从长程编码到复杂知识工作，前沿模型开始更稳定地理解目标、选择工具、检查自己的工作，并在没有人逐步牵引的情况下持续推进。OpenAI 在 2026 年 2 月描述 Codex 的长程任务时，已经把工作方式概括为：用户在里程碑处 steering，而不是逐行 micromanage；到了 GPT-5.5，官方进一步强调模型能更早理解任务、需要更少指导、更有效地使用工具、检查工作并继续推进。[3][4]

我说的阈值，并不是某条 benchmark 曲线突然出现了数学断点，更多是工程意义上的：过去必须由人类写进 prompt 或 SKILL 的脚手架，今天开始能由模型自己生成、修正和验证。

```text
跨越阈值之前：
Agent 会执行你给出的路线
→ Workflow 是能力补丁

跨过阈值之后：
Agent 能自己寻找、修正和验证路线
→ 同一套 Workflow 可能变成能力上限
```

这时，举证责任应该反过来。过去我们问：为什么不把步骤写清楚？现在更应该问：为什么这一步必须由 SKILL 写死？

## 三、一次跑通——也仅仅只能证明这个路径能跑通

很多（我个人视角下）新时代的垃圾 SKILL 的诞生过程其实很自然。作者先成功做完一次任务，然后把过程复盘出来：第一步列目录，第二步逐个读取文件，第三步抽取 frontmatter，第四步合并，最后检查数量。

这条路线可能没有任何问题。但它最多证明：在当时的环境、工具和判断下，这样做能成功。它并没有证明未来每一个 Agent 都应该照着走。

```text
这条路径成功过
        ↓
这条路径值得被记录
        ↓
未来 Agent 必须遵循这条路径 -> ARE YOUR SURE?
```

真正可疑的是最后一跳。一次成功案例里，至少混着三种东西：任务成功不可缺少的条件、当前环境客观存在的接口事实，以及作者当时恰好选择的策略。前两类通常值得写进 SKILL；第三类默认只是一段历史。

但 Markdown 列表会把这三类东西压成同一种语气。当我们写下 `1、2、3、4`，它天然会暗示：这些项目是完整的，而且顺序是有意义的。作者也许只是在回忆几个可能的动作，Agent 读到的却是一条封闭 pipeline。

这很像官僚系统里的表格：一旦表格定义了要勾哪些框，执行者就获得了一条免责路线。框都勾完了，流程就算走完；至于问题有没有真正解决，反而变成次要的。

在写这个文章之前，我甚至练就了一个条件反射：如果看到 SKILL.md 里出现了一堆 Markdown 列表，本能就开始犯恶心。

为啥？—— 因为列表最大的危险，是它很容易把“我想到的几件事”传递成“世界只有这几件事”，进而扼杀了比你更聪明的Agent给出更优路径的可能性。

## 四、SKILL 应该保存的，不是路线，而是契约

如果不再把一次 workflow 当成规范，那么 SKILL 里究竟该留下什么？

我现在更愿意把它分成两层。第一层是核心契约：这项任务到底是什么，什么行为算正确，哪些边界不能越过，什么结果意味着成功或失败。拿前面的反馈审查 SKILL 来说，“怀疑信源、服从论证”就是核心契约；如果论证在真实约束下闭合，就必须更新，而不能为了面子维护原方案。

第二层是支撑契约。它不定义任务本身，却让核心契约能在现实环境里执行、验证、交付或被别人消费。命令参数、输出 schema、必须出现的报告字段、高风险操作门禁、审计要求、某些 checklist，都可能属于这一层。

别误会——我不是说 output format、checklist 或操作步骤这些东西就一定要归类为“坏东西”。其实同一种形式，在不同场景里可能完全不同。

如果下游系统真的依赖固定 JSON，格式就是契约；如果用户需要 `Valid core / Failure / Decision` 来审查结论，这几个字段也有真实价值。反过来，如果固定标题只是作者觉得“报告应该长这样”，那它就只是仪式。

> 判断一段内容该不该留下，不能看它长得像流程、格式还是 checklist；要看它到底服务了什么真实需求。

于是，真正该删的不是“核心以外的一切”，而是既不构成核心契约，也没有为核心提供必要支撑的内容：重复解释、可以轻易推导的结论、无因果必要性的步骤、只为显得完整而增加的章节，以及把一般能力重新念一遍的废话。

## 五、当然，我不是在反对所有流程

这个观点很容易被推到另一个极端：既然强 Agent 会自己规划，那 SKILL 只写一句目标不就行了？不行。只写结果，同样会制造漏洞。

例如，把成功定义成“所有测试通过”，模型完全可能删掉失败测试、放宽断言，或者只运行最容易通过的那一部分。开放策略空间，不等于把正确性定义也一起开放。

工具封装型 SKILL 也经常需要大量具体操作。一个 `read-pdf` SKILL 若规定页码从 1 开始、输出路径从 `Agent log` 读取、扫描页需要渲染而不能只信 Markdown，这些都不是人类对思考过程的偏好，而是接口事实和能力边界。Agent 再聪明，也不能自行发明不存在的命令。

所以真正的分界从来不是“有没有 workflow”，而是这条 workflow 的约束力来自哪里：来自真实接口、因果顺序、安全风险和外部消费者，它就应该严格；只来自作者曾经这么做过，它就没有资格成为未来 Agent 的纪律。

## 六、一个真正的范式的迁移

SKILL 才出现半年多，按理说不该这么快就谈“旧时代”。但没办法，执行它的模型变化得比规范本身快。某条指令在去年可能是必要脚手架，今天可能只是提醒，明天则可能变成妨碍模型发挥的硬约束。

```text
同一条指令的生命周期：

必要脚手架
→ 有帮助的提示
→ 无效冗余
→ 有害约束
```

这也是为什么复杂 SKILL 的优化，不能只在原地逐句删字。有时问题就在章节结构本身：核心原则散落在多个位置，支撑契约压过了任务本身，示例被写成规则，多个 checklist 反复枚举同一件事。此时应该允许大幅重排、合并甚至重写。

当然啦，“大改”不意味着 Agent 擅自改写任务定义。如果Agent准备重建章节和逻辑，应该先向用户说明：你认为核心契约是什么，当前结构哪里出了问题，准备怎样重组，哪些内容会被保留、移动或删除。让用户先审查方向，再动刀。

说到底，强 Agent 时代不是取消人的控制，而是把控制放回正确的位置：人定义任务、边界和验收；模型负责在这个空间里寻找更好的路径。

> 模型跨过能力阈值之后，过程约束不再享有默认正当性。任何限制 Agent 策略空间的规则，都应该证明它来自任务、环境或风险，而不是来自作者曾经跑通过的一条路线。

所以我现在看到一份又长又完整的 SKILL，不会先问它是不是写得足够细。我会先问：删掉这些步骤之后，Agent 真的会做错吗？

如果不会，那么它们大概从来就不属于这份 SKILL。

—— 跑通不等于规范。新的时代，人类应该停止注入哪些手工作坊的经验。裁定什么是对什么是错，才是真正属于人的责任。

## 参考资料

- [1] Anthropic, “Equipping agents for the real world with Agent Skills,” 2025-10-16；页面记录 2025-12-18 发布开放标准。 原文
- [2] Anthropic, “Effective harnesses for long-running agents,” 2025-11-26。 原文
- [3] OpenAI, “Run long horizon tasks with Codex,” 2026-02-23。 原文
- [4] OpenAI, “Introducing GPT-5.5,” 2026-04-23；GPT-5.5 System Card。 原文
