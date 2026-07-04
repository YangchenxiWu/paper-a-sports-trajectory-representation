# Table 1. Two-Sample Representation Summary

| Sample | Sport label | Duration (s) | Raw points | Post-dedup points | Removed exact duplicates | Mean speed (m/s) | Max speed (m/s) | Mean curvature proxy (rad/m) | Max curvature proxy (rad/m) | Primitive candidates by type | Topology candidates | Graph nodes | Graph edges |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | --- | ---: | ---: | ---: |
| `skiing_run_01` | Skiing descent | 659.812 | 661 | 338 | 323 (48.9%) | 6.992 | 25.171 | 0.038 | 0.203 | high-curvature 7; left-turn 11; right-turn 15; stop 1; turn 37 | 0 | 207 | 347 |
| `running_2026-04-09` | Running activity | 2767.990 | 2770 | 871 | 1899 (68.6%) | 1.967 | 17.386 | 0.473 | 3.112 | direction-reversal 151; high-curvature 131; left-turn 42; right-turn 44; stop 95; turn 90 | 4372 | 5695 | 15543 |

**Caption draft:** Summary of generated representation artifacts for two retained sample trajectories. Exact duplicate removal is reported because repeated consecutive positions materially affect descriptor and candidate generation. Primitive candidates are threshold-conditioned outputs, and topology candidates are tolerance-conditioned outputs.

**Source basis:** Private representation summary.

**Forbidden interpretation:** This table does not support generalization, candidate correctness, unique physical crossing counts, sport-specific semantic conclusions, or external measurement accuracy.
