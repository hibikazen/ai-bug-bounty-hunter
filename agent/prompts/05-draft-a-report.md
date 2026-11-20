# Starter Prompt 5 — Draft a Report

Paste this when a finding has passed the triage gate AND has a working
PoC. The draft is for the human to review — never send it without
reading it yourself first. Fill in the bracketed parts.

---

Draft a bug bounty report for the **[program name]** program on
**[platform]**, using the report template in this repo.

**Finding:** [bug class] in [exact endpoint/feature]
**Severity (defendable):** [Critical / High / Medium — with the CVSS
vector if the program uses CVSS]
**Steps to reproduce:** [paste the working repro]
**PoC:** [paste the PoC or its location: `findings/.../poc/`]
**Impact:** [who is affected, what an attacker can actually do — proven,
not hypothetical]
**Suggested fix:** [1–2 sentences, or "suggest one"]

Write the draft following these rules:

1. **Title formula:** `[Bug Class] in [Exact Endpoint/Feature] allows
   [attacker role] to [impact] [victim scope]`. Specific, impact-first.
2. **No theoretical language.** Never write "could potentially", "may
   allow", or "could be used to". Either it does the thing or it
   doesn't. Every claim must trace to the evidence.
3. **Steps a stranger can follow from zero.** URL, parameter, HTTP
   method, account/role, full request, expected result. Include the
   environment (browser, date).
4. **Realistic impact only.** Who is affected, what data or action is
   at stake, what an attacker can actually do. No wild speculation.
5. **Professional, neutral tone.** Don't demand a bounty or name a
   price. Don't oversell the severity — credibility is the asset.
6. **One issue per report.** This draft covers exactly one bug (or one
   proven chain — explain the chain).

Save the draft to `findings/[program]-[bug-class]/report-draft.md`.
After drafting, run the pre-submit checklist from the instruction file
(title / repro / evidence / severity / fix) and list anything that
fails — I will fix it before submitting. Do NOT submit anything.
