# Starter Prompt 3 — Triage-Gate Check on a Candidate Finding

Paste this when you think you found something and want a hard,
independent check before writing a report. Fill in the bracketed parts.

---

Run the full triage gate on this candidate finding for the
**[program name]** program. Be adversarial: your job is to try to KILL
it, not to cheer it on.

**Candidate finding:**
- Bug class: [e.g. IDOR]
- Location: [exact endpoint / feature]
- What I did: [the exact request, copy-paste ready]
- What happened: [the exact response / observed behavior]
- Claimed impact: [what an attacker gains]

**Program scope (in-scope assets):**
- [list]

**My evidence so far:** [paste request/response pairs, screenshots
described, PoC output — whatever you have]

Check, in order:

1. **7-Question Gate.** Answer Q1–Q7 from the instruction file, in
   order, one wrong answer kills it. For Q1, fill in the full template
   (setup / request / result / impact / cost). If any question can't be
   answered from the evidence, say which one and what evidence is
   missing.
2. **Identity check.** Which account found this? Does it reproduce with
   no auth? Under a different account I own? After logout? If it only
   reproduces under one identity, say so.
3. **Known-issue check.** Is this documented behavior, a known issue, or
   already in the program's disclosed reports? Search what you can.
4. **Never-submit check.** Is this on the never-submit list without a
   proven chain?
5. **Verdict.** One of: SUBMIT (with the severity you can defend),
   DOWNGRADE (to what, and why), NEEDS_MORE_PROOF (exactly what proof),
   or KILL (with the reason). If the verdict is SUBMIT, also run the
   self-duplicate check against my earlier reports to this program:
   [list them, or say "none yet"].
