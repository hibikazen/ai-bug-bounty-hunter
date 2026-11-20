# 07 — Platforms

A directory of bug bounty platforms. One line each: what it is, what
it focuses on, and what to check before hunting there.

> **Read this first.** Fees, KYC requirements, and payout terms vary
> by *program*, not just by platform — and they change. Nothing here
> is a promise about a specific program. Always check the program page
> itself before hunting. Platform lists also go stale: verify a program
> is alive today (see [01 — Picking Your First Program](01-picking-your-first-program.md)).

## General (web, mobile, APIs)

| Platform | Focus | Notes |
|---|---|---|
| [HackerOne](https://hackerone.com) | The largest general platform; web, mobile, APIs, and more | Free to join. Reputation (Signal) gates access to some programs; new accounts start with a small number of trial reports on some programs — check the program page. Has disclosed reports to learn from. |
| [Bugcrowd](https://bugcrowd.com) | General crowdsourced security; public and private programs | Free to join. Check the program page for scope and payout terms. |
| [YesWeHack](https://yeswehack.com) | European platform; public and private programs | Free to join. Check the program page for scope and terms. |
| [Intigriti](https://intigriti.com) | European platform; public and private programs | Free to join. Check the program page for scope and terms. |
| [Synack](https://synack.com) | Vetted, invite-only researcher community; private programs | Entry is application-based and vetted — not a first-program pick. Check the site for current requirements. |
| [Open Bug Bounty](https://openbugbounty.org) | Free, open vulnerability disclosure for websites (VDP-style) | Public disclosure coordination; not all listings pay bounties — check each listing. |
| [BugBase](https://bugbase.ai) | General platform; private + public programs | Check the program page for scope, fees, and terms. |

## Web3 (smart contracts, DeFi, bridges)

| Platform | Focus | Notes |
|---|---|---|
| [Immunefi](https://immunefi.com) | The largest Web3 bounty platform; smart contracts, DeFi, bridges | Filing requires proof-of-humanity verification (a Human Passport score or a one-time "Skin in the Game" fee). PoC required for all severities; mainnet/testnet testing is prohibited — local forks only. Check the program page for the severity matrix and payout terms. |
| [Remedy](https://hunt.r.xyz) | Web3 programs (also at r.xyz) | Check the program page: some programs show a KYC badge, some don't; payout currency and PoC requirements vary by program. |
| [HackenProof](https://hackenproof.com) | Web3 programs | Some programs charge a per-report submission fee — check the program page. KYC may be required at payout stage. |
| [Sherlock](https://app.sherlock.xyz) | Auditing contests (time-boxed, competitive) | Contest format, not continuous bounties — check the contest page for the stake/fee and payout structure. |
| [Cantina](https://cantina.xyz) | Competitive audits and bounties | Check the competition page for format, fees, and terms. |
| [CodeHawks](https://codehawks.cyfrin.io) | Competitive audits (Cyfrin) | Contest format — check the contest page for terms. |
| [AuditOne](https://auditone.io) | Audits and bounties | Check the program page for scope and terms. |
| [BugRap](https://bugrap.io) | Web3 bounties | Check the program page for scope and terms. |
| [Hashlock](https://hashlock.com) | Audits and bug bounties | Check the program page for scope and terms. |

## Dead or wound down — do not hunt

These still appear on older lists. Verify before trusting any list.

| Platform | Status |
|---|---|
| Code4rena (code4rena.com) | Wound down in May 2026. |
| Hats Finance (hats.finance) | Closed in December 2025. |

## Self-hosted programs (no platform)

Many projects run their own bounty program from a `SECURITY.md` file
in their repo or a page on their own site. Terms vary completely:
read the project's own page, note the contact method (usually an
email or a GitHub security advisory), and confirm scope and payout
terms in writing before hunting. Self-hosted programs are often
free to enter with no KYC — check the page.

## Choosing between platforms

- **First hunt:** a general platform (HackerOne, Bugcrowd, YesWeHack,
  Intigriti) with an open, free program and disclosed reports.
- **Web3 / smart contracts:** Immunefi or Remedy — but read the
  verification and PoC requirements first; they are stricter than
  web programs.
- **Learning the craft:** any platform's disclosed reports are free
  study material. Read them before you hunt.

Platform list seeded from [disclose/bug-bounty-platforms](https://github.com/disclose/bug-bounty-platforms)
(CC0 1.0) — see [CREDITS.md](../CREDITS.md).
