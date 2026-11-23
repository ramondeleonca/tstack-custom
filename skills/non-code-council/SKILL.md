---
name: non-code-council
description: Trigger this if the user says 'council' about non-code work, such as an essay, report, plan, decision, email, or presentation. Three Claude reviewers critique it in rounds until they agree. For code use council.
---

# Non-code Council

Before the review, finish the draft and fix the problems you already know of.
Give the council the current version; do not hold known fixes for later.

Bring in three Claude delegates. If the user's instructions name members, use
those. Otherwise use the latest Opus, Sonnet, and Fable models, one each, at
high reasoning effort. Give each a different lens:

- **Opus**: substance. Is it true, complete for its goal, and well argued?
  Flag claims without support.
- **Sonnet**: the reader. Is it clear in one read? What would the intended
  audience misread, skip, or push back on?
- **Fable**: risk. What could embarrass the user, mislead someone, leak private
  details, or commit them to something they did not mean?

In Claude Code, start the three with the Agent tool in one message, passing
`model` for each. In T3 Code, use `orchestrator_capabilities` and
`delegate_task`. If a member is unavailable, report it instead of substituting.

Give each delegate the work, its goal, its audience, and any constraints
(length, tone, deadline). Keep them read-only. Ask each for a score out of 10
and findings marked `blocker` (fails its goal), `should` (the reader will hit
it), or `nit`.

Do not wait idle. Check each result as it arrives. Do not edit while a
delegate still reads the same file.

Fix what you agree with, decline the rest in one line with a reason, then
request a fresh round. Stop when no blocker or should is open, or after three
rounds. Then report:

```markdown
## Council review

Rounds: 2

| Delegate | Round 1 | Round 2 |
| --- | --- | --- |
| Claude Opus | 7/10 | 9/10 |
| Claude Sonnet | 8/10 | 9/10 |
| Claude Fable | 6/10 | 9/10 |
```

If a delegate gives no score, write `no score`. Do not invent one.

Fight scope creep. Reviewers will ask for more sections, caveats, and
examples. Keep the work the size its goal needs. Cutting usually beats adding.
