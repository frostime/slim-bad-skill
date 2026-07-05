# Glossary

This glossary covers only the terms needed to read the article and the accompanying SKILL examples.

| English | Chinese | Definition |
|---|---|---|
| **Core Contract** | 核心契约 | The minimal coherent definition of a task: what it governs, what behavior or result it requires, and which boundaries distinguish correct from incorrect execution. Removing it changes the skill's identity or correctness semantics. |
| **Supporting Contract** | 支撑契约 | Constraints that make the core contract reliably executable, verifiable, deliverable, reviewable, or consumable in its actual environment (e.g., tool interfaces, output schemas, safety gates). |
| **Tool-Wrapper SKILL** | 工具封装型技能 | A SKILL whose primary role is to describe real CLI/script tool interfaces, command semantics, path resolution, and output protocols. Often requires dense operational detail that is genuinely contract, not bloat. |
| **Specification Gaming** | 规格游戏 | The risk that an open-strategy agent exploits vague success definitions (e.g., "all tests pass" by deleting failing tests). Prevented by keeping correctness criteria in the core contract. |
| **Closed List** | 封闭列表 | A list presented as exhaustive, ordered, or mandatory. Dangerous when used for heuristics, examples, or possible methods that are actually open-ended. |
| **Bloated / Mechanical / List-Heavy** | 臃肿 / 机械 / 列表堆砌 | Descriptors for SKILLs that contain excessive procedural imitation, redundant derivations, false closed sets, or author preference disguised as necessity. |
