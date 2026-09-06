# Verification-First Governance for LLM Agent Systems

> Treating agent output with CI-grade skepticism.

This repository holds a preprint and sanitized illustrative material for a design pattern
observed in a production multi-agent system we call **squad-harness**: a **verification
substrate** that sits beneath the (conventional) company-of-agents organization and keeps it
honest.

**Read online:** https://tedfernandes.github.io/squad-harness/

The central claim is deliberately narrow:

> The organizational layer of multi-agent systems (roles, coordinators, personas) is commodity.
> The verification layer beneath it is under-explored, and making **"not measured" a first-class
> outcome** is the single most valuable design decision in the system.

## The five mechanisms

1. **The third state.** Every gate returns pass / fail / *indeterminate*. "Not measured" is never
   rounded to "passed"; indeterminate is a distinct exit code and never auto-merges.
2. **The defect-ledger ratchet.** An LLM-free gate of 45 invariants, each one provenance-linked to
   a real, previously confirmed defect. Verification prefers *executing the artifact* over
   *string-matching its text* ("mention does not prove existence").
3. **The closing loop.** Each confirmed defect is compiled into either a new mechanical invariant
   or a new behavioral evaluation case, so audits raise a floor instead of aging into a report.
4. **Prompt-change governance.** Prompt edits ship only through a property-based
   evaluation-regression gate. Prompts are code under test.
5. **Untrusted context.** Agent-authored content injected back into the model is framed as
   reference, not instruction, and scanned for injection patterns.

## Read the paper

- Português (principal): [`paper.md`](paper.md) - preprint completo (v1.0).
- English: [`paper.en.md`](paper.en.md) - full preprint, English (v1.0).

Both versions are kept in sync; the Portuguese version (`paper.md`) is the primary version of record.

## Status and honesty note

This is a **preprint / experience report**, not peer-reviewed work, from a **single-operator**
deployment. The evaluation separates mechanisms that are *fully exercised* from those that are
*defined but lightly exercised*, and states threats to validity plainly (N=1, self-reported,
author is also evaluator). See the paper's Sections 5 and 6.

No client data, production-security detail, or verbatim operational configuration appears here.
All figures are anonymized and all code excerpts are sanitized illustrations of mechanism.

## Citing

If you reference this work, a `CITATION.cff` is provided (GitHub renders a "Cite this repository"
button). A DOI can be minted on release via Zenodo.

## License

- **Prose** (`paper.md`, this README): [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- **Code snippets** (illustrative): [MIT](LICENSE).
