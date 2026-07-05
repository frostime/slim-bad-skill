---
name: slim-bad-skill
description: Use this skill when the user explicitly considers an existing SKILL.md bloated, mechanical, list-heavy, workflow-driven, or over-prescriptive and wants it substantially simplified without losing real capability. Recover the skill's core contract, validate the supporting contracts required by its actual use case, and remove accidental process, redundant derivations, false closed sets, and author preference presented as necessity. This is a repair skill, not a general SKILL-writing standard or blanket terseness pass.
---

# Slim Bad Skill

Repair an existing skill that the user considers poorly written. Preserve the contracts that make it correct and usable; remove structure and text that add no independent value.

## Scope

This is a **repair pass**, not a general authoring standard.

Do not redesign the underlying domain strategy unless the user asks. Do not assume operational detail is bloat: tool adapters and script wrappers may require exact commands, parameter semantics, path resolution, output protocols, error behavior, and causal sequences.

The repair may be local or structural. Preserve the existing organization only when it still expresses the skill's contracts clearly.

## First Principle

**A SKILL constrains required behavior, not the cognitive path used to produce it.**

Assume a capable 2026 Agent can understand ordinary tasks, derive common implications, decompose work, choose tools, and recover from routine errors. A skill should add missing knowledge and necessary control, not restate generic intelligence.

Do not disguise one human-imagined execution route as the task specification. Constrain what must be true while leaving implementation strategy open wherever the task permits it.

## Contract Model

Evaluate content by the role it serves.

| Role | Meaning | Removal test |
|---|---|---|
| **Core contract** | Defines the task, its boundaries, and what counts as correct behavior. | Removal changes the skill's identity or correctness semantics. |
| **Supporting contract** | Makes the core reliably executable, verifiable, deliverable, reviewable, or consumable in its actual environment. | Removal leaves the task definition intact but materially weakens correct use. |
| **No independent contract value** | Repeats, derives, narrates, or over-directs without protecting the core or a real supporting need. | Removal causes no material loss. |

Core contracts often include governing principles, domain rules, invariants, and success or failure boundaries.

Supporting contracts may include tool interfaces, output fields, schemas, checklists, intermediate artifacts, workflow gates, communication constraints, or validation procedures. These forms are not inherently good or bad. Their value depends on the concrete requirement they serve.

Do not classify content by section name or surface form. The same output format, checklist, workflow, or explanation may be core, supporting, or unnecessary in different skills.

## Repair Strategy

### 1. Recover the core contract

Identify the smallest coherent statement of:

- what task the skill governs;
- what behavior or result it requires;
- which boundaries distinguish correct from incorrect execution.

If the current text expresses the same contract repeatedly, preserve the strongest formulation and remove its derivations.

### 2. Validate supporting contracts

For each remaining constraint, determine what concrete need it serves.

Preserve it when removing it would materially increase the chance that a capable fresh Agent would:

- lack non-obvious domain or interface knowledge;
- violate a real dependency, exception, invariant, or stop boundary;
- misuse a capability or its input/output protocol;
- produce superficially acceptable work that violates the actual intent;
- lose evidence, structure, coordination, or compatibility required by the user or an external consumer.

Otherwise remove it, merge it into a stronger rule, or move conditional detail into `references/`.

When a potentially material supporting contract depends on use-case information absent from the text, confirm its purpose with the user before removing, weakening, or reinterpreting it. Do not interrupt for obvious duplication or changes that are semantically lossless.

### 3. Choose the appropriate edit scale

Use local edits when the existing structure already reflects the recovered contract.

Use a structural rewrite when clarity requires substantial reordering, consolidation, section replacement, or re-expression of the governing logic. Do not preserve a bad structure merely to minimize the diff.

Before applying a substantial structural rewrite, report:

- the recovered core contract;
- the main structural defects;
- the proposed organization;
- the consequential material to preserve, move, merge, or remove;
- the reason the larger change is preferable and any material risk.

Obtain user approval before applying the rewrite unless the user has already explicitly authorized substantial restructuring.

## Contract vs. Author Preference

Preserve real contracts such as command and schema semantics, externally required outputs, causal ordering, safety gates, domain constraints, and testable acceptance or recovery conditions.

Challenge content such as a generic understand → analyze → plan → execute → validate workflow, one convenient implementation route presented as mandatory, fixed reasoning stages, repeated implications, or scaffolding that substitutes the author's preferred thinking style for Agent judgment.

These are illustrative examples, not a closed taxonomy. The distinction depends on what requirement the instruction serves.

## Lists and Closure

Use a closed list only when its semantics are genuinely closed:

- an exhaustive set of valid states or categories;
- requirements that must all be satisfied;
- a sequence whose order is causally necessary.

Heuristics, examples, common cases, and possible methods are open by default. Mark them as illustrative or rewrite them so they cannot be mistaken for a complete set.

Do not number unordered material merely for presentation. Numbering implies sequence or priority and can manufacture a workflow that does not exist.

## Delivery

Deliver the revised skill as the primary result.

Keep commentary limited to material ambiguity, non-obvious supporting contracts, consequential removals, and approved structural changes. Do not produce a line-by-line defense of obvious edits unless the user asks.

The revision passes when a capable fresh Agent can identify:

- the core contract;
- the supporting contracts required by the real use case;
- what constitutes success or failure;
- where implementation freedom remains.

Do not solve procedural overreach by reducing the skill to a vague outcome. Preserve the contracts needed to prevent misuse, literal compliance, specification gaming, or unverifiable success.

When the contract distinction is unclear, read `references/minimal-vs-bloated.md`.
