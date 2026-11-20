# 03 — The Hunt Workflow

A hunt has seven stages. Most of your time goes to the first three;
most beginners fail by skipping straight to the last two.

```text
recon → hypothesize → verify → PoC → triage → report → follow-up
```

This workflow adapts Cloudflare's 6-phase security-audit workflow
(recon + coverage ledger, coverage-led hunting, adversarial validation,
structured findings, independent verification, reporting) to bounty
hunting, and layers Agentic-Bug-Hunter's gates on top. See
[CREDITS.md](../CREDITS.md).

## Stage 1 — Recon: map before you touch

Goal: a complete map of the in-scope surface, and a ranked list of
leads. Passive first; active only inside confirmed scope.

- Confirm the scope in writing and keep it visible.
- Enumerate subdomains and live hosts; record every live asset.
- Map the tech stack (frameworks, auth provider, CDN, JS libraries).
- Map features: what the app does, which parts need auth, where user
  input flows, where money or private data moves.
- Read at least 3 disclosed reports for the program. Note which bug
  classes paid and which are exhausted.
- Check the changelog, docs, and issue tracker for acknowledged
  behavior — don't hunt what they already know about.

Save it all in a recon-notes file (see
`templates/recon-notes-template.md`). Good recon is reusable: the next
hunt on the same target starts from your notes, not from zero.

## Stage 2 — Hypothesize: one crown jewel, one bug class

- Pick one crown jewel first: money movement, account access, or
  private data. Hunt the feature that guards it.
- Pick ONE bug class per pass and go deep before switching. Common
  classes for web targets: broken access control / IDOR, injection
  (SQLi, XSS, SSTI), SSRF, auth bypass, business logic, race
  conditions, file upload, GraphQL abuse, OAuth/JWT flaws, cache
  poisoning, insecure direct object references.
- Before diving into a class, read disclosed reports for that class.
  Start from paid-finding shapes, not abstract OWASP descriptions.
- Write each hypothesis down in the form: "If I do X, then Y happens,
  which would mean Z impact." A hypothesis you can't state this way
  isn't ready to test.

## Stage 3 — Verify: evidence, not vibes

- Test with your own accounts only. For access-control bugs, use two
  accounts you own (attacker + victim).
- Keep requests minimal and reversible. Record the exact request and
  response for anything interesting.
- A response code alone never proves a vulnerability. You need semantic
  evidence: the other user's data in the response, the state change,
  the internal service answering.
- If a hypothesis dies, record why it died (in the coverage ledger).
  A killed lead is still progress — it stops the next pass from
  re-testing the same thing.
- Switch targets after an hour without progress; switch features after
  five minutes of nothing but 401/403/404.

## The coverage ledger

Borrowed from the audit workflow: a running list of what you checked,
so you don't re-hunt the same surface and so you can see what you
haven't touched yet.

| Asset / feature | Bug class | Verdict | Note |
|---|---|---|---|
| api.example.com /invoices | IDOR | Killed | IDs are random UUIDs, no enum |
| example.com /reset-password | Host header | Open | Not tested yet |
| example.com /upload | File upload | Confirmed | See finding F-03 |

Keep it in the recon-notes file. After each hunting wave, do a "critic
pass": look at the ledger and ask what entry points, parallel paths, or
lifecycle modes you haven't covered. The gaps are your next leads.

## Stage 4 — PoC: prove it, minimally

- A PoC is the smallest thing that proves the impact: one curl command,
  a short script, or a few clicks — reproducible by a stranger from zero.
- It must show the impact, not just the request. A bare `200 OK` is
  not a PoC.
- For web bugs: request/response pairs, screenshots, or a short video.
  Redact sensitive data.
- For smart contracts: a single `forge test` that proves the impact
  with an explicit assertion on the drained balance, minted token, or
  corrupted state — runnable on a local fork, never on mainnet or
  testnet. (Immunefi auto-rejects submissions without a PoC.)
- Stop after sufficient proof. Don't exfiltrate more, don't escalate
  further.

## Stage 5 — Triage: try to kill your own finding

Run the 7-Question Gate (in `agent/AGENT.md`), then the independent
triage gate and the self-duplicate check (see
`templates/triage-checklist.md`). Be adversarial: your job at this
stage is to disprove the finding. Most candidates die here, and that's
the system working — every killed report is reputation saved.

Submission floors: don't submit Low/Informational findings, and don't
submit pure denial-of-service impact. If the severity moves within
Medium/High/Critical, correct the report and file at the proven
severity.

## Stage 6 — Report: one issue, well written

Follow [04 — Writing a Report](04-writing-a-report.md) and the
template in `templates/report-template.md`. One issue per report.
Human-reviewed before sending — always.

## Stage 7 — Follow-up: be a professional

- Answer triager questions quickly and politely. They decide your
  payout; make their job easy.
- If the report is marked N/A or duplicate, read the reason carefully.
  It usually teaches you something about the program's bar — apply it
  to the next hunt.
- If the report is accepted, follow the disclosure policy. Don't
  publish anything before the team allows it.
- Don't nag for status. Programs state their review windows; respect
  them.

## The mindset, in one paragraph

You are not spraying payloads and hoping. You are a careful tester
with a map (recon), a hypothesis (one bug class, one feature), evidence
(a reproducible PoC), and a critic (the triage gate) — and you only
speak when the evidence is solid. That discipline is the whole skill.
The tools and the agent are just leverage.

Next: [04 — Writing a Report](04-writing-a-report.md)
