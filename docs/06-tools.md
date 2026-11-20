# 06 — Tools

A tooling map by lane. You don't need all of these — start with the
web recon lane, add the rest when a hunt needs them. Every link was
verified. Install from the project's own releases, never from a random
mirror.

## Web recon (finding the surface)

| Tool | What it does | Author / link |
|---|---|---|
| subfinder | Fast passive subdomain enumeration | ProjectDiscovery — <https://github.com/projectdiscovery/subfinder> |
| httpx | Probes live hosts: status, title, tech stack | ProjectDiscovery — <https://github.com/projectdiscovery/httpx> |
| katana | Crawls a site and maps URLs, endpoints, JS files | ProjectDiscovery — <https://github.com/projectdiscovery/katana> |
| nuclei | Template-based vulnerability scanner (thousands of checks) | ProjectDiscovery — <https://github.com/projectdiscovery/nuclei> |
| ffuf | Fast web fuzzer for directories, parameters, and vhosts | ffuf team — <https://github.com/ffuf/ffuf> |
| nmap | Port and service discovery | Nmap Project — <https://nmap.org/> |

Rule: a scanner finding is a hypothesis, not a bug. Every nuclei hit
needs manual verification and a PoC before it becomes a report.

## Web vulnerabilities (proving the bug)

| Tool | What it does | Author / link |
|---|---|---|
| Burp Suite | Intercepting proxy — see, replay, and modify requests (Community Edition is free) | PortSwigger — <https://portswigger.net/burp> |
| OWASP ZAP | Free, open-source web app scanner and proxy | OWASP — <https://www.zaproxy.org/> |
| BurpAPISecuritySuite | Burp extension for API-focused security checks | Teycir Ben Soltane — <https://github.com/Teycir/BurpAPISecuritySuite> |

## Smart contracts (Web3)

| Tool | What it does | Author / link |
|---|---|---|
| Foundry | Solidity toolchain: `forge` (test/fuzz), `cast` (chain queries), `anvil` (local node) | Foundry contributors — <https://getfoundry.sh/> (docs: <https://book.getfoundry.sh/>) |
| Slither | Static analyzer for Solidity — flags common bug patterns | Trail of Bits (Crytic) — <https://github.com/crytic/slither> |
| Echidna | Property-based fuzzer for Solidity | Trail of Bits (Crytic) — <https://github.com/crytic/echidna> |
| Mythril | Symbolic execution for EVM bytecode | ConsenSys — <https://github.com/ConsenSys/mythril> |
| sealevel-attacks | Curated Solana attack PoCs by the Anchor maintainers | Coral — <https://github.com/coral-xyz/sealevel-attacks> |
| Tenderly | Forking and transaction simulation for EVM chains | Tenderly — <https://www.tenderly.co/> |

PoC discipline for Web3: a Foundry PoC is usually required, and it
should be a single `forge test` invocation proving the impact with an
explicit assertion — runnable on a local fork, never on mainnet or
testnet.

For DeFi-specific attack depth (MEV, precision loss, governance,
bridge patterns, proxy storage collisions), see the
`defi-attack-patterns` and `smart-contract-vulnerabilities` skills in
[Cybermes](https://github.com/Zyrexnn/Cybermes) (Zyrexnn, Apache 2.0).

## Mobile

| Tool | What it does | Author / link |
|---|---|---|
| MobSF | Automated static + dynamic analysis for Android/iOS apps | MobSF team — <https://github.com/MobSF/Mobile-Security-Framework-MobSF> |
| JADX | Decompiles Android DEX bytecode to Java | skylot — <https://github.com/skylot/jadx> |
| apktool | Decodes APK resources for inspection | iBotPeaches — <https://apktool.org/> |
| Frida | Dynamic instrumentation toolkit — hook and inspect running apps | Frida — <https://frida.re/> |

## Reverse engineering (closed-source targets)

| Tool | What it does | Author / link |
|---|---|---|
| REA | Reverse-engineer anything: EVM bytecode interface inference, native binary inspection, JS/Electron app analysis (CLI + MCP) | morluto — <https://github.com/morluto/rea> (npm package `rea-agents`) |
| Ghidra | Free, open-source reverse-engineering suite (decompiler included) | NSA — <https://github.com/NationalSecurityAgency/ghidra> |
| WABT | WebAssembly Binary Toolkit — inspect and decompile WASM | WebAssembly community — <https://github.com/WebAssembly/wabt> |

Use reverse engineering when the source is unavailable and the answer
depends on a shipped artifact: deployed-but-unverified bytecode, a
closed-source binary, or a packaged app. Treat inferred results
(selectors, function names) as inferences, not verified facts, until
cross-checked.

## Learning (free)

| Resource | What it is | Link |
|---|---|---|
| OWASP Web Security Testing Guide | The standard methodology for testing web apps | <https://owasp.org/www-project-web-security-testing-guide/> |
| OWASP Top 10 | The ten most critical web risks, with examples | <https://owasp.org/www-project-top-ten/> |
| PortSwigger Web Security Academy | Free interactive labs for every major web bug class | <https://portswigger.net/web-security> |
| Hacker101 | Free video lessons + CTFs from HackerOne | <https://www.hacker101.com/> |
| HackTricks | Community wiki of pentest techniques | <https://book.hacktricks.wiki/> |

## Methodology skill packs (for agents that support skills)

- [Agentic-Bug-Hunter](https://github.com/awarexone/Agentic-Bug-Hunter)
  (awarexone, MIT) — CLI + skill bundle, recon to report.
- [Claude-BugHunter](https://github.com/elementalsouls/Claude-BugHunter)
  (elementalsouls, MIT code / CC BY 4.0 content) — 83 skills, 681
  disclosed-report patterns.
- [recon-skills](https://github.com/uphiago/recon-skills)
  (uphiago, MIT) — 41 recon skills and playbooks.
- [security-audit-skill](https://github.com/cloudflare/security-audit-skill)
  (Cloudflare, MIT) — 6-phase audit workflow.

These are the sources this kit is built on. See
[CREDITS.md](../CREDITS.md) for the full list.

Next: [07 — Platforms](07-platforms.md)
