# Application of Rigor Findings R-1–R-12 to system-ontology

Repo: `~/workspace/system-ontology`  
Date: 2026-10-10  
**Auditor:** brutal-audit rollout slice 7/8 (parent orchestrator)
Repo type: DOCS repo — no code, no tests  
Primary files: `ONTOLOGY.md`, `DERIVATIONS.md`, `COVERAGE.md`, `ORGANELLES.md`, `RELATION-TO-GO50.md`, `ROADMAP.md`, `README.md`, `organelles/`

## Disposition Table

| Finding | Applicability | Disposition |
|---|---|---|
| R-1 | Applies to derivation claims | Instance-only; one-book refutation; no PROVEN/FIXED without re-attack |
| R-2 | Applies | Ontology claims require explicit bounds |
| R-3 | N/A | No hash-chained log |
| R-4 | Applies | ROADMAP triage with budgets |
| R-5 | N/A | No signature/denylist/strip surface |
| R-6 | N/A | No detectors |
| R-7 | N/A | No tests |
| R-8 | Mostly N/A | No provenance artifacts; docs are asserted, not proven |
| R-9 | N/A | No claim log |
| R-10 | Applies | Timestamp/archive policy required |
| R-11 | Applies | Explicit UNKNOWN list required |
| R-12 | Applies | Source citations required |

## R-1 — Derivation claims are instance-only; no PROVEN/FIXED without re-attack

**Applicability:** N/A as code. Applies to `DERIVATIONS.md`.

**Label:** UNKNOWN for derivation durability.

**Policy:** Every claim that X derives from Y is an instance claim only. A refutation of that derivation must be recorded against the original derivation in the same book, using a `SUPERSEDED-BY-BYPASS` analogue. No derivation may be marked PROVEN or FIXED without a dedicated re-attack result.

## R-2 — Honest bounds on structural claims

**Applicability:** APPLIES. `ONTOLOGY.md` makes structural claims about what the system IS.

**Label:** UNKNOWN until `COVERAGE.md` bounds are audited.

**Policy:** Each major structural claim must carry its bound: what the ontology asserts and what it does not cover. `COVERAGE.md` is the natural home. If `COVERAGE.md` lacks explicit non-goals and non-covered system areas, that is the finding. Freeze hardening past the declared bound.

## R-3 — Hash-chained logs and tamper-evident claims

**Applicability:** N/A. No hash-chained log exists in this repo.

**Label:** N/A.

**Policy:** Any future hash-chained log must have an out-of-band head copy that the repo’s own machinery cannot rewrite. Until then, do not call anything tamper-evident. Document the same-VM limitation.

## R-4 — Backlog triage

**Applicability:** APPLIES. `ROADMAP.md` is the backlog.

**Label:** UNKNOWN until every ROADMAP item is triaged.

**Policy:** Triage every `ROADMAP.md` item as `wont-fix` with a complexity budget or `queued` with a complexity budget. Standing HIGH items get `wont-fix` with complexity budget or are fixed. Unbounded roadmap growth is the failure mode.

## R-5 — Signature/denylist/strip games

**Applicability:** N/A. No signature, denylist, or stripping logic in a DOCS repo.

**Label:** N/A.

**Policy:** If any document later describes such mechanisms, they are best-effort with a FIXED complexity budget and redirect to structural answers.

## R-6 — Detectors need named consumer and enforcement gate

**Applicability:** N/A. No detectors exist.

**Label:** N/A.

**Policy:** No detector-like prose may stand without a named consumer and an enforcement gate. Wire it or delete it.

## R-7 — Property tests vs change-detection tests

**Applicability:** N/A. No test suite exists.

**Label:** N/A.

**Policy:** If tests are introduced, separate property tests from change-detection tests, label them explicitly, and never rewrite a property-test expectation without adversarial sign-off.

## R-8 — No unsigned provenance that invites misreading

**Applicability:** Mostly N/A. No provenance artifacts exist.

**Label:** UNKNOWN for docs that may imply machine verification.

**Policy:** Any diagram or doc that looks authoritative must state plainly: docs are asserted, not proven; no machine-verification is implied. Do not present unsigned provenance as if it verifies anything. Sign/anchor or declare honestly-unsigned with verification power stated plainly.

## R-9 — Claim log discipline

**Applicability:** N/A. No claim log exists; the ontology itself is the claim set.

**Label:** N/A.

**Policy:** If a claim log is introduced, freeze its schema: enum verdicts only, and include `SUPERSEDED-BY-BYPASS`. Ontology versioning is the current schema discipline.

## R-10 — Record-keeping in the same motion as the event

**Applicability:** APPLIES to dated docs and forward-looking ROADMAP items.

**Label:** UNKNOWN for ROADMAP timestamps.

**Policy:** Dated docs were same-motion records for their era. Forward-looking `ROADMAP.md` items must be timestamped or they rot. Declare archival policy: each event recorded in the same motion as the event, or explicitly declared archival.

## R-11 — Explicit UNKNOWN list

**Applicability:** APPLIES.

**Label:** UNKNOWN.

**Policy:** List as UNKNOWN where not re-verified. No “probably” may be recorded as PROVEN. The UNKNOWN list is below.

## R-12 — No unsourced oral footnotes

**Applicability:** APPLIES to `RELATION-TO-GO50.md` and `DERIVATIONS.md` claims about external systems.

**Label:** UNKNOWN until citations are audited.

**Policy:** Cite sources for claims about external systems. Unsourced assertions are UNVERIFIED. Evidence or UNVERIFIED; no unsourced oral footnotes.

## Changes made today

None. Policy pass only. No repo files were edited. This `AUDIT-APPLICATION.md` is the deliverable.

## Commits

TBD.

## Test counts

Tests run: 0.  
Test suite: none.  
`system-ontology` is a DOCS-only repo. No code or tests exist per its own file layout and commit history.

## UNKNOWN list

- Which ontology claims have been re-verified against the current system: UNKNOWN.
- Freshness of `RELATION-TO-GO50.md` claims relative to the current external system: UNKNOWN.
- Validity of `ROADMAP.md` items: UNKNOWN.
- Whether `COVERAGE.md` currently lists explicit non-goals/non-coverage bounds: UNKNOWN.
- Whether `RELATION-TO-GO50.md` and `DERIVATIONS.md` have source citations for external-system claims: UNKNOWN.
- Whether any doc or diagram implies machine verification or tamper-evidence: UNKNOWN.

## Wont-fix / backlog triage

- `ROADMAP.md`: assign every item `wont-fix` with complexity budget or `queued` with complexity budget.
- Stale claims: if not re-verified, declare archival. Do not carry stale claims as current PROVEN.
- New ROADMAP items must carry a timestamp and complexity budget at creation.
- `COVERAGE.md`: add explicit non-goals/non-coverage bounds if absent.

