# ROADMAP — attack order for the holes

Zackary's named targets, in the order that compounds. Each item: derive from
primitives → organelle composition → nasty tests → receipts → integrate. The
FULL SEND lanes (A–H) own the trust slice; this roadmap owns everything else.

## Phase 1 — load-bearing gaps (cryptography is no longer the bottleneck)

1. **Time doctrine** (`tm`) — wall/monotonic/logical clocks, skew, leases,
   replay windows, expiry. Unblocks: distributed systems, reliability, audit.
2. **State management doctrine** (`st` + `ev`) — event sourcing, CQRS,
   projections, replay, temporal queries. The journals are already drifting here.
3. **Threat model** (`bo` + `id` + `po`) — formal: assets, adversaries,
   trust boundaries, what each boundary crossing requires. Without this,
   security work is decoration.
4. **Recovery doctrine** (`st` + `ev` + `tm` + `rs`) — backup verification,
   RPO/RTO, disaster recovery, degraded-mode policy (dependency down ≠ always
   NO for applications; verification stays NO, operations degrade by policy).

## Phase 2 — the missing continents

5. **Scalability** (`rs` + `st` + `ex`) — characterize N on every axis;
   establish O() complexity per subsystem; horizontal/vertical/sharding/caching
   as compositions, not vibes.
6. **Distributed systems doctrine** (`st` + `ev` + `tm` + `pr`) — consensus,
   election, quorum, delivery semantics, idempotency, backpressure, failure
   detection. As compositions of the primitives, not a imported framework.
7. **Multi-tenancy** (`id` + `bo` + `rs` + `po`) — tenant, isolation at every
   layer (data, fs, process, net, cache, logs, queues), quotas, billing.
8. **Resource economics** (`rs` + `po`) — every capability priced in compute,
   memory, bandwidth, energy, money, attention. "Cheapest way to satisfy the
   invariant" becomes computable.

## Phase 3 — the organism grows a face

9. **Operational reliability** (`ex` + `ev` + `tm`) — health/readiness/liveness,
   failover, chaos testing, runbooks as policy.
10. **Supply chain** (`ar` + `ev` + `id`) — SBOM, reproducible builds, artifact
    signing, provenance (SLSA/in-toto/Sigstore already Tier S).
11. **Product/runtime surfaces** (`pr` + `bo`) — UX, domain organelles, the
    boring-but-essential half of the machine.

## Non-goals for this scaffold

25 new subsystems. Framework adoption as substitute for derivation. Any box
that cannot name its primitives.
