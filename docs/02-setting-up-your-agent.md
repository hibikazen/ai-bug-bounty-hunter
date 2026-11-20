# 02 — Setting Up Your Agent

This kit is agent-agnostic: the same instruction file works in any AI
coding agent. What changes is *where the file goes*. This guide covers
the common agents plus a generic fallback.

## The instruction file

The master file is [`agent/AGENT.md`](../agent/AGENT.md). It tells the
agent how to hunt: scope first, one bug class at a time, the 7-Question
Gate, safety rules, and the reporting bar. Copy it into your agent as
its instruction file — that is the single most important setup step.

## Per-agent setup

### Muse

Muse reads `AGENTS.md` files. Put the instruction file at the root of
your hunting workspace as `AGENTS.md` (rename it from `AGENT.md`).
Muse picks it up automatically for work in that folder.

### Claude Code

Claude Code reads `CLAUDE.md`. Copy `agent/AGENT.md` to `CLAUDE.md` in
your project root for per-project instructions, or to `~/.claude/CLAUDE.md`
for instructions that apply everywhere.

### Codex

Codex reads `AGENTS.md`. Copy `agent/AGENT.md` to `AGENTS.md` in your
project root (or `~/.codex/AGENTS.md` for global instructions).

### Cursor

Cursor uses project rules in `.cursor/rules/` (Markdown files with
frontmatter, `.mdc` extension) and global rules in Settings → Rules.
Copy the content of `agent/AGENT.md` into a rule file such as
`.cursor/rules/bug-bounty.mdc`, or paste it into Settings → Rules for
a global setup. (Older Cursor versions used a single `.cursorrules`
file at the project root.)

### Any other agent (generic fallback)

Almost every AI coding assistant accepts custom instructions somehow:
a system prompt, a "custom instructions" box, a project memory file,
or a pasted message at the start of a session. If your agent has none
of the files above, paste the whole content of `agent/AGENT.md` into
whatever instruction mechanism it offers, or paste it as the first
message of each hunting session.

> Agent file locations change over time. If your agent ignores the
> file, check that agent's current documentation for where it reads
> instructions from.

## Recommended skills and tools per agent

You don't need any of these to start — the instruction file plus the
starter prompts are enough for a first hunt. Add tooling when a hunt
actually needs it.

- **Recon (web):** subfinder, httpx, nuclei, katana, ffuf, nmap.
  Install from the projects' GitHub releases. See
  [06-tools.md](06-tools.md) for links.
- **Web proxy / manual testing:** Burp Suite (Community Edition is
  free) or OWASP ZAP (free and open source). A proxy lets you see and
  replay the requests your browser sends — essential for proving bugs
  by hand.
- **Smart contracts:** Foundry (`forge`/`cast`/`anvil`) and Slither.
  Foundry's installer is at <https://getfoundry.sh/>.
- **Methodology skill packs (optional, for agents that support skills):**
  - [Agentic-Bug-Hunter](https://github.com/awarexone/Agentic-Bug-Hunter)
    — CLI + skill bundle, recon to report.
  - [Claude-BugHunter](https://github.com/elementalsouls/Claude-BugHunter)
    — 83 skills + 681 disclosed-report patterns across 36 bug classes.
  - [recon-skills](https://github.com/uphiago/recon-skills)
    — 41 recon skills and playbooks.
  - [security-audit-skill](https://github.com/cloudflare/security-audit-skill)
    — Cloudflare's 6-phase audit workflow.
  - [REA](https://github.com/morluto/rea) — reverse engineering
    (EVM bytecode, native binaries, JS apps).
  These are the sources this kit is built on — see
  [CREDITS.md](../CREDITS.md). Install them only if your agent
  supports skills and you want the deeper playbooks; the instruction
  file in this repo already carries the core methodology.

## Accounts and keys

**Needed before your first hunt:**

- A **GitHub account** — most programs' scope links to GitHub repos,
  and several platforms use GitHub login.
- An account on **each platform you hunt on** (HackerOne, Bugcrowd,
  Immunefi, etc.). Joining is free on the major platforms; check the
  program page for any program-specific requirements.

**Optional (add when a hunt needs it):**

- A **second test account** on the target (attacker + victim) for
  access-control bugs. Both accounts must be yours.
- A **crypto wallet** (for Web3 programs) — only for programs that pay
  in crypto, and only with funds you can afford to use for gas on
  test transactions. Never reuse a wallet that holds real funds for
  testing.
- **API keys** for recon services (some subdomain tools offer paid
  tiers). Start with the free tiers; paid data is a later optimization.

**Never put in your agent or your repo:** passwords, API keys, private
keys, session tokens, or wallet seed phrases. If an agent asks for one
to "help you test", stop — that is not part of legitimate hunting.

## Workspace layout (suggested)

```text
bounty-hunting/
  AGENTS.md              # or CLAUDE.md — the instruction file
  recon/<program>/       # recon notes per program
  findings/<program>-<bug-class>/
    report-draft.md
    poc/
    evidence/            # screenshots, request/response captures
```

Keep recon notes and findings in files, not in chat scrollback — you
will want them months later when a similar bug shows up.

Next: [03 — The Hunt Workflow](03-the-hunt-workflow.md)
