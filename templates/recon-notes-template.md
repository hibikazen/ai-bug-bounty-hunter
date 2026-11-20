# Recon Notes Template

One file per program. Keep it updated — the next hunt on the same
target starts here.

---

## Program

- **Program:** [name]
- **Platform:** [HackerOne / Bugcrowd / Immunefi / self-hosted / ...]
- **Program URL:** [link]
- **Date started:** [YYYY-MM-DD]

## Scope (quoted from the program page)

**In scope:**
- [asset 1]
- [asset 2]

**Out of scope:**
- [exclusion 1]
- [exclusion 2]

**Rules that matter:** [reward range, severity definitions, PoC
required? disclosure policy, anything unusual — quote, don't guess]

## Live assets

| Host | Status | What it is |
|---|---|---|
| [example.com] | [200] | [marketing site] |
| [api.example.com] | [200] | [REST API] |

## Tech stack

- **Frontend:** [framework, JS libraries]
- **Backend:** [language, framework]
- **Auth:** [provider / session / JWT / OAuth]
- **Infra:** [CDN, cloud, WAF]
- **Notable:** [anything with known CVE history, unusual deps]

## Attack surface map

| Feature | Needs auth? | User input? | Notes |
|---|---|---|---|
| [login] | [no] | [email, password] | [rate limited?] |
| [file upload] | [yes] | [file, filename] | [file types allowed?] |
| [API /users/{id}] | [yes] | [id in URL] | [IDOR candidate?] |

## Disclosed reports (what already paid)

| Bug class | Endpoint | Bounty (if public) | Lesson |
|---|---|---|---|
| [e.g. IDOR] | [endpoint] | [$X] | [what to try / avoid] |

## Known / acknowledged behavior (don't report)

- [behavior + where it's documented]

## Coverage ledger

| Asset / feature | Bug class | Verdict | Note |
|---|---|---|---|
| [asset / feature] | [class] | [Open / Killed / Confirmed] | [why] |

## Leads (ranked)

1. [Lead — feature + bug class + why it's promising]
2. [Lead]
3. [Lead]

## Findings

| ID | Bug class | Location | Status |
|---|---|---|---|
| [F-01] | [class] | [endpoint] | [Open / In triage / Reported / Killed] |
