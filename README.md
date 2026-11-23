# tstack-custom

My fork of [t3dotgg/tstack](https://github.com/t3dotgg/tstack) for Claude Code:
reviews run on Claude models only, and each workflow has a `non-code-*` version
for writing, plans, and research.

## Code skills

| Skill | Say | What it does |
|---|---|---|
| `full-send` | "full send" | Takes a change to a merged PR unattended: proves it, reviews it, files it, babysits it, merges it. |
| `full-stop` | "full stop" | Same, but stops when the PR is ready for you to merge. |
| `council` | "council" | Three Claude reviewers (Opus: correctness, Sonnet: simplicity, Fable: risk) loop until they agree. |
| `review-loop` | "review loop" / "sol loop" | One fresh Claude Opus reviewer loops with you until both agree. |
| `file-pr` | "file a PR" | Files a short PR that leads with the problem. |
| `takeover` | "take over" | Finishes someone else's PR or branch and keeps their credit. |
| `babysit-pr` | "babysit" | Watches a PR through CI and review bots. |
| `modernize` | "modernize" | Rebases an old PR and decides if it should still exist. |
| `leaving-pr-comments` | (automatic) | Formats comments posted on your behalf. |

## Non-code skills

| Skill | What it does |
|---|---|
| `non-code-full-send` | Finishes a task end to end, including the send, publish, or delete step your request names. |
| `non-code-full-stop` | Same, but never sends, publishes, or deletes. Leaves drafts. |
| `non-code-council` | Three Claude reviewers critique writing or a plan: substance, reader, risk. |
| `non-code-review-loop` | One Claude reviewer loops on writing or a plan until both agree. |
| `non-code-takeover` | Finishes someone else's doc or plan on a copy, keeping their credit. |
| `non-code-modernize` | Refreshes an old plan or doc and recommends modernize, rework, or retire. |

## Install

```bash
git clone https://github.com/ramondeleonca/tstack-custom ~/tstack-custom
ln -s ~/tstack-custom/skills/* ~/.claude/skills/
```

`babysit-pr` needs an authenticated `gh` and `python3`.

## License

MIT, from the original tstack. See [LICENSE](LICENSE).
