# Selected technical decisions (ADRs)

Short, honest records of decisions that shaped the platform. Each states the context, the
decision, the reasoning, and the trade-off accepted.

---

## ADR-001 — Structured data before narrative rendering

**Context.** Historical content is easy to write as prose and hard to keep trustworthy once prose
detaches from its source.
**Decision.** Model claims as structured records first; render narrative from them.
**Why.** The interface can then guarantee that every statement carries a source and a grade.
**Trade-off.** More up-front modelling effort; less freedom to hand-write one-off prose.

## ADR-002 — Human verification before publication

**Context.** AI-assisted production can generate plausible claims faster than they can be checked.
**Decision.** No claim is published as verified without human verification performed outside the
producing agent.
**Why.** Plausibility is not proof; independence is what makes verification meaningful.
**Trade-off.** Human verification is the throughput bottleneck — accepted deliberately, because
it is the product's core value.

## ADR-003 — Static-first architecture

**Context.** A cultural reference should be trustworthy, cheap to run, and durable.
**Decision.** Vanilla HTML/CSS/JS reading version-controlled JSON; no backend, no runtime AI.
**Why.** Small trust surface, auditable data, operational simplicity, longevity.
**Trade-off.** Dynamic/server features (search at scale, personalisation) must be designed around
the static model rather than assumed.

## ADR-004 — Progressive enhancement for 3D

**Context.** A 3D globe and immersive reader are compelling but heavy and not essential to the
core reference.
**Decision.** Keep 3D (Three.js) as a **prototype in a lab**, integrated only after an explicit
integration decision; the core atlas works fully in 2D (Leaflet) without it.
**Why.** The reference value must not depend on WebGL, device power, or the prototype's fate.
**Trade-off.** The 3D experience is not yet in the product; integration is deferred, not assumed.

## ADR-005 — Version-controlled governance

**Context.** Decisions made in conversation are forgotten or contradicted.
**Decision.** A decision is durable only when approved **and** written into version-controlled
source of truth.
**Why.** "Done" becomes a verifiable state with an author and a history, not a memory.
**Trade-off.** More writing discipline; every real decision must be committed, not just agreed.

## ADR-006 — AI agents separated by responsibility

**Context.** A single general agent concentrates production and verification in one place.
**Decision.** Split delivery into specialised roles (curation, design, architecture, development,
quality, iconography) with verification kept outside the producer.
**Why.** Separation of duties; independence of checks; clearer accountability.
**Trade-off.** Coordination overhead between roles, handled by an explicit hand-off discipline.
