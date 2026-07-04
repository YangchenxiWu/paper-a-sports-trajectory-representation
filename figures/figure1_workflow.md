# Figure 1. Deterministic Representation Packet Workflow

```mermaid
flowchart LR
    A["Configured sports trajectory observation"] --> B["Packet-level coordinate contract check"]
    B --> C["Canonical metric track construction"]
    C --> D["Per-point descriptor table"]
    D --> E["Threshold-conditioned primitive candidates"]
    D --> F["Tolerance-conditioned topology candidates"]
    E --> G["Symbolic graph artifact"]
    F --> G
    E --> H["Inspection overlay artifact"]
    F --> H
    B --> I["Packet provenance and metadata"]
    C --> J["Representation summary"]
    D --> J
    E --> J
    F --> J
    G --> J
```

**Caption draft:** Configured sports trajectory observations are converted into a deterministic representation packet through packet-level coordinate contract checking, canonical metric track construction, descriptor generation, threshold-conditioned primitive candidate extraction, tolerance-conditioned topology candidate extraction, graph construction, overlay generation, provenance recording, and summary reporting.

**Source basis:** Private packet manifest and provenance summaries.

**Forbidden interpretation:** This workflow does not demonstrate production readiness, external measurement accuracy, universal coordinate-system enforcement, sport-specific semantic interpretation, or robust detection.
