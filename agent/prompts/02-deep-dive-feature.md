# Starter Prompt 2 — Deep-Dive a Feature

Paste this when recon has surfaced a promising feature and you want to
go deep on one bug class. Fill in the bracketed parts.

---

Deep-dive the **[feature, e.g. password reset / file upload / coupon
system]** on **[in-scope asset]** for the **[program name]** program.

**Bug class to hunt:** [one class, e.g. IDOR / broken access control /
race condition / SSRF / business logic]

**Scope reminder (test ONLY these):**
- [in-scope assets]

Context from recon: [paste the relevant recon notes — endpoints,
parameters, auth behavior, anything interesting].

Work through it like this:

1. **Map the feature first.** List every endpoint, parameter, and state
   change involved. Who can call each one (anonymous / logged-in user /
   admin)? What data goes in, what comes out?
2. **Hypothesize.** Based on how the feature works, write down 2–4
   specific hypotheses of the form "If I do X, then Y happens, which
   would mean Z impact". Rank them by expected impact.
3. **Test the top hypothesis.** Use my own test accounts only
   ([attacker account] and [victim account] — both mine). Keep requests
   minimal and reversible. Record the exact request and response for
   anything interesting.
4. **For each result, say plainly:** confirmed (with evidence), killed
   (with the reason), or needs a different angle (with what you'd try
   next). Don't oversell a maybe.
5. **If something confirms**, probe sibling endpoints in the same
   module for a second instance before we report the first one alone.

Rules: no denial-of-service testing, no touching other users' data, stop
after sufficient proof. If a hypothesis needs an account or access level
I don't have, say so instead of working around it.
