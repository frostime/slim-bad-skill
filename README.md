# Rethinking SKILL Writing

[README|中文](README.zh-CN.md)

This repository contains an article on the Agent SKILL writing paradigm, plus a companion example: `slim-bad-skill`.

Core thesis:

> A SKILL should not freeze a one-time successful workflow into a route every future Agent must follow.
> A SKILL should preserve the task contract: goal, boundaries, acceptance criteria, interface facts, and necessary risk constraints.

## Contents

```text
.
├── rethinking-skill-writing.en.md
├── rethinking-skill-writing.zh.md
├── skills/slim-bad-skill/
└── README.md
```

* `rethinking-skill-writing.en.md` / `rethinking-skill-writing.zh.md`: Article — "Rethinking SKILL Writing: Why Many Old-Style SKILLs Are Actually Bad"
* `skills/slim-bad-skill/`: The accompanying SKILL

## Overview

Many early SKILLs describe task execution as fixed steps:

```text
Do A first
Then do B
Then do C
Finally check D
```

This kind of workflow had value when models were weaker and long-horizon execution was unstable. It provided scaffolding, reducing the chance the model would get lost.

But today's more capable Agents can plan, choose tools, verify results, and correct their own course in many tasks. When a SKILL still hardcodes large amounts of non-essential steps, it may restrict the Agent's strategy space, causing it to serve the process rather than the task.

The problem is not workflow itself. The problem is:

> Where does the binding force of this workflow come from?

If the constraint comes from real interfaces, causal order, security risks, external consumers, or acceptance criteria, it should stay.
If the constraint comes only from "the author once succeeded this way," it has no right to become a rule.

## What Is `slim-bad-skill`

`slim-bad-skill` is a minimal example showing how to compress a bloated, procedural, performative SKILL into a version closer to a "contract."

## Applicability

This mindset fits:

* Agent SKILL design
* Prompt / system-instruction trimming
* Task-contract design for long-horizon agents
* Migrating from workflow-style prompts to contract-style prompts
* Removing rules that "look rigorous but carry no real binding force"

It is **not** a universal template. For compliance, medical, legal, financial, data-migration, irreversible, or other high-risk tasks, process constraints may still be necessary.
