# Table 2. Provenance, Score, and Tolerance Semantics

| Metadata item | Packet value or location | Manuscript interpretation | Forbidden interpretation |
| --- | --- | --- | --- |
| Coordinate enforcement scope | Packet-level builder metadata | The manuscript can claim packet-level coordinate contract enforcement for the Paper A packet. | Universal coordinate-system enforcement across the full local codebase. |
| Input coordinate type | Packet coordinate contract | Inputs are treated according to an explicit metric-coordinate contract in the packet path. | Raw geographic coordinates can be silently treated as metric trajectories. |
| Source CRS and projection method | Private coordinate provenance | Projection assumptions are recorded for the packet. | External positional accuracy or field-survey confirmation. |
| Units and axis convention | Packet coordinate contract | Descriptor and candidate generation are tied to recorded metric units and axis convention. | Unit correctness outside the packet path. |
| Deduplication policy | Representation summary and provenance metadata | Consecutive exact duplicate points are removed before downstream representation. | Duplicate removal is a sport-specific cleaning model. |
| Primitive candidate score | Primitive candidate metadata | Score/confidence is a deterministic heuristic score derived from local evidence and thresholds. | Calibrated probability, statistical confidence, or perturbation survival. |
| Primitive candidate type | Primitive candidate artifact summary | Stop, turn, reversal, and high-curvature outputs are candidate records. | Confirmed events or ground-truth movement labels. |
| Topology tolerance | Packet topology metadata | The reported tolerance is a computational predicate tolerance for candidate generation. | GNSS measurement-error tolerance or sensor-error model. |
| Topology candidate count | Representation summary | Counts describe generated tolerance-conditioned topology candidates. | Unique physical crossings or externally confirmed topology. |
| Descriptor statistics | Representation summary | Speed and curvature proxy summaries describe generated packet descriptors. | Complete biomechanical or sport-performance characterization. |

**Caption draft:** Public-safe summary of the provenance, score, and tolerance semantics used to constrain manuscript claims.

**Source basis:** Private packet metadata, private representation summary, and public limitations.

**Forbidden interpretation:** This table does not establish calibrated statistical confidence, sensor-error tolerance, full codebase coordinate enforcement, or production readiness.
