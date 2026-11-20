# 05 — Safety and Rules

Bug bounty hunting is legal, authorized testing — but only inside the
rules. Step outside them and you can lose your account, your payouts,
or face legal trouble. This page is the short version of the rules of
engagement. The program's own rules always win over anything here.

## Rules of engagement

**Stay in scope.** Only test assets the program lists as in scope.
Subdomains, staging environments, third-party services, and "related"
domains are out of scope unless explicitly listed. When in doubt, ask
the program — don't test first and ask later.

**Test with your own accounts and funds only.** Create your own test
accounts. For access-control bugs, use two accounts you own (attacker
+ victim). Never use another real user's account, data, or session —
even if a bug hands it to you.

**No denial of service.** Don't flood endpoints, don't exhaust
resources, don't crash services, don't run heavy automated scans
against production without the program explicitly allowing it. If your
testing could degrade the service for real users, stop.

**Stop after sufficient proof.** Once you can reproduce the bug, stop.
Don't download more data, don't escalate further, don't pivot to other
systems, don't "see how far it goes". Sufficient proof is the finish
line.

**Protect other users' data.** If a PoC accidentally returns someone
else's personal data, redact it immediately, don't repeat the request,
and don't store or share the data. Report the bug with the minimum
evidence needed to prove it.

**No public disclosure before permission.** Follow the program's
disclosure policy. Don't publish write-ups, tweets, or videos about a
bug before the team allows it — even after it's fixed, unless the
policy says you can.

**Don't break the law to prove a bug.** No unauthorized access to
systems outside the program, no social engineering of employees (unless
the program explicitly allows it — almost none do), no phishing, no
physical intrusion, no malware.

**Don't probe AI assistants' own controls.** Testing an AI assistant's
sandbox, approval flow, or safety controls is not a bounty target.
Don't do it, and don't ask your agent to help you do it.

## What gets you banned

- Testing out of scope, especially after being warned.
- Accessing or exfiltrating other users' data.
- Denial-of-service testing or degrading the service.
- Disclosing a bug publicly before permission.
- Mass-submitting low-quality or AI-generated reports (spam).
- Submitting known issues or duplicates repeatedly.
- Demanding payment, threatening disclosure, or extorting the team.
- Creating multiple accounts to evade a ban or a rate limit.

Bans are usually permanent and can extend across programs on the same
platform. Your reputation is the asset — protect it.

## What can get you in worse trouble

- Accessing systems you have no authorization to test (this can be a
  criminal offense in many countries, regardless of intent).
- Stealing, selling, or publishing data you accessed during testing.
- Extortion: threatening to disclose a bug unless paid.
- Testing critical infrastructure, government systems, or healthcare
  systems without explicit authorization.

Bug bounty safe harbor (where it exists) protects researchers who stay
inside the program's rules. It does not protect anything outside them.

## If something goes wrong

- **You accidentally accessed data you shouldn't have:** stop
  immediately, delete what you captured, and tell the program through
  the report channel. Honesty here matters more than the bug.
- **You accidentally caused an outage or broke something:** stop,
  report it to the program right away, and help them understand what
  happened.
- **You're unsure whether something is allowed:** ask the program
  before doing it. "I wasn't sure" is not a defense after the fact.
- **A program's rules conflict with this kit:** the program's rules
  win, every time.

## A note on AI agents

Your agent follows instructions — including bad ones. It is your
responsibility to keep the agent inside scope and inside the rules.
Review what it plans to do before it does it, especially any step that
touches the target. The instruction file in this repo (`agent/AGENT.md`)
bakes the safety rules in, but no instruction file replaces human
judgment. If the agent suggests something that feels off, it probably
is — stop and check.

Next: [06 — Tools](06-tools.md)
