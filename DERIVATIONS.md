# DERIVATIONS — the 25 surfaces as primitive compositions

The derivation algebra: each surface = a composition of primitives. If a surface
cannot be expressed, either the surface is incoherent or a primitive is missing —
both are findings.

## Compositions

| # | Surface | Derivation |
|---|---|---|
| 1 | security | identity + capability + boundary + policy (+ evidence for audit) |
| 2 | identity (arch) | identity + authentication(protocol) + attestation(evidence) + authorization(policy) + action(execution) + receipt(evidence) |
| 3 | data | information + state + event + relationship + policy (lifecycle) + boundary (ownership) |
| 4 | distributed systems | state + event + time + protocol + relationship (topology) |
| 5 | scalability | resource + state + execution + topology |
| 6 | reliability | state + event + time + redundancy (resource × N) |
| 7 | observability | event + evidence + time |
| 8 | testing | execution + event + policy (oracle) + evidence |
| 9 | supply chain | artifact + event + identity + relationship + evidence |
| 10 | deployment | artifact + execution + state + policy |
| 11 | networking | protocol + boundary + relationship (topology) + resource |
| 12 | API/protocol design | protocol + policy + identity + capability |
| 13 | state management | state + event + time (event sourcing = event log + projections) |
| 14 | time (doctrine) | time + event + policy (leases, expiry) |
| 15 | AI/agents | artifact (model) + execution + capability (tools) + evidence + identity |
| 16 | UX | information + boundary (human) + protocol (interaction) + time (latency) |
| 17 | product/domain | policy (business rules) + identity (tenants) + resource (billing) + event |
| 18 | multi-tenancy | identity + boundary + resource + policy (isolation = boundary + policy) |
| 19 | economics | resource + identity + event + policy ("cheapest way to satisfy the invariant") |
| 20 | operations | execution + event + time + policy (runbooks) |
| 21 | compliance/governance | event + evidence + time + policy (retention, holds) |
| 22 | documentation | information + artifact + relationship + evidence (docs as verifiable info) |
| 23 | developer experience | protocol + artifact + execution + information |
| 24 | compatibility | artifact + protocol + time (versions) + policy (negotiation) |
| 25 | physical/hardware | identity (device) + evidence (attestation) + execution + resource |

## Worked example: attestation

`attestation = identity + evidence + cryptography`
where cryptography = protocol(information) with hardness assumptions.
NRAS: identity(GPU, fused keys) + evidence(signed EAT) + protocol(JWT/ES384/JWKS).
Our verifier consumes the evidence; it does not inherit the identity's authority.

## Worked example: authorization (the R020 shape)

```
CLAIMED:      caller declares what they want        (information, untrusted)
ESTABLISHED:  verifier derives what evidence shows  (evidence → relationship)
AUTHORIZED:   policy decides what may be used       (policy over established)
```
Collapse any two and you reimplement `A says X, B says X, therefore X`.

## Open derivations (unknowns)

- Is `topology` a 16th primitive or just relationship-over-execution? Currently
  derived; revisit if it earns independent productions.
- Is `cryptography` primitive or protocol(information)? Currently derived;
  hardness assumptions may earn it a seat.
- `consciousness`/`intent`: excluded — no production in the 25 needs them
  (same gate that kept INTENT out of GO-50).
