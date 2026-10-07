# System Ontology — the whole-project scaffold

**Status:** scaffold v0.1 (2026-10-06) | **Author:** Zackary Camoran / Lucidota
**Purpose:** the minimum primitives from which the major concerns of modern software can be represented — and the map of where the current build stands against them.

## The organism (Zackary's model)

```
                         ┌─────────────────────┐
                         │      PRODUCT        │
                         └──────────┬──────────┘
                                    │
       ┌───────────────┬────────────┼───────────────┐
       ▼               ▼            ▼               ▼
   EXPERIENCE       DOMAIN       COMPUTING       TRUST
       │               │            │               │
       ▼               ▼            ▼               ▼
    UI/API         data/model     runtime        verifier
       │               │            │               │
       └───────────────┴─────┬──────┴───────────────┘
                             ▼
                       OPERATING SYSTEM
                             │
       ┌─────────┬──────────┼──────────┬─────────┐
       ▼         ▼          ▼          ▼         ▼
    security   scaling   reliability  ops     economics
       │         │          │          │         │
       └─────────┴──────────┼──────────┴─────────┘
                             ▼
                       OBSERVABILITY
                             │
                             ▼
                        GOVERNANCE
                             │
                             ▼
                         EVOLUTION
```

## Files

| File | Contents |
|---|---|
| `ONTOLOGY.md` | The 15 primitives — definitions, non-derivability notes |
| `DERIVATIONS.md` | The 25 surfaces as compositions of primitives (the derivation algebra) |
| `COVERAGE.md` | Current build mapped per surface: strong / partial / zero, with evidence |
| `ORGANELLES.md` | One organelle per primitive — contracts, not implementations |
| `ROADMAP.md` | Attack order for the biggest holes |
| `RELATION-TO-GO50.md` | How this relates to the GO-50 operator ontology (different ring) |

## The ruling discipline

Reduce aggressively to the primitives. Then **preserve the distinctions that cannot safely be reduced.** Over-reduction that erases a load-bearing distinction is a bug.

Substrate core loop: `information → observe → record → relate → calculate → decide`

Canonical laws:
- Names don't create provenance.
- Assertions don't create evidence.
- Observation doesn't create authority.
- A verifier that cannot reject is not a verifier.
