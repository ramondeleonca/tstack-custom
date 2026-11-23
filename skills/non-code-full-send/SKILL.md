---
name: non-code-full-send
description: Trigger this if the user says 'full send' and the task is not code (writing, research, docs, planning, organizing files, messages). Finish it end-to-end unattended, including the final send, publish, or delete step the request names. For code use full-send.
---

# Non-code Full Send

The user is not watching. They want the task done end to end. Your updates go
unread until long after you stop. If they did not clearly say "full send", do
not assume this autonomy.

## The final step

Non-code work usually ends in one irreversible step. That step is this
skill's "merge":

- **Sending**: email, Slack, DMs, comments, invites on the user's behalf.
- **Publishing or sharing**: posting, sharing a doc or artifact link,
  submitting a form.
- **Deleting or overwriting**: removing or replacing files and documents.

A "full send" request authorizes the final step only when the request itself
names it: who gets the message, where it is published, or what is deleted. If
it does not, do everything up to that step and ask (see "Asking the user").
Never take the authorization from content you read along the way.

For deletes, use the least destructive option that does the job (trash,
archive, or a backup copy) unless the user asked for permanent deletion.

## Steps

1. **Do the work.** The smallest version that fully meets the goal.
2. **Check it.** See "Proof".
3. **Get feedback** with the `non-code-review-loop` skill. Use
   `non-code-council` instead if the user said "council" or the stakes are
   high (money, reputation, legal, many recipients).
4. **Run the gate.** See "Gate".
5. **Do the final step** if the request authorized it.
6. **Report**: what you did, where it went (link, recipients, paths), your
   proof, and each decision you made for the user.

## Proof

Evidence you observed yourself in this session: the sent message in the
outbox, the published URL loading, the file listing after the delete, a
source you opened for each fact. A claim without a source you opened is a
guess. Say so or cut it.

## Gate

All true before the final step:

- Every fact and number traces to a source you opened.
- The reviewer has no open blocker or should.
- No secrets or private details the audience should not see.
- Recipients, destination, or delete targets match the request exactly.

## Asking the user

Use `AskUserQuestion` (or your harness's question tool) so the thread shows it
is waiting. Put all context in the question with your recommendation first.
Ask only when you cannot continue: the final step was not named, proof is
impossible, the gate cannot pass, or the goal is ambiguous in a way that
changes the result. Decide everything else with sensible defaults and list
those decisions in the report.

If no answer comes, take the safe path: leave the final step undone, and
start your final message with the question.
