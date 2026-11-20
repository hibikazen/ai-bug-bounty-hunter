# 04 — Writing a Report

A good report gets triaged fast and paid fairly. A bad report gets
ignored, marked N/A, or — worst — damages your reputation so your next
good report is trusted less. This guide covers the structure, the tone,
and the one warning that matters most.

## Before you write: the pre-checks

- The bug is in scope (checked against the program page, not memory).
- You checked for duplicates in disclosed reports and the changelog.
- You tested safely: your own accounts, no other users' data, no DoS.
- You re-verified it — no false positives, no scanner output without
  manual confirmation.
- It passed the 7-Question Gate and the triage checklist
  (`templates/triage-checklist.md`).

## Report structure

Use the template in `templates/report-template.md`. The sections:

### 1. Title

Specific: bug class + location + impact.

- Bad: "XSS on the website"
- Good: "Stored XSS in the /posts/{id} comment field allows session
  hijacking of any user who views the post"

Title formula: `[Bug Class] in [Exact Endpoint/Feature] allows
[attacker role] to [impact] [victim scope]`.

### 2. Summary

Two or three sentences. What the bug is, where it is, what happens
because of it. The triager reads this first — make it count.

### 3. Severity

Propose Low, Medium, High, or Critical, with reasoning. Use CVSS where
the program uses it. Never inflate severity: credibility is the asset,
and an inflated report teaches the triager to discount your next one.
Severity follows demonstrated impact only.

### 4. Steps to reproduce

The most important section. A stranger must be able to follow it from
zero. Include the URL, parameter, HTTP method, account/role, the full
request or payload, and the browser/version. If the triager can't
reproduce it, the report dies here.

### 5. Proof of concept

Screenshot, short video, or minimal script. Redact sensitive data.
Prove the impact without causing damage. A PoC that shows the impact
(a session stolen, another account's data returned, funds moved on a
local fork) is worth more than ten paragraphs of explanation.

### 6. Impact

Realistic scenarios only. Who is affected, what data is at stake, what
an attacker can actually do. Don't speculate wildly — "an attacker
could theoretically..." is not impact, it's fiction.

### 7. Suggested fix

Short and concrete: validate input, encode output, check authorization
on the server, add rate limiting. Optional, but teams usually
appreciate it, and it shows you understand the bug.

### 8. Additional info

Test environment, date and time, CWE/OWASP references where relevant.

## Tone and habits

- One report = one bug (except a proven chain — explain the chain).
- Professional and neutral. Don't demand a bounty or name a price in
  the report.
- Focus on business impact: account takeover, data leak, and remote
  code execution are usually valued highest — because they matter
  most to the business.
- Always include repeatable evidence.
- Stop after sufficient proof; don't exploit further.
- Reply to clarification requests quickly and politely.
- Follow the disclosure policy. Never publish before permission.

## Common mistakes

- Title too generic.
- Reproduction steps ambiguous ("go to the site and try it").
- Reporting raw scanner output without verification.
- Inflated severity.
- Reporting out-of-scope or known issues.
- Spamming duplicate or low-quality reports.

## ⚠️ Firm warning: never mass-submit AI-generated reports

This needs to be said plainly, because it is the fastest way to destroy
a bounty career before it starts:

**Platforms detect and ban AI slop spam.** Triage teams and platforms
now recognize mass-submitted, AI-generated reports — vague titles,
theoretical impact, no real PoC, dozens of near-identical filings —
and they ban the accounts that submit them. A ban follows you: your
reputation on a platform is tied to your account, and a spam flag can
end your access to every program on it.

This kit exists to make you a *better hunter*, not a faster submitter.
The agent helps you recon, hypothesize, and draft — but **every report
must be human-verified and PoC-proven before it is sent**:

1. You (the human) reproduce the bug yourself, or personally verify
   the agent's PoC end to end.
2. You read the full report draft before submitting. If you can't
   explain the bug in your own words, don't submit it.
3. You submit one report at a time, only for findings that passed the
   triage gate.

If your agent drafts ten reports in an afternoon, nine of them are
probably not submittable. That is normal. Submit the one that is.

Next: [05 — Safety and Rules](05-safety-and-rules.md)
