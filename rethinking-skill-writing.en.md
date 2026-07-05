---
title: "Rethinking SKILL Writing: Why Many SKILLs Are Actually Bad Today"
language: "en"
---

A few days ago, I was organizing a SKILL called `arrogant-objectivist`. Its purpose was simple: when receiving external reviews, inspection comments, or feedback, do not get carried away by the other party's tone, status, or authority. First examine whether the argument itself holds.

I vibed out a core prompt and gave it to GPT. I only wanted it to help me add frontmatter. Instead, it decided to “optimize” the whole thing on its own. When I saw the result, my blood pressure instantly spiked.

## 1. Two Versions: Which One Do You Think Is Better?

I made two versions. To keep the article from getting out of control, I am only excerpting the parts that best illustrate the issue.

Ver A:

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

Ver B:

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

If you look only at individual sentences, Ver B is almost impossible to criticize. Remove social pressure, distinguish phenomena from diagnoses, check the lifecycle, make uncertainty explicit — all of these are correct. It even looks more rigorous than Ver A.

But my judgment is extreme: Ver A is excellent; Ver B is garbage.

The reason is not that I prefer short text, nor that adding a few hundred tokens is some original sin. The real problem is this: Ver A defines the judgment principles, applicable boundaries, and decision outcomes of the task. Ver B takes the thinking process that a capable Agent could have completed on its own and breaks it into a set of standard moves that must be performed. The difference looks like a few paragraphs, but it is actually the difference between specifying what must hold and constraining the posture by which the Agent must reach the destination.

## 2. Not Writing Fastidiousness; the Model Executing SKILL Has Changed

Agent Skills was officially released only in October 2025 and became an open standard only in December. By the age scale of technical products, it has barely left infancy. [1]

But that is exactly where things get interesting: SKILL is new, yet the capability assumptions it depends on have already started to age. The reason is that, over the past half year, models have crossed an important capability threshold.

When SKILL was born, frontier models could already write code, call tools, and execute multi-step tasks. But in long-running tasks, they were still prone to getting lost. In November 2025, Anthropic was still discussing how to use initializer agents, progress files, and explicit task lists to help models sustain work across context windows. [2] In other words, Agents at the time were like highly capable executors whose memory and persistence were still unstable. You were better off placing road signs densely along the way.

So workflows like “understand first, then plan, then execute, then verify” were not stupid. They were reasonable scaffolding for that stage.

The issue is that, over the past half year, model capability has not moved along a gentle curve. From long-running coding to complex knowledge work, frontier models have started to more reliably understand goals, choose tools, check their own work, and keep moving forward without step-by-step human traction. In February 2026, when OpenAI described long-horizon tasks with Codex, it summarized the working mode as users steering at milestones rather than micromanaging line by line. By GPT-5.5, OpenAI further emphasized that the model can understand tasks earlier, require less guidance, use tools more effectively, check its work, and continue making progress. [3][4]

The threshold I am talking about is not a mathematical discontinuity in some benchmark curve. It is more of an engineering threshold: scaffolding that previously had to be written by humans into prompts or SKILLs can now increasingly be generated, revised, and verified by the model itself.

```text
Before crossing the threshold:
The Agent executes the route you provide
→ Workflow is a capability patch

After crossing the threshold:
The Agent can find, correct, and verify routes on its own
→ The same Workflow may become a capability ceiling
```

At this point, the burden of proof should reverse. In the past, we asked: why not write the steps clearly? Now we should ask: why must this step be hardcoded into the SKILL?

## 3. One Successful Run Only Proves That This Path Can Run

Many new-era garbage SKILLs, at least from my personal perspective, are born in a very natural way. The author first completes a task successfully, then reviews the process: first list directories, second read files one by one, third extract frontmatter, fourth merge, and finally check counts.

There may be nothing wrong with that route. But at most it proves this: under the environment, tools, and judgments at that moment, this approach could succeed. It does not prove that every future Agent should follow the same path.

```text
This path succeeded once
        ↓
This path is worth recording
        ↓
Future Agents must follow this path -> ARE YOUR SURE?
```

The suspicious part is the final jump. In one successful case, at least three different things are mixed together: conditions indispensable to task success, interface facts objectively present in the current environment, and the strategy the author happened to choose at the time. The first two are usually worth writing into a SKILL. The third is, by default, just a piece of history.

But Markdown lists compress all three into the same tone. When we write `1, 2, 3, 4`, it naturally implies that these items are complete and that their order is meaningful. The author may merely be recalling a few possible actions, but the Agent reads a closed pipeline.

This is similar to forms in bureaucratic systems: once the form defines which boxes need to be checked, the executor obtains an escape route from responsibility. Once all boxes are checked, the process is considered complete. Whether the problem has actually been solved becomes secondary.

Before writing this article, I had even developed a conditioned reflex: whenever I saw a SKILL.md full of Markdown lists, I instinctively felt sick.

Why? Because the greatest danger of lists is that they easily transmit “a few things I thought of” as “the world contains only these few things,” thereby killing the possibility that an Agent smarter than you could find a better path.

