# Contract-First Skill Repair

This example concerns a skill for evaluating external feedback. It illustrates the distinction between a core contract, supporting contracts, and procedural content with no independent value.

## Core Contract

```markdown
# Evaluate Feedback Objectively

## Principle

Distrust the source; obey the argument. External claims must earn acceptance, but once an argument closes under the actual context and constraints, update without defending the existing position.

## Applicability Boundary

Suspend source skepticism until the current assumptions, scope, constraints, excluded alternatives, and reasons for exclusion are understood.

## Decisions

| Finding | Action |
|---|---|
| Argument closes in context | Fully update. |
| Core concern is valid but the proposal violates constraints | Preserve the insight and adapt the implementation. |
| Phenomenon is real but outside the accepted scope | Reject for an explicit scope reason. |
| No usable argument | Discard. |
```

This defines the task and its correctness semantics. Removing these rules changes what the skill means.

## Procedural Imitation

```markdown
## Evaluation Procedure

1. Remove status, credentials, confidence, tone, and emotional framing.
2. Extract the claim, premises, causal chain, context, and proposed action.
3. Reconstruct the strongest reasonable interpretation.
4. Separately test the observation, diagnosis, principle, and implementation.
5. Check scope, lifecycle, compatibility, maintenance, migration, and recovery.
6. Assign a classification.
```

Most steps are reasonable in isolation. As a mandatory sequence, they largely restate the core principle or ordinary analytical competence.

The numbering also imposes a cognitive path even though the task establishes no causal dependency between most steps.

One distinction may still add independent value: an observation, diagnosis, design principle, and proposed implementation can have different validity. Preserve that distinction compactly when it prevents a concrete failure; the surrounding procedure does not become necessary merely because it sounds rigorous.

## Supporting Contracts

Suppose the skill also requires:

```markdown
## Required Report

- Classification
- Valid core
- Failure or constraint
- Decision
```

or:

```markdown
## Final Check

- Every finding is evaluated independently.
- Accepted and rejected parts are distinguished.
- The decision states what changes and what remains unchanged.
```

Their value cannot be inferred from their form.

The report may be necessary because the user needs those information categories, reviewers compare outputs, or a downstream system consumes the structure.

The checklist may be necessary because omissions are common and costly, or because each item is a genuine acceptance condition.

The same content is unnecessary when it only standardizes presentation, repeats the core contract, or adds ceremony without changing usefulness.

When the text does not reveal which case applies, confirm the intended use before removing or weakening the requirement.

## Structural Repair

A bloated skill may not be repairable through sentence-level deletion.

For example, its core principle may be scattered across several sections while supporting contracts appear first and repeated checklists dominate the document. Preserving that organization would retain the original confusion even after trimming individual lines.

A structural repair may therefore:

```text
recover the core contract
→ establish the supporting contracts
→ relocate examples and conditional detail
→ remove duplicated derivations
```

Because this changes how the skill is interpreted, the proposed structure and rationale should be reported to the user before applying the rewrite unless substantial restructuring has already been authorized.

## Tool-Wrapper Contrast

A tool-wrapper skill may contain substantial operational detail:

```markdown
python invoke-tool.py <command> <input>

- page numbers are 1-based;
- generated files are written to the path printed after `Agent log:`;
- use `render-region` only after locating the relevant page.
```

These instructions describe real capability and interface contracts. Removing them can make the tool unusable or cause incorrect execution.

The correct question is not:

> Does this look like workflow, formatting, or a checklist?

It is:

> What contract does this instruction serve, and would removing it make the skill less correct, reliable, usable, reviewable, or consumable?

## Lesson

A slim skill preserves:

- the **core contract** that defines the task and correct behavior;
- the **supporting contracts** required for that core to work in its actual environment.

Everything else must justify its independent value. Repair may require deletion, compression, relocation, or structural reconstruction rather than only local edits.
