# Figure 3. Staged Sensitivity Evidence Overview

```mermaid
flowchart TB
    A["Staged sensitivity evidence"] --> B["Sampling density"]
    A --> C["Gap handling"]
    A --> D["Smoothing"]
    A --> E["Curvature noise response"]
    A --> F["Primitive threshold behavior"]
    A --> G["Topology tolerance behavior"]

    B --> B1["Candidate counts depend on sampling condition"]
    C --> C1["Gap policy affects generated representation"]
    D --> D1["Smoothing changes descriptor and candidate behavior"]
    E --> E1["Curvature proxy has noise-sensitive behavior"]
    F --> F1["Primitive candidates depend on configured thresholds"]
    G --> G1["Topology candidates depend on computational tolerance"]
```

**Caption draft:** Staged sensitivity evidence summarizes how representation outputs respond to sampling density, gap handling, smoothing, curvature noise, primitive thresholds, and topology tolerance. These probes characterize tolerance-conditioned behavior and stability boundaries for the packet rather than providing a unified validation benchmark.

**Source basis:** Public staged sensitivity aggregation in `tables/robustness_summary.csv` and public staged sensitivity summary.

**Forbidden interpretation:** This figure does not show robust validation, ground-truth detection accuracy, external sensor validation, or a unified validation benchmark.
