# Triage Checklist

Run this on every candidate finding BEFORE writing a report. One wrong
answer in the 7-Question Gate = kill the finding and move on.

## 7-Question Gate (in order)

- [ ] **Q1 — Exploitable RIGHT NOW?** I can write the full template:
  setup (what account/access), the exact request (method, URL,
  headers, body — copy-paste ready), the result (what data/action the
  response proves), the real-world impact, and the cost in time/money.
  If I can't write the request, the finding dies here.
- [ ] **Q2 — Impact on the program's accepted list?** Checked the
  program page's vulnerability types and exclusions. The bug does not
  map to a listed exclusion.
- [ ] **Q3 — Root cause in an in-scope asset?** In-scope domain,
  production asset (not staging/dev unless explicitly in scope), not a
  third-party service.
- [ ] **Q4 — No unrealistic privileged access needed?** Not "admin can
  do X". Not requiring a compromised victim account or physical access.
- [ ] **Q5 — Not already known / accepted behavior?** Searched
  disclosed reports, changelog, docs, and public issues. Not
  acknowledged, not a documented design decision.
- [ ] **Q6 — Impact proven beyond "technically possible"?** XSS shows
  session theft, not `alert(1)`. SSRF reaches internal data, not a DNS
  ping. SQLi returns real rows, not an error string. IDOR returns
  another user's actual data, not a 200.
- [ ] **Q7 — Not a known-invalid class?** Not on the never-submit list
  without a proven exploit chain.

## Identity check (auth-related findings)

- [ ] Which account found this: [attacker / victim / anonymous]
- [ ] Reproduces with no auth? [yes / no]
- [ ] Reproduces under a different account I own? [yes / no]
- [ ] Survives logout / expired session? [yes / no]

## 4 pre-submission gates

**Gate 0 — Reality check**
- [ ] Bug is REAL — confirmed with actual requests, not code reading alone
- [ ] Bug is IN SCOPE — checked the program scope page explicitly
- [ ] Reproducible from scratch, starting from a fresh session
- [ ] Evidence ready — screenshot, response body, or video

**Gate 1 — Impact validation**
- [ ] I can answer "What can the attacker DO that they couldn't before?"
- [ ] The answer is more than "see non-sensitive data"
- [ ] There is a real victim: another user's data, company data, or
      financial loss
- [ ] It doesn't rely on the victim doing something unlikely

**Gate 2 — Deduplication check**
- [ ] Searched the program's disclosed reports for this bug class/endpoint
- [ ] Searched the target's GitHub issues / changelog
- [ ] Read the 5 most recent disclosed reports for this program
- [ ] Not a "known issue" in their changelog or public docs

**Gate 3 — Report quality**
- [ ] Title: [Bug Class] in [Endpoint] allows [actor] to [impact]
- [ ] Steps to reproduce: copy-pasteable request
- [ ] Evidence: screenshot/video of actual impact (not just a 200)
- [ ] Severity: matches CVSS AND the program's severity definitions
- [ ] Remediation: 1–2 sentences of concrete fix
- [ ] No "could potentially" or "may allow" anywhere

## Independent triage gate

- [ ] Reviewed the draft as the platform's first-line triager (fresh
      eyes — not the person/agent who hunted it)
- [ ] Every claim re-verified against the evidence
- [ ] Unsupported impact downgraded or removed
- [ ] No severity upgrade from a new angle found at the gate (new
      angles are spin-off leads, recorded separately)

## Self-duplicate check

Compare against my own prior submissions to this program AND other
reports from this hunt. Compare: underlying defective behavior,
affected component + trust boundary, exploit primitive + attacker
prerequisites, proven impact, and whether the same fix would cover
both.

- [ ] Verdict: [NOT_DUPLICATE / POSSIBLE_DUPLICATE / LIKELY_DUPLICATE]
- [ ] Uncertainty is POSSIBLE_DUPLICATE, never NOT_DUPLICATE
- [ ] If possible/likely duplicate: does the new report contain proven
      information that would materially strengthen the canonical
      report? If yes, fold it in as an update instead of filing new.

## Submission floors

- [ ] Final severity is NOT Low or Informational
- [ ] Impact is NOT pure denial-of-service / availability-only

## Verdict

- [ ] **SUBMIT** at severity: [Critical / High / Medium]
- [ ] **DOWNGRADE** to: [severity + reason]
- [ ] **NEEDS_MORE_PROOF**: [exactly what proof]
- [ ] **KILL**: [reason]
