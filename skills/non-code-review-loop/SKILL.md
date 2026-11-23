---
name: non-code-review-loop
description: Use when the user says "review loop" or "sol loop" about non-code work (writing, a plan, research, a decision). One fresh Claude reviewer critiques it in rounds until both agree. For code use review-loop.
---

# Non-code review-loop

A fresh Claude reviewer with no stake in the work reviews it in a loop. Make
the smallest changes that answer real findings, and push back on the rest.

## Budget

- 3 rounds by default. Round 1 is full; later rounds check only what changed
  and open findings.
- Extend to 5 only when a blocker stays open with evidence, or the user asks.
- Stop early if a round returns only nits.
- Keep a ledger: id, severity, outcome.

## 1. Scope

State the goal, the audience, and what is out of scope in 1-2 sentences. Save
the work to a file if it is not in one, so every round reads the same thing.

## 2. Start the reviewer

Use the latest Claude Opus unless the user named another model. In Claude
Code, start it with the Agent tool (`model: "opus"`) and keep its ID so later
rounds continue it with SendMessage. In T3 Code, use `delegate_task`.

Round 1 brief:

```
Review only. Do not edit the file or start subagents.
File: <abs path> Goal: <goal> Audience: <audience> Out of scope: <scope>
Find: wrong or unsupported claims, gaps that break the goal, anything the
audience would misread, private details or commitments the author did not mean.
Skip taste unless it hurts the reader. Hold to the current length. Flag
sections the goal does not need.
blocker = fails its goal. should = the reader will hit it. nit = rest.
Reply:
VERDICT: APPROVE or CHANGES
R1 [blocker|should|nit] <section or line> <claim>. Fix: <suggestion> (stable ids)
```

Do not edit the file while the review runs. No reply is not approval.

## 3. Answer findings

Check each finding yourself. Agree: smallest fix, prefer cutting. Disagree:
say why with evidence. Nit or out of scope: decline in one line. If the work
grew, cut first.

## 4. Next round

Only if budget remains and a blocker or should is open. Send the ledger and
what changed. Ask the reviewer to mark each old id `resolved` or
`still open: <reason>`.

## 5. Stop

Agreed: APPROVE, nothing open. Stuck: an item disputed after two replies, or
budget ends. Show both sides in 2-3 lines; the user decides.

Report: rounds, model, what changed, length before/after, fixed and declined
findings with reasons.
