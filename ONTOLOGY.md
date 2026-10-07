# ONTOLOGY — 15 system primitives

Each primitive earns its seat by the same gates as GO-50: it appears in real
productions, it cannot be composed from the others in ≤2 steps, and naming it
changes what the operator can build. A primitive with no production is a vibe
with capitalization.

## 1. INFORMATION
The substrate. Any content plus its identity question: *what makes this the
same information?* (hash? canonical bytes? semantic equivalence? version?)
Everything below operates on information; nothing else is fundamental.

## 2. IDENTITY
What makes an actor or artifact the *same* across time and space. Covers human,
device, process, service, agent, container, pod, node, cluster, organization,
external authority, model, artifact. Identity is claimed, then established —
never assumed from a name (law 1).

## 3. STATE
The standing configuration of a thing. State persists; events punctuate it.
`desired state ≠ observed state` is the founding distinction of the whole
substrate.

## 4. EVENT
A discrete state transition: timestamped, ordered, immutable once recorded.
Events are the only thing that ever *happens*; everything else is derived.

## 5. TIME
Wall clock, monotonic clock, logical clock (Lamport, vector). Expiry, leases,
validity windows, replay windows, retention. Clocks lie; the doctrine says how.

## 6. RELATIONSHIP
A typed, directed connection between identified things: `built-by`,
`observed-by`, `owns`, `attests-to`, `supersedes`, `depends-on`. Relationships
are established by evidence, never by assertion.

## 7. CAPABILITY
What an identity *may do*, as an unforgeable reference. Capabilities are
granted, delegated, attenuated — never ambiently inferred.

## 8. AUTHORITY
The standing right to *decide*. Authority ≠ capability: capability is the key,
authority is the lock's policy. Observation never creates authority (law 3).

## 9. EVIDENCE
Recorded information bearing on a claim, *with provenance*. Evidence is not
assertion-shaped (law 2): a caller saying "FACTUAL" produces a claim, not evidence.

## 10. POLICY
A rule mapping `(identity, capability, evidence, context) → decision`.
Policy is data, versioned and auditable — never vibes.

## 11. EXECUTION
The act of doing: processes, workloads, runs, agent tool calls. Execution is
where information meets the world and where most lies are told about what happened.

## 12. RESOURCE
Anything consumed: compute, memory, storage, bandwidth, latency, energy, money,
*human attention*. Every capability has a resource cost; the cheapest way to
satisfy the invariant is an architectural question.

## 13. BOUNDARY
Where one trust/scope domain ends and another begins. The membrane. Every
boundary crossing is a verification event. Unverifiable boundary → STOP.

## 14. PROTOCOL
The agreed message/behavior contract across a boundary: versioned, negotiated,
canonicalized. HTTP, MCP, EAT/JWT, Kubernetes API, Unix sockets — all protocols.

## 15. ARTIFACT
A named, content-addressed, versioned bundle of information: build output,
model weights, document, container image. Artifacts are what provenance is *about*.

## Non-derivability notes (why 15, not 12 or 40)

- STATE vs EVENT: the oldest trap. State is what *is*; event is what *happened*.
  Collapse them and you lose replay, audit, and causality in one move.
- CAPABILITY vs AUTHORITY: the confused-deputy trap. Collapse them and ambient
  authority reappears wearing a capability costume.
- EVIDENCE vs INFORMATION: evidence is information *plus* provenance *plus* a
  claim it bears on. Raw information establishes nothing.
- IDENTITY vs ARTIFACT: identities act; artifacts don't. An artifact with an
  identity (signed) is a relationship between the two, not one primitive.
- TIME vs EVENT: events need ordering; ordering needs time. Logical clocks show
  they are separable: you can have causality without wall time.
