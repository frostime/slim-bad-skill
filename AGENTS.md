# Agent Instructions

## Scope

This file governs how future automated or agent-assisted updates should interact with this repository.

## Terminology Rule

**All edits, translations, rewrites, and new content in this repo must stay consistent with `glossary.md`.**

Before writing or modifying any markdown file (articles, SKILLs, READMEs, references), read `glossary.md` and use the defined terms as the canonical vocabulary. If a concept is not in the glossary, add it there first before using it in other files.

Key conventions:

* Use **"core contract"** and **"supporting contract"** (not "main contract / auxiliary contract" or similar variants).
* Use **"workflow"** (not "process" or "pipeline") when referring to fixed step-by-step routes in a SKILL.
* Use **"repair pass"** (not "refactor" or "cleanup") when describing the slimming operation performed by `slim-bad-skill`.
* Use **"capability threshold"** (not "model breakpoint" or "AI maturity") when discussing the engineering boundary where scaffolding becomes harmful.
* Use **"specification gaming"** (not "cheating" or "loophole") when describing the risk of vague success criteria.
* Preserve the distinction between **"closed list"** (exhaustive, mandatory) and open-ended heuristics.

## Content Boundaries

* Do not rewrite `rethinking-skill-writing.zh.md` or `rethinking-skill-writing.en.md` without explicit user approval. These are published articles.
* SKILL files under `skills/` may be repaired or extended, but any structural rewrite must report the recovered core contract and proposed changes before applying them (per the contract model in `skills/slim-bad-skill/SKILL.md`).
* `glossary.md` is the source of truth: update it when new load-bearing terms appear; prune it when terms become obsolete.
