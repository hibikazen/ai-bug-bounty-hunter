# AI Bug Bounty Hunter

A beginner-friendly, agent-agnostic starter kit for hunting bug bounties
with an AI coding agent.

You don't need to be a security expert to start. You need a program with
clear rules, an AI agent with good instructions, and the discipline to only
report bugs you can actually prove. This repo gives you all three: a
copy-paste instruction file for any agent, a step-by-step workflow, starter
prompts, report templates, and honest guidance on what to expect.

> **This is not a get-rich-quick kit.** Bug bounty is hard. Most beginners
> earn $0 for their first weeks or months. The hunters who get paid are the
> ones who report few, high-quality, proven bugs — not the ones who submit
> the most reports. This kit is built around that truth.

## Who this is for

- You've never hunted a bug bounty before and want a structured way in.
- You already use an AI coding agent (Muse, Claude Code, Codex, Cursor,
  or anything else) and want it to help you hunt — safely and in scope.
- You want one place that collects the workflow, the rules, and the
  templates, instead of piecing it together from a dozen blog posts.

## Quickstart (5 steps)

**1. Pick your first program.**
Read [docs/01-picking-your-first-program.md](docs/01-picking-your-first-program.md).
Start with a FREE program: no submission fee, no stake, no paid
verification. Make sure it has a clear written scope and a visible payout
history. Verify it is actually alive before you hunt — program lists go
stale.

**2. Set up your agent.**
Copy [agent/AGENT.md](agent/AGENT.md) into your agent as its instruction
file. Where it goes depends on your agent — see
[docs/02-setting-up-your-agent.md](docs/02-setting-up-your-agent.md).
It works with Muse, Claude Code, Codex, Cursor, and any agent that takes
custom instructions or a system prompt.

**3. Do your first recon.**
Paste the recon prompt from
[agent/prompts/01-first-recon.md](agent/prompts/01-first-recon.md) and let
the agent map the target's in-scope surface. Save the notes using
[templates/recon-notes-template.md](templates/recon-notes-template.md).

**4. Hunt one bug class at a time.**
Follow the workflow in [docs/03-the-hunt-workflow.md](docs/03-the-hunt-workflow.md):
recon → hypothesize → verify → prove with a PoC → triage → report.
One bug class per pass. Kill weak findings fast — most ideas die, and
that's normal.

**5. Report only what you proved.**
When a finding survives the triage gate, write it up with
[templates/report-template.md](templates/report-template.md) and the
guidance in [docs/04-writing-a-report.md](docs/04-writing-a-report.md).
One issue per report. Never submit a report you haven't verified yourself.

## Repo map

```text
agent/
  AGENT.md            The master instruction file — copy it into any agent.
  prompts/            Starter prompts: recon, deep-dive, triage, PoC, report.
docs/
  01-picking-your-first-program.md
  02-setting-up-your-agent.md
  03-the-hunt-workflow.md
  04-writing-a-report.md
  05-safety-and-rules.md
  06-tools.md         Tooling map by lane (web, smart contracts, mobile, RE).
  07-platforms.md     Platform directory (HackerOne, Bugcrowd, Immunefi, ...).
templates/
  report-template.md
  recon-notes-template.md
  triage-checklist.md
CREDITS.md            Every project and methodology this kit builds on.
```

## The rules that matter most

Read the full version in [docs/05-safety-and-rules.md](docs/05-safety-and-rules.md).
The short version:

- **Never hunt out of scope.** If an asset isn't listed as in scope, don't
  touch it. Testing outside scope can get you banned — or worse.
- **Test with your own accounts and funds only.** Never touch other users'
  accounts or data, even to "prove" a bug.
- **No denial-of-service testing.** Don't flood, crash, or degrade a target.
- **Stop after sufficient proof.** Once you can reproduce the bug, stop.
  Don't dig deeper, don't exfiltrate more, don't keep exploiting.
- **No public disclosure before permission.** Follow the program's disclosure
  policy. Never publish a bug before the team allows it.
- **Never mass-submit AI-generated reports.** Platforms detect and ban
  AI slop spam. Every report must be human-verified and PoC-proven before
  it is sent.

## What this kit is built on

This is a synthesis, not an invention. The workflow, the triage gate, the
report structure, and the tooling map are adapted from excellent open work
by other people — see [CREDITS.md](CREDITS.md) for every source, author,
and license. If this kit helps you, go star the projects it stands on.

## License

MIT. See [LICENSE](LICENSE).
