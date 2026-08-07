# AI operating model

Specialised AI roles under human authority. Agents propose and produce; humans hold the approval
and acceptance gates and the source of truth. A role is a scope of work, not a grant of authority.

```mermaid
flowchart TD
    H[Historian / Curator] --> DS[Designer]
    DS --> RE[Design runtime review]
    RE --> FA{Founder approval}
    FA -- approved --> AR[Architecture / CTO]
    FA -- returned --> H
    AR --> DV[Developer / Dev Lead]
    DV --> QA[Quality / Audit]
    IC[Iconography] --> QA
    QA --> FAC{Founder acceptance}
    FAC -- accepted --> SoT[(Version-controlled source of truth)]
    FAC -- returned --> DV
```

**Boundaries.** Agents may not publish verified claims, change governance, create agents,
redefine architecture, or approve releases. Verification is always performed outside the agent
that produced the work.
