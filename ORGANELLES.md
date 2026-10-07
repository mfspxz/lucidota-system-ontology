# ORGANELLES — one organ per primitive

Each primitive becomes a ToolOrganelle: the smallest unit that implements the
primitive's productions. Same contract shape as SHAMBHALA organelles (id,
handle, mutation class, valence, capability gate, input schema) — the pattern
Zackary already proved.

| Codon | Primitive | Mutation | Core productions |
|---|---|---|---|
| `in` | INFORMATION | ReadOnly | canonicalize, hash, compare, identify-sameness |
| `id` | IDENTITY | Write | claim, establish, attest-binding, revoke |
| `st` | STATE | Write | read, transition (via event), snapshot, diff |
| `ev` | EVENT | Write | append (immutable), order, replay, subscribe |
| `tm` | TIME | ReadOnly | now (per clock), expiry-check, lease, window |
| `re` | RELATIONSHIP | Write | assert (evidence-backed), query, traverse |
| `cp` | CAPABILITY | Write | grant, delegate, attenuate, invoke-check |
| `au` | AUTHORITY | ReadOnly | decide (policy evaluation), explain |
| `evd` | EVIDENCE | Write | record (with provenance), verify-shape, correlate |
| `po` | POLICY | ReadOnly | evaluate(identity, capability, evidence, context) |
| `ex` | EXECUTION | Write | run, sandbox, attest-run, meter |
| `rs` | RESOURCE | Write | account, quota, cheapest-satisfying-invariant |
| `bo` | BOUNDARY | ReadOnly | check-crossing, verify (or BOUNDARY_UNVERIFIED) |
| `pr` | PROTOCOL | ReadOnly | negotiate, validate-message, canonicalize |
| `ar` | ARTIFACT | Write | store (content-addressed), sign, verify-provenance |

## Composition rule

Surfaces are organelle *compositions*, not new organelles. `security` is not an
organelle — it is `id + cp + bo + po` wired together with `evd` feeding audit.
Any "subsystem" that cannot be expressed as a composition is either incoherent
or evidence of a missing primitive (file it as a finding, don't build a 26th box).

## The verifier as one organ

The current verifier work (R020, NRAS adapter, receipt minting) is the
`evd + re + au + po` composition — one organ in the larger machine, not the
machine itself. Its job in the organism: answer "what does this establish, what
relationship does it prove, what authorization does it NOT prove, what policy
decision follows" for any signed/attested/provenance-bearing thing.
