# COVERAGE — current build vs the 25 surfaces

Honest map as of 2026-10-06. Tags: STRONG (production, tested) / PARTIAL
(real pieces, gaps) / ZERO (no formal subsystem) / IN-FLIGHT (FULL SEND lane).

| # | Surface | Rating | Evidence |
|---|---|---|---|
| 1 | security | PARTIAL | Verifier/R020 program STRONG; key mgmt, rotation, revocation, SBOM, vuln-mgmt, incident response: ZERO–thin |
| 2 | identity | PARTIAL → IN-FLIGHT | Governor becoming identity→authz chain; NRAS attestation probed; full identity arch: lane C/E |
| 3 | data | PARTIAL | Ledger (append-only), D1, SQLite graph STRONG as stores; canonicalization, versioning, migrations, lineage: thin |
| 4 | distributed systems | PARTIAL | Sockets, events, MCP, REST, journals; consensus/election/clocks/causality: no doctrine |
| 5 | scalability | ZERO → IN-FLIGHT | No formal subsystem. Biggest opportunity. |
| 6 | reliability | PARTIAL | Fail-closed doctrine STRONG for verification; degraded-mode/cache/queue/recovery policy: thin |
| 7 | observability | PARTIAL | Receipts STRONG; logs/metrics/traces/profiling: thin. Continuous verification (observations → invariants) is the interesting direction |
| 8 | testing | STRONG (adversarial) | R020 campaign = adversarial property testing; unit/integration/mutation present; perf/load/chaos: thin |
| 9 | supply chain | IN-FLIGHT | SLSA/in-toto/Sigstore on the Tier S steal list; lane F/G |
| 10 | deployment | PARTIAL | Cloudflare Workers/wrangler real; generalized deployment matrix: thin |
| 11 | networking | PARTIAL | "Don't make everything HTTP" is principle, not subsystem |
| 12 | API/protocol | STRONG | MCP + REST + OpenAPI + ai-router; versioning/negotiation/capability-discovery: partial |
| 13 | state management | PARTIAL | Journals drifting toward event sourcing; no formal doctrine |
| 14 | time | PARTIAL | not_after, journal chains, expiry exist; no formal time doctrine |
| 15 | AI/agents | PARTIAL → IN-FLIGHT | ai-router (12 lanes), 95/5 doctrine; model identity, tool sandboxing, prompt injection, eval: lanes B/C |
| 16 | UX | ZERO | Untouched. Formally perfect and unusable is a failure mode. |
| 17 | product/domain | ZERO | Untouched as architecture. |
| 18 | multi-tenancy | ZERO | No first-class concept. |
| 19 | economics | PARTIAL | $0 doctrine + resource-efficiency obsession; no formal engineering-economics layer |
| 20 | operations | PARTIAL | Crons, ledger, runbooks-as-code emerging; on-call/incident: thin |
| 21 | compliance/governance | PARTIAL | Receipt system is the seed; retention/holds/residency: thin |
| 22 | documentation | PARTIAL | This scaffold is the start; machine-readable contracts: thin |
| 23 | developer experience | PARTIAL | Organelles + MCP + REST + OpenAPI heading there; CLI/SDK/CI: thin |
| 24 | compatibility | ZERO | No versioning/negotiation doctrine. |
| 25 | physical/hardware | IN-FLIGHT | NRAS probe done (JWKS, 80 P-384 keys); TPM/TEE: Tier B |

## The pattern

The build is extraordinarily deep on TRUST (verifier, evidence, receipts, policy
gates) and respectable on COMPUTING (router, Exchange, protocols). It is thin or
absent on EXPERIENCE, DOMAIN, and the OPERATING SYSTEM layer (security-complete,
scaling, reliability, ops, economics) — exactly the map Zackary drew. That is not
an insult; it is the attack plan.
