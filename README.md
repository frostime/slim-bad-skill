# Rethinking SKILL Writing

这个仓库包含一篇关于 Agent SKILL 写作范式的文章，以及一个配套示例：`slim-bad-skill`。

核心观点：

> SKILL 不应该把一次跑通过的 workflow 固化成未来 Agent 必须遵守的路线。
> SKILL 更应该保存任务契约：目标、边界、验收标准、接口事实和必要风险约束。

## 内容

```text
.
├── rethinking-how-we-write-skill.md
├── skills/slim-bad-skill/
└── README.md
```

* `rethinking-how-we-write-skill.md`：文章《重新思考 SKILL 写作：为什么很多旧时代的 SKILL 其实很“烂”》
* `skills/slim-bad-skill/`：附带的 SKILL

## 简述

很多早期 SKILL 会把任务执行过程写成固定步骤：

```text
先做 A
再做 B
然后做 C
最后检查 D
```

这类 workflow 在模型能力较弱、长程执行不稳定时有价值。它提供脚手架，降低模型迷路的概率。

但当前更强的 Agent 已经能在很多任务中自行规划、选择工具、验证结果和修正路线。此时，如果 SKILL 继续写死大量非必要步骤，可能会限制 Agent 的策略空间，让它为了完成流程而不是完成任务。

问题不在于 workflow 本身，而在于：

> 这条 workflow 的约束力来自哪里？

如果约束来自真实接口、因果顺序、安全风险、外部消费者或验收标准，它应该保留。
如果约束只来自“作者曾经这样跑通过一次”，它不应该成为规则。

## `slim-bad-skill` 是什么

`slim-bad-skill` 是一个最小化示例，用来展示如何把一个臃肿、流程化、表演式的 SKILL 压缩成更接近“契约”的版本。

## 适用场景

这个思路更适合：

* Agent SKILL 设计
* Prompt / system instruction 精简
* 长程任务 agent 的任务契约设计
* 从 workflow 型提示迁移到 contract 型提示
* 删除“看起来严谨但没有真实约束力”的规则

不适合直接套用到所有场景。对于合规、医疗、法律、财务、数据迁移、不可逆操作等高风险任务，流程约束仍然可能是必要条件。
