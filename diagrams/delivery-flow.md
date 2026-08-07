# Delivery / quality flow

From requirement to a verified, committed live state, with quality gates and a fail-closed
deploy check.

```mermaid
flowchart LR
    R[Requirement / priority] --> P[Agent proposal]
    P --> G1{Founder approval}
    G1 -- approved --> B[Build against spec]
    G1 -- returned --> P
    B --> CH[Automated checks / linting]
    CH --> AU[Evidence-based quality audit]
    AU --> G2{Founder acceptance}
    G2 -- accepted --> DEP[Controlled deploy]
    G2 -- returned --> B
    DEP --> V{Served == built?}
    V -- yes --> SoT[(Committed source of truth)]
    V -- no, fail-closed --> DEP
```

**Rules.** Single writer per file, serialised. Reviewed ≠ committed. A check that exists but is
not run on a cadence is a document, not an instrument.
