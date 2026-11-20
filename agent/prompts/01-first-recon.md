# Starter Prompt 1 — First Recon of a Target

Paste this to your agent after you have picked a program and confirmed
its scope. Fill in the bracketed parts.

---

I want to hunt the bug bounty program **[program name]** on **[platform,
e.g. HackerOne]**.

**Confirmed in-scope assets (test ONLY these):**
- [asset 1, e.g. example.com]
- [asset 2, e.g. api.example.com]
- [add more as listed on the program page]

**Out of scope (do NOT touch):**
- [anything the program page excludes]

Do a passive-first recon pass and save the notes to
`recon/[program-name]-recon-notes.md` (use the template in this repo
if you have it). Cover:

1. **Program rules**: reward range, severity definitions, report
   requirements (is a PoC required?), disclosure policy, and anything
   explicitly excluded. Quote the program page; don't guess.
2. **Subdomains and live hosts**: enumerate subdomains of the in-scope
   domains from public sources, then check which are live. List every
   live host with its status code and what it appears to be.
3. **Tech stack**: what the target runs (frameworks, languages, auth
   provider, CDN, JS libraries) — from headers, public docs, and JS
   bundles. Note anything with a known CVE history.
4. **Attack surface map**: main features (login, signup, payments,
   file upload, search, API endpoints, GraphQL?), which need auth,
   and where user input flows. Rank the top 3 features most likely to
   hold a bug, and say why.
5. **Disclosed reports**: find at least 3 disclosed reports for this
   program if any exist. Note which bug classes already paid out and
   which look already hunted to death.
6. **Known issues**: check the target's changelog, public issue
   tracker, and docs for acknowledged behavior — so we don't report
   something they already know about.

Rules: passive recon only in this pass — no requests that change state,
no fuzzing, no scanning behind login. Do NOT probe anything outside the
in-scope list above. End with a short list of the 3 most promising
leads and which bug class each one suggests.
