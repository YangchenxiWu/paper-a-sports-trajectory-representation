# Limitations — Paper A

This document makes the limitations of Paper A explicit and conservative.
Each limitation is traceable to repo evidence. No limitation should surprise a
reviewer who reads the code.

---

## 1. Metric Coordinate Contract Not Fully Enforced

**Status**: Confirmed.

**Evidence**: The coordinate contract (`coordinate_contract.v1`) is built and
validated in `build_canonical_track` (`src/sports_spatial_core/cleaning/projection.py`).
However, descriptor, primitive, topology, and overlay functions accept any
DataFrame with numeric `x`/`y` columns — they do not verify that a coordinate
contract is attached or that coordinates are metrically projected.

**Impact**: A user could pass raw lat/lon as `x`/`y` and the pipeline would
produce deterministic but geometrically invalid results. The heuristic lint
check (`lint_projected_coordinates`) warns but does not block.

**Paper A mitigation**: State explicitly that all results assume metric ENU
coordinates. The coordinate contract is recorded in provenance but not
enforced in all pipeline stages.

## 2. Resampling Is Experimental, Not Canonical

**Status**: Confirmed.

**Evidence**: `src/sports_spatial_core/resampling/__init__.py` states:
"All functions in this module are **experimental**. No default parameters are
frozen and no policy is claimed production-ready."

**Impact**: The pipeline operates on raw input sample spacing. Curvature,
primitive boundaries, and topology candidates are all sampling-rate dependent.
Two recordings of the same movement at different cadences may produce different
candidate sets.

**Paper A mitigation**: Do not claim resampling invariance. Reference exp-002
through exp-004 as characterization, not validation.

## 3. Primitive Thresholds Are Not Stable Under Perturbation

**Status**: Confirmed.

**Evidence**: `experiments/exp-007-primitive-stability/` demonstrates that
primitive detection boundaries shift under parameter perturbation. Confidence
scores are deterministic functions of threshold margins, not perturbation
survival rates.

**Impact**: Small changes to threshold parameters (angle, curvature, speed)
can cause primitives to appear, disappear, or change boundaries. There is no
primitive identity matching across parameter variations.

**Paper A mitigation**: Use "primitive candidate" language consistently. Report
parameters alongside results. Reference exp-007 as evidence of sensitivity.

## 4. Topology Is Tolerance-Dependent

**Status**: Confirmed.

**Evidence**: `src/sports_spatial_core/topology/candidates.py` uses a default
tolerance of 1e-9 (in coordinate units). `experiments/exp-008-topology-robustness/`
demonstrates that intersection type classification and candidate detection
change under tolerance variation. Near-endpoint and near-collinear cases are
flagged but not resolved.

**Impact**: Self-intersection and loop candidates are brittle under small
coordinate perturbations or tolerance changes. The default tolerance of 1e-9
has no documented justification relative to typical GNSS precision (~1-5m).
Additionally, the O(n²) segment-pair comparison can produce very large numbers
of low-confidence candidates on dense, self-crossing trajectories (e.g., 4,372
total topology candidates on 871 trajectory points in the running sample),
making raw candidate counts misleading without confidence and stability-flag
filtering.

**Paper A mitigation**: Report tolerance explicitly. Flag endpoint_touch and
collinear_overlap cases as ambiguous. Reference exp-008. Note that candidate
counts alone do not indicate trajectory complexity — they reflect both
trajectory geometry and the O(n²) comparison scaling with point density.

## 5. No Unified Perturbation Framework

**Status**: Confirmed.

**Evidence**: `KNOWN_ISSUES.md` line: "Perturbation Framework Is Missing."
Experiments exp-004 through exp-008 each implement ad-hoc perturbation, but
there is no shared harness, no common perturbation protocol, and no
cross-experiment comparison standard.

**Impact**: Cannot make quantitative claims about representation stability.
Each experiment's perturbation is siloed.

