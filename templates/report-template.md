# Report Template

One report = one bug (or one proven chain — explain the chain).
Fill in every section. Delete nothing; write "N/A" with a reason if a
section truly doesn't apply.

---

## Title

[Bug Class] in [Exact Endpoint/Feature] allows [attacker role] to
[impact] [victim scope]

Example: "IDOR in /api/v2/invoices/{id} allows an authenticated user
to read any customer's invoice data"

## Summary

[2–3 sentences: what the bug is, where it is, what happens because
of it.]

## Severity

Proposed severity: [Critical / High / Medium / Low]

Reasoning: [why this severity — tie it to the demonstrated impact and
the program's severity definitions, not to the bug class alone.]

CVSS (if the program uses it): [score + vector, e.g. 6.5
AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:N/A:N]

## Steps to reproduce

[A stranger must be able to follow these from zero. Number each step.]

1. [Setup: accounts needed, data to create first]
2. [Step: exact URL, method, parameters]
3. [Step: exact request — paste the full request or payload]
4. [Expected result vs actual result]

Environment: [browser + version, or tool + version]
Date/time tested: [YYYY-MM-DD, timezone]

## Proof of concept

[Attach or link: screenshot, short video, minimal script, or curl
commands. Redact sensitive data — no real user data, no secrets, no
session tokens.]

[For smart contracts: a single `forge test` proving the impact, run
on a local fork.]

## Impact

[Realistic scenarios only. Who is affected? What data or action is at
stake? What can an attacker actually do with this — proven, not
hypothetical?]

## Suggested fix

[1–2 sentences of concrete remediation, e.g. "Check that the
authenticated user owns the requested invoice on the server before
returning it."]

## Additional information

- CWE: [e.g. CWE-639]
- OWASP reference: [e.g. Broken Access Control]
- References: [links to docs or similar disclosed reports, if any]

---

## Pre-submit checklist (delete before sending)

- [ ] Title follows the formula and names the impact
- [ ] Steps to reproduce are copy-pasteable from zero
- [ ] PoC shows the impact, not just a request
- [ ] Severity matches demonstrated impact (not inflated)
- [ ] No "could potentially" / "may allow" language anywhere
- [ ] Sensitive data redacted from all evidence
- [ ] Triage checklist (`triage-checklist.md`) completed
- [ ] I (the human) read the full draft before submitting
