# Starter Prompt 4 — Build a PoC

Paste this when a finding has passed the triage gate and you need a
clean, minimal proof of concept. Fill in the bracketed parts.

---

Build a minimal proof of concept for this finding for the
**[program name]** program.

**Finding:** [bug class] in [exact endpoint/feature]
**Impact to prove:** [e.g. "an authenticated user can read any other
user's invoice by changing the id parameter"]
**Repro steps that already work:** [paste the working request/response]

Requirements for the PoC:

1. **Minimal.** The smallest thing that proves the impact — a single
   curl command, a short script, or a few clicks. No extra tooling,
   no dependencies the triager can't install in a minute.
2. **Self-contained and safe.** It must run against the in-scope target
   using my own test accounts only ([attacker account] / [victim
   account] — both mine). It must not touch other users' data, must not
   change state beyond what's needed to prove the impact, and must
   include a cleanup step if it creates anything.
3. **Shows the impact, not just the request.** The output must make the
   impact visible: the other user's data in the response (redacted to
   the minimum needed), the state change, the error that proves the
   point. A bare `200 OK` is not a PoC.
4. **Reproducible from zero.** A stranger with two fresh test accounts
   should be able to follow it. Include setup (what accounts, what
   data to create first), the exact commands, and the expected output.
5. **Redacted.** No real user data, no secrets, no session tokens in
   the PoC or its output. Use placeholder values and note where the
   triager substitutes their own.

For smart-contract findings instead: write a single Foundry test
(`forge test`) that proves the impact with an explicit assertion on the
drained balance, minted token, or corrupted state — runnable on a local
fork, never on mainnet or testnet.

Save the PoC to `findings/[program]-[bug-class]/poc/` and give me the
exact commands to run it. Then run it once yourself to confirm it works
end to end, and report the result honestly.