**Paper A mitigation**: Present individual experiment results as qualitative
characterization, not quantitative stability guarantees.

## 6. Confidence Is Heuristic, Not Calibrated

**Status**: Confirmed.

**Evidence**: Confidence scores are weighted combinations of threshold margins
and local consistency metrics:
- Stops: 0.5 × threshold_margin + 0.3 × duration_score + 0.2 × radius_score
- Turns/curvature: 0.7 × threshold_score + 0.3 × local_consistency
- Reversals: 0.75 × angular_margin + 0.25 × length_consistency
- Topology intersections: 0.7 × endpoint_score + 0.3 × separation_score
- Overlaps: 0.45 × distance_margin + 0.35 × direction_consistency + 0.20 × length_margin

These weights are implementation choices, not empirically calibrated.

**Impact**: Confidence values are not comparable across primitive types. A
0.8-confidence stop and a 0.8-confidence turn do not have the same
interpretation.

**Paper A mitigation**: Describe confidence as "deterministic heuristic score"
or "evidence-weighted score." Never call it "probability" or "calibrated
confidence."

## 7. Total-Station Validation Is Planning-Only

**Status**: Confirmed.

**Evidence**: `experiments/exp-009-total-station-reference-validation/` exists
as an empty directory. No code, no data, no reference measurements.

**Impact**: No absolute positional accuracy assessment exists. All claims are
about internal consistency and deterministic behavior, not accuracy relative
to physical ground truth.

**Paper A mitigation**: Explicitly exclude absolute accuracy claims. State that
ground-truth validation is future work (Paper B).

## 8. Blind LLM Audit Is Demonstration-Only

**Status**: Confirmed.

**Evidence**: `experiments/exp-001-audit-comparison/` generates audit contexts
but does not implement a validated blind audit protocol. The comparison
methodology (C0 vs C4) is described in `audit_demonstration.md` but is not
formalized with inter-rater reliability, statistical power analysis, or
adversarial audit design.

**Impact**: Cannot claim that deterministic representation improves audit
quality. The demonstration shows feasibility, not validation.

**Paper A mitigation**: Exclude audit claims from Paper A. The overlay artifact
supports human review but is not an audit protocol.

## 9. Single-Sample Demonstration

**Status**: Confirmed.

**Evidence**: `experiments/exp-001-audit-comparison/run_pipeline.py` primarily
runs on one sample (skiing_run_01). A second sample (running_2026-04-09) exists
in configuration but is not the primary demonstration.

**Impact**: Cannot claim generalizability across sports, movement types, or
recording conditions.

**Paper A mitigation**: Describe results as "demonstration on two sports
trajectories" rather than "validation across sports."

## 10. No Smoothing Policy

**Status**: Confirmed.

**Evidence**: `KNOWN_ISSUES.md`: "No Smoothing Policy." The descriptor layer
has validity flags, but no coordinate smoothing step exists in the main pipeline.
`experiments/exp-005-smoothing-trial/` is an isolated experiment only.

**Impact**: GNSS jitter propagates directly into heading, curvature, and all
downstream primitives/topology.

**Paper A mitigation**: Acknowledge that results reflect raw (unsmoothed)
coordinates. Reference exp-005 as evidence that smoothing would change results.

---

## What Paper A CAN Honestly Say About Limitations

> "The representation is deterministic and self-consistent under fixed parameters,
> but its outputs are sensitive to: (1) input sampling rate, (2) coordinate
> projection quality, (3) primitive threshold choices, (4) topology tolerance
> values, and (5) GNSS measurement noise. Confidence scores are deterministic
> heuristics, not calibrated probabilities. No absolute positional accuracy
> assessment exists. Results are demonstrated on two sports trajectories and
> should not be generalized without further validation."

## What Paper A CANNOT Say

> "The representation is robust," "confidence is calibrated," "topology is
> stable," "the pipeline is sampling-invariant," "results are validated against
> ground truth," "the representation improves audit quality."
