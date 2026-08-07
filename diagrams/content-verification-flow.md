# Content verification flow

How a single claim moves from a source to a rendered, graded statement — or to an honest gap.

```mermaid
flowchart TD
    S[Candidate claim from a source] --> ID[Identify source + document link]
    ID --> HV{Human verification<br/>outside the producer}
    HV -- supported --> GR[Assign certainty grade<br/>word + symbol]
    HV -- sources disagree --> CF[Grade: in conflict<br/>two identified sources]
    HV -- not locatable --> GAP[Declared honest absence<br/>localised, not universal]
    GR --> REC[Structured record:<br/>claim · source · grade · nature · dating · coords]
    CF --> REC
    GAP --> REC
    REC --> RENDER[Rendered in map / entity / narrative]
    RENDER --> AUDIT[Audited: source present,<br/>vocabulary valid, links resolve]
```

**Two axes, never fused.** The *grade of the claim* and the *nature/dating of the source* are
recorded and shown separately. **Prove the instrument** before declaring any absence.
