# 01 — Picking Your First Program

Your first program choice matters more than your first tool. A good
first program teaches you the craft; a bad one wastes weeks and pays
nothing. This guide explains what to look for.

## The checklist for a first program

**1. It must be free to enter.**
No submission fee, no stake you have to lock up, no paid verification
step before you can file. Some programs charge per report or require a
paid identity check — skip those until you have payouts behind you.
Joining the big platforms is free; the cost, when there is one, lives
on individual program pages, so always check the program page itself.

**2. It must have a clear written scope.**
The program page should list exactly which domains, apps, or contracts
are in scope, and what is out of scope. If you can't tell what you're
allowed to test, don't test anything. Vague scope is a trap: you can
do real work and still get a "not in scope" rejection.

**3. It should have a visible payout history.**
Look for disclosed reports, a public leaderboard, or a "paid so far"
figure. A program that has never paid anyone — or has been live for
years with zero payouts — is a warning sign. Payout history also tells
you which bug classes the program actually rewards.

**4. The rules should be beginner-friendly.**
Prefer programs that accept Medium and Low findings, explain their
severity tiers plainly, and don't require a runnable proof-of-concept
for every severity. Some programs only pay Critical/High and demand a
PoC for everything — those are fine later, but brutal as a first hunt.

**5. The target should be understandable.**
A web app you can click through beats a 400-contract DeFi protocol for
a first hunt. You need to understand the feature before you can break
it. Pick something you can map in an afternoon.

## What to avoid as a beginner

- **Programs with no public scope** — if you have to ask what's in
  scope, move on.
- **Invite-only or reputation-gated programs** — some platforms only
  let established researchers into the good programs. Build reputation
  on open programs first.
- **Huge, battle-tested targets** — the biggest programs have been
  hunted by thousands of researchers for years. The easy bugs are gone.
  A smaller program with a fresh feature is a better bet.
- **Anything that asks for money up front** — a legitimate bounty never
  needs you to pay to report a bug.

## Warning: program lists go stale

Curated lists of bounty programs (including the directory in
[07-platforms.md](07-platforms.md)) decay fast. Programs close, pause,
or change terms without updating every list that mentions them. Two
real examples:

- **Code4rena** wound down in May 2026 — it still appears on lists that
  haven't been updated.
- **Hats Finance** closed in December 2025 — same story.

Before you invest hours in a program, verify it is alive **today**:
open the program page, check that it accepts submissions, and confirm
the scope and terms match what the list said. Five minutes of checking
saves weeks of wasted hunting.

## A sensible first hunt

1. Pick one open program from the directory that passes the checklist.
2. Read its scope and rules twice. Write the scope down.
3. Read 3–5 of its disclosed reports. Note what paid and what got
   rejected as N/A.
4. Do one recon pass (see the prompt in `agent/prompts/01-first-recon.md`).
5. Hunt one bug class on one feature. If nothing survives the triage
   gate, that's a normal outcome — switch features, not programs, until
   you've covered the surface.

Next: [02 — Setting Up Your Agent](02-setting-up-your-agent.md)