## 4. SKILL Should Preserve Contracts, Not Routes

If we no longer treat a one-time workflow as the norm, then what exactly should remain in a SKILL?

I now prefer to divide it into two layers. The first layer is the core contract: what the task is, what behavior counts as correct, which boundaries cannot be crossed, and what outcome means success or failure. For the feedback-review SKILL above, “distrust the source; obey the argument” is the core contract. If an argument closes under the real constraints, you must update rather than defend the existing design to save face.

The second layer is the supporting contract. It does not define the task itself, but it allows the core contract to be executed, verified, delivered, or consumed by others in the real environment. Command parameters, output schemas, mandatory report fields, high-risk operation gates, audit requirements, and certain checklists may all belong to this layer.

Do not misunderstand me: I am not saying that output formats, checklists, or operating steps must be classified as “bad things.” In fact, the same form can mean completely different things in different contexts.

If a downstream system truly depends on fixed JSON, the format is a contract. If users need `Valid core / Failure / Decision` to inspect the conclusion, those fields also have real value. Conversely, if fixed headings exist only because the author feels that “a report should look like this,” then they are merely ritual.

> To decide whether a piece of content should remain, do not look at whether it resembles a process, format, or checklist. Look at what real need it serves.

Therefore, what should be deleted is not “everything outside the core.” What should be deleted is content that neither constitutes the core contract nor provides necessary support for it: repeated explanations, conclusions that can be easily inferred, steps without causal necessity, sections added only to look complete, and nonsense that merely recites general capabilities.

## 5. Of Course, I Am Not Against All Processes

This view can easily be pushed to the other extreme: if strong Agents can plan on their own, then shouldn’t a SKILL contain only one sentence stating the goal? No. Stating only the result creates vulnerabilities as well.

For example, if success is defined as “all tests pass,” the model may delete failing tests, loosen assertions, or run only the easiest subset to pass. Opening the strategy space does not mean opening the definition of correctness.

Tool-wrapping SKILLs also often need many concrete operations. If a `read-pdf` SKILL states that page numbers start from 1, that the output path is read from the `Agent log`, and that scanned pages must be rendered rather than trusted through Markdown alone, these are not human preferences about the thinking process. They are interface facts and capability boundaries. No matter how smart the Agent is, it cannot invent commands that do not exist.

So the real boundary is never whether there is a workflow. It is where the binding force of the workflow comes from. If it comes from a real interface, causal order, safety risk, or external consumer, it should be strict. If it only comes from the fact that the author once did it that way, it has no right to become discipline for future Agents.

## 6. A Real Paradigm Shift

SKILL has existed for only a little more than half a year, so in theory it should be too early to talk about an “old era.” But there is no way around it: the models executing SKILL are changing faster than the specification itself. A certain instruction may have been necessary scaffolding last year, a helpful reminder today, and a hard constraint that prevents the model from performing well tomorrow.

```text
The lifecycle of the same instruction:

Necessary scaffolding
→ Helpful hint
→ Ineffective redundancy
→ Harmful constraint
```

This is also why optimizing complex SKILLs cannot only mean deleting words sentence by sentence in place. Sometimes the problem lies in the section structure itself: core principles scattered across multiple places, supporting contracts overpowering the task itself, examples written as rules, and multiple checklists repeatedly enumerating the same thing. In such cases, substantial rearrangement, merging, or even rewriting should be allowed.

Of course, “major revision” does not mean the Agent may rewrite the task definition without permission. If the Agent is preparing to rebuild the sections and logic, it should first explain to the user: what it believes the core contract is, where the current structure has problems, how it plans to reorganize it, and which content will be preserved, moved, or deleted. Let the user inspect the direction before the knife comes down.

In the end, the era of strong Agents is not about removing human control. It is about putting control back in the right place: humans define the task, boundaries, and acceptance criteria; models search for better paths within that space.

> After models cross the capability threshold, process constraints no longer enjoy default legitimacy. Any rule that restricts an Agent's strategy space should prove that it comes from the task, environment, or risk — not from a route the author once managed to run successfully.

So now, when I see a long and complete SKILL, I do not first ask whether it is detailed enough. I first ask: if these steps are deleted, will the Agent actually do the wrong thing?

If not, then they probably never belonged in that SKILL.

— Running once is not the same as becoming a norm. In the new era, humans should stop injecting workshop-style experience into hard constraints. Deciding what is right and what is wrong is the responsibility that truly belongs to humans.

## References

- [1] Anthropic, “Equipping agents for the real world with Agent Skills,” 2025-10-16; the page records the 2025-12-18 release of the open standard. Original.
- [2] Anthropic, “Effective harnesses for long-running agents,” 2025-11-26. Original.
- [3] OpenAI, “Run long horizon tasks with Codex,” 2026-02-23. Original.
- [4] OpenAI, “Introducing GPT-5.5,” 2026-04-23; GPT-5.5 System Card. Original.
