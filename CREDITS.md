# Credits

This kit is a synthesis of open work by other people. Nothing here is
presented as original where it was adapted. If this kit helps you, go
star and support the projects below.

## Methodology and workflows

| Project | Author | License | What was taken or adapted |
|---|---|---|---|
| [Agentic-Bug-Hunter](https://github.com/awarexone/Agentic-Bug-Hunter) | [awarexone](https://github.com/awarexone) | MIT | Core hunting methodology: scope-first rule, one bug class per pass, the 7-Question Gate, the 4 pre-submission gates, the never-submit list, kill-fast rules, report title formula, and CVSS guidance. Adapted into `agent/AGENT.md`, `docs/03-the-hunt-workflow.md`, `docs/04-writing-a-report.md`, and `templates/triage-checklist.md`. |
| [security-audit-skill](https://github.com/cloudflare/security-audit-skill) | [Cloudflare](https://github.com/cloudflare) | MIT | The 6-phase audit workflow (recon + coverage ledger, coverage-led hunting waves with critic passes, adversarial candidate validation, schema-validated findings, independent record verification, target-neutral reporting) and the coverage-ledger idea. Adapted for bounty hunting in `docs/03-the-hunt-workflow.md` and `agent/AGENT.md`. Described in Cloudflare's [Build your own vulnerability harness](https://blog.cloudflare.com/build-your-own-vulnerability-harness). |
| [bug-bounty-hunting-prompts](https://github.com/mdpsec/bug-bounty-hunting-prompts) | [mdpsec](https://github.com/mdpsec) | MIT | The independent triage gate (review as the platform's triager; never upgrade severity from a new angle found at the gate), the self-duplicate check (uncertainty is POSSIBLE_DUPLICATE, never NOT_DUPLICATE), and the submission floors (no Low/Informational, no pure denial-of-service). Adapted into `agent/AGENT.md` and `templates/triage-checklist.md`. |
| [Claude-BugHunter](https://github.com/elementalsouls/Claude-BugHunter) | [elementalsouls](https://github.com/elementalsouls) (Sachin Sharma) | MIT (code), CC BY 4.0 (content) | The disclosed-report pattern library concept (learn from paid findings before hunting a class) and the 2026 Web3 audit deltas (flash-loan / reentrancy / secondary-oracle classes still paying; EIP-1153, EIP-7702, ERC-4337, ZK-bridge, and LST-depeg notes; Immunefi PoC discipline). Adapted into `docs/03-the-hunt-workflow.md` and `docs/06-tools.md`. |
| [recon-skills](https://github.com/uphiago/recon-skills) | [uphiago](https://github.com/uphiago) (Hiago Felipe) | MIT | Recon workflow structure (meta playbooks, discovery and enumeration skills) and the evidence standard (a response code alone never proves a vulnerability). Adapted into `docs/03-the-hunt-workflow.md` and `agent/prompts/01-first-recon.md`. |
| [REA — Reverse Engineer Anything](https://github.com/morluto/rea) | [morluto](https://github.com/morluto) | MIT | The reverse-engineering lane: EVM bytecode interface inference, native binary static inspection, and JS/Electron app analysis for closed-source targets. Referenced in `docs/06-tools.md`. |

## Platforms and tooling references

| Project | Author | License | What was taken or adapted |
|---|---|---|---|
| [bug-bounty-platforms](https://github.com/disclose/bug-bounty-platforms) | [disclose](https://github.com/disclose) | CC0 1.0 | The platform directory seed for `docs/07-platforms.md` (platform names, URLs, regions, program types). Note: that list can go stale — verify a program is alive before hunting. |
| [Cybermes](https://github.com/Zyrexnn/Cybermes) | [Zyrexnn](https://github.com/Zyrexnn) | Apache 2.0 | DeFi attack-pattern references (`defi-attack-patterns` and `smart-contract-vulnerabilities` skills: MEV, precision loss, governance, bridge patterns, proxy storage collisions). Referenced in `docs/06-tools.md`. |
| [BurpAPISecuritySuite](https://github.com/Teycir/BurpAPISecuritySuite) | [Teycir](https://github.com/Teycir) (Teycir Ben Soltane) | MIT | API security testing approach (Burp Suite extension for API-focused checks). Referenced in `docs/06-tools.md`. |
| [bugbounty-lab101](https://github.com/DevCop95/bugbounty-lab101) | [DevCop95](https://github.com/DevCop95) | MIT | Workspace organization ideas for a HackerOne-focused hunting workspace. Informed the templates layout. |

## Report structure

The report structure in `docs/04-writing-a-report.md` and
`templates/report-template.md` (title, summary, severity with reasoning,
steps to reproduce, PoC, impact, suggested fix) is adapted from a
report-writing guide shared with the author, combined with the report
templates and human-tone guidance of Agentic-Bug-Hunter's report-writing
skill (see above).

## Learning resources mentioned in the docs

- [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) and [OWASP Top 10](https://owasp.org/www-project-top-ten/) — OWASP Foundation.
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) — PortSwigger (free interactive labs).
- [Hacker101](https://www.hacker101.com/) — HackerOne (free video lessons and CTFs).
- [HackTricks](https://book.hacktricks.wiki/) — Carlos Polop (community wiki of pentest techniques).
- [sealevel-attacks](https://github.com/coral-xyz/sealevel-attacks) — Coral / Anchor maintainers (curated Solana attack PoCs).
- [Foundry Book](https://book.getfoundry.sh/) — Foundry contributors (smart-contract testing toolchain docs).

Tool authors are credited inline in `docs/06-tools.md` next to each tool.
