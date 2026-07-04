# Public Staged Sensitivity Evidence Summary

This public-safe summary describes staged sensitivity evidence used to bound Paper A interpretation. It does not expose private trajectory artifacts or private planning details.

## Interpretation

The evidence supports sensitivity and limitation claims only. It does not establish robust detection, external measurement accuracy, or a unified validation benchmark.

## Public Evidence Categories

| Category | Public finding | Safe manuscript use |
| --- | --- | --- |
| Sampling density | Candidate counts and geometry-derived summaries can change with sampling density. | Sampling assumptions should remain explicit. |
| Gap handling | Segment boundaries can change candidate counts and interpretation. | Gap handling is an interpretation boundary. |
| Smoothing | Smoothing can reduce positional noise while changing structural descriptors. | Smoothing is not treated as a solved preprocessing step. |
| Curvature sensitivity | Coordinate noise can inflate curvature-derived quantities. | Curvature-derived candidates inherit noise sensitivity. |
| Primitive thresholds | Primitive candidate counts and boundaries are threshold-sensitive. | Primitive outputs are threshold-conditioned candidates. |
| Topology tolerance | Topology outputs are tolerance-conditioned and can be sensitive near endpoints, overlaps, or near-threshold geometry. | Topology candidates should not be treated as externally confirmed structures. |

## Public Boundary

Detailed trajectory-level artifacts and private packet outputs are withheld. The public table `tables/robustness_summary.csv` provides a staged summary suitable for manuscript review but not full private-packet reproduction.
