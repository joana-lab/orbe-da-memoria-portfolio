# System architecture

Static-first, data-driven. Sources become structured claims; claims pass a human verification
gate; verified data is version-controlled and rendered by a framework-free application into map,
narrative, and (prototype) 3D experiences. Quality checks run against the data; deployment is
verified served-vs-built.

```mermaid
flowchart TD
    A[Historical / archival sources] --> B[Structured claims + sources + certainty]
    B --> C{Human verification gate}
    C -- verified --> D[(Version-controlled data)]
    C -- gap --> D2[Declared honest absence]
    D2 --> D
    D --> E[Application layer — static SPA]
    E --> F[Map experience — Leaflet]
    E --> G[Narrative / entity experience]
    E -. prototype .-> H[3D / time exploration — Three.js]
    D --> I[Quality checks / linting]
    I --> E
    D --> J[Controlled deploy]
    J --> V{Served == built?}
    V -- yes --> K[Public web experience]
    V -- no --> J
```

**Notes.** No backend, no database, no runtime AI. 3D is a prototype, not integrated. The
served-vs-built check is fail-closed: a release is not "live" until it passes.
