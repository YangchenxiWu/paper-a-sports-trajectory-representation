# Claims Ledger — Paper A

Each claim is classified:

| Level | Meaning |
|-------|---------|
| **supported** | Implementation exists, tested, and artifact is reproducible from repo code |
| **partially supported** | Implementation exists but has gaps in provenance, policy, or testing |
| **unsupported** | Either not implemented or exists only as documentation/theory |
| **future work** | Explicitly out of scope for Paper A; reserved for Paper B or later |

---

## 1. Canonical metric track schema exists

- **Claim**: A schema-validated canonical trajectory table with required columns
  (track_id, point_index, t, x, y, source) and deterministic schema validation
  exists.
- **Evidence path**: `src/sports_spatial_core/cleaning/track_schema.py`
  (validate_track_schema); `src/sports_spatial_core/cleaning/projection.py`
  (build_canonical_track)
- **Supported level**: **supported**
- **Safe paper wording**: "The canonical track schema enforces six required columns,
  five optional columns, and validates point ordering, timestamp monotonicity,
  and numeric types. The schema is versioned implicitly through the
  TRACK_COLUMNS definition."
- **Risk**: Low. Well-tested with 232 passing tests including schema validation
  tests.
- **Action needed**: None for Paper A.

## 2. Descriptor table generation exists

- **Claim**: Deterministic per-point motion and geometry descriptors are computed
  from the canonical track.
- **Evidence path**: `src/sports_spatial_core/descriptors/geometry.py`
  (compute_basic_motion_descriptors); 22 descriptor columns including validity
  flags
- **Supported level**: **supported**
- **Safe paper wording**: "The descriptor layer produces 22 per-point columns
  including segment distance, dt, speed, heading, turn angle, curvature, local
  radius, heading variance, and tortuosity, each with explicit validity flags.
  Descriptor parameters are recorded in DataFrame.attrs."
- **Risk**: Low. Basic descriptors are well-tested.
- **Action needed**: None for Paper A.

## 3. Primitive candidate extraction exists

- **Claim**: Deterministic stop, turn, high-curvature, and direction-reversal
  primitive candidates are extracted from descriptor tables.
- **Evidence path**: `src/sports_spatial_core/primitives/stops.py`,
  `turns.py`, `reversals.py`; schema in `src/sports_spatial_core/schemas/primitives.py`
- **Supported level**: **supported**
- **Safe paper wording**: "Six primitive candidate types are extracted under
  parameterized thresholds: stop_candidate (speed + duration + optional radius),
  left_turn_candidate, right_turn_candidate, turn_candidate (angle threshold),
  high_curvature_segment (curvature threshold), and direction_reversal_candidate
  (near-180° heading change). Each primitive records start/end source indices,
  deterministic confidence, parameter snapshot, and evidence fields."
- **Risk**: Low-Medium. Confidence is deterministic heuristic, not calibrated.
  Primitive boundaries are sensitive to input sampling rate.
- **Action needed**: Acknowledge confidence semantics; do NOT claim calibration.

## 4. Topology candidate extraction exists

- **Claim**: Deterministic self-intersection, loop, and repeated-path/overlap
  candidates are extracted from the canonical track.
- **Evidence path**: `src/sports_spatial_core/topology/candidates.py`
  (extract_topology_candidates); `src/sports_spatial_core/topology/overlaps.py`
  (extract_overlap_candidates)
- **Supported level**: **supported**
- **Safe paper wording**: "Three topology candidate types are extracted:
  self_intersection_candidate (proper crossing, endpoint touch, or collinear
  overlap), loop_candidate (spatially bounded self-intersection regions), and
  repeated_path_candidate (proximate parallel or anti-parallel segments).
  Each candidate includes intersection geometry, confidence, ambiguity flags,
  and stability flags."
- **Risk**: Medium. Topology is tolerance-dependent; small coordinate changes can
  flip intersection type. No persistence metric exists.
- **Action needed**: Document tolerance sensitivity; do NOT claim robustness.

## 5. Symbolic graph exists

- **Claim**: A deterministic symbolic IR graph artifact exists that links
  primitive events and topology candidates in a structural graph.
- **Evidence path**: `src/sports_spatial_core/topology/graph.py`
  (build_symbolic_ir_graph)
- **Supported level**: **supported**
- **Safe paper wording**: "The symbolic IR graph (schema v1) constructs boundary
  nodes from all primitive/topology index boundaries, primitive event nodes,
  structural event nodes, and four edge types (movement_continuity,
  primitive_span, primitive_transition, structural_relation) with deterministic
  IDs."
- **Risk**: Low. Graph construction is deterministic and tested. Missing:
  visualization, graph persistence metrics.
- **Action needed**: None for Paper A beyond acknowledging missing persistence
  metrics.

## 6. Overlay artifact exists

- **Claim**: Inspectable HTML and PNG overlay artifacts are generated from
  trajectory points, primitives, and topology candidates.
- **Evidence path**: `src/sports_spatial_core/overlays/artifacts.py`
  (write_overlay_artifacts, generate_overlay_html, write_overlay_png)
- **Supported level**: **supported**
- **Safe paper wording**: "The overlay layer generates an inspectable HTML
  artifact with inline SVG trajectory rendering, primitive-range highlighting,
  topology-candidate annotation, and a structured data panel. An optional
  static PNG is also supported."
- **Risk**: Low. Tested. Requires matplotlib for PNG.
- **Action needed**: None for Paper A.

## 7. Robustness experiments exist

- **Claim**: Experiments characterize sensitivity of the representation to
  sampling, smoothing, curvature estimation, primitive parameters, and topology
  tolerances.
- **Evidence path**: `experiments/exp-002*/` (resampling), `exp-003/` (segment API),
  `exp-004/` (sampling invariance), `exp-005/` (smoothing trial),
  `exp-006/` (curvature robustness), `exp-007/` (primitive stability),
  `exp-008/` (topology robustness)
- **Supported level**: **partially supported**
- **Safe paper wording**: "Experiments exp-002 through exp-008 characterize
  representation sensitivity to arc-length resampling, sampling density,
  coordinate jitter, curvature estimation method, primitive parameter
  perturbation, and topology tolerance variation. These are parameter-sweep
  characterizations, not formal statistical validations."
- **Risk**: Medium. Each experiment is a self-contained script; there is no
  unified robustness harness. Results are not cross-validated across samples.
- **Action needed**: Summarize individual experiment findings; do NOT claim
  comprehensive robustness.

## 8. CRS/projection is enforced

- **Claim**: The coordinate reference system is enforced and projection
  provenance is attached to every artifact.
- **Evidence path**: `src/sports_spatial_core/cleaning/projection.py`
  (build_coordinate_contract, validate_coordinate_contract,
  lint_projected_coordinates)
- **Supported level**: **partially supported**
- **Safe paper wording**: "The coordinate contract (v1) records projection method,
  origin (lat, lon, ECEF), axis units (meters), and axis directions
  (East, North, Up). A heuristic lint check warns if x/y values fall within
  lat/lon numerical ranges. Contract validation is enforced at canonical track
  construction time."
- **Risk**: Medium. The contract exists but is NOT enforced in the CLI or in
  descriptor/primitives/topology functions — they accept any numeric x/y. The
  contract only propagates through `build_canonical_track`.
- **Action needed**: Acknowledge the contract-attached-but-not-enforced-in-all-paths
  gap. See PATCH_RECOMMENDATIONS.md.

## 9. Resampling is canonical

- **Claim**: Arc-length resampling is a frozen, canonical part of the pipeline.
- **Evidence path**: `src/sports_spatial_core/resampling/segment_resample.py`
  (labeled "Stage 1 experimental API")
- **Supported level**: **unsupported**
- **Safe paper wording**: "Segment-first arc-length resampling exists as an
  experimental API (Stage 1). It preserves source-interval traceability and
  segment-boundary awareness. No default step size, gap guard, or sampling
  policy is frozen. Resampling is not part of the canonical pipeline."
- **Risk**: High if claimed as canonical. The module docstring explicitly says
  "⚠️ Experimental."
- **Action needed**: Do NOT claim canonical resampling. Treat as experimental
  evidence only.

## 10. Smoothing policy is frozen

- **Claim**: A coordinate smoothing policy is frozen and integrated into the
  pipeline.
- **Evidence path**: `experiments/exp-005-smoothing-trial/` (experimental only)
- **Supported level**: **unsupported**
- **Safe paper wording**: "Smoothing is characterized in an isolated experiment
  (exp-005) using synthetic jitter pairs. No smoothing policy is frozen, and no
  smoothing step exists in the main pipeline."
- **Risk**: High if claimed. Smoothing is research-only.
- **Action needed**: None for Paper A. Treat exp-005 as supplementary evidence.

## 11. Primitive confidence is perturbation-based

- **Claim**: Primitive confidence scores reflect perturbation survival rates.
- **Evidence path**: `src/sports_spatial_core/primitives/` (confidence is
  threshold-margin × weight + local-consistency × weight)
- **Supported level**: **unsupported**
- **Safe paper wording**: "Confidence scores are deterministic functions of
  threshold margin, local sign/direction consistency, and (for stops) duration
  and radius scores. They are NOT calibrated probabilities and do NOT reflect
  perturbation survival rates."
- **Risk**: Medium if wording is ambiguous. The confidence formula is
  deterministic but heuristic.
- **Action needed**: Use precise language: "deterministic heuristic confidence,"
  not "confidence."

## 12. Topology tolerance policy is documented

- **Claim**: The topology tolerance policy is explicitly documented with
  provenance.
- **Evidence path**: `src/sports_spatial_core/topology/candidates.py`
  (tolerance parameter with default 1e-9); `ARCHITECTURE.md` (missing section)
- **Supported level**: **partially supported**
- **Safe paper wording**: "Topology candidate extraction uses a configurable
  tolerance parameter (default 1e-9 in coordinate units) for intersection
  tests. The tolerance is recorded in candidate parameters. No tolerance-sweep
  policy or tolerance provenance beyond parameter recording is implemented."
- **Risk**: Medium. The tolerance default is an implementation choice, not a
  documented policy with justification.
- **Action needed**: Document the rationale for 1e-9 default. Add tolerance
  provenance to the coordinate contract.

## 13. Perturbation framework exists

- **Claim**: A perturbation framework systematically evaluates representation
  stability.
- **Evidence path**: Individual experiments (exp-004, exp-005, exp-006, exp-007,
  exp-008) each implement ad-hoc perturbation
- **Supported level**: **unsupported** (as a unified framework)
- **Safe paper wording**: "Individual experiments evaluate specific perturbation
  axes (sampling density, coordinate jitter, curvature parameter variation,
  primitive threshold perturbation, topology tolerance sweeps). There is no
  unified perturbation harness that systematically evaluates all artifacts
  under a common perturbation protocol."
- **Risk**: Medium. Without a unified harness, cross-experiment comparison is
  qualitative.
- **Action needed**: Write PATCH_RECOMMENDATIONS.md entry for a unified
  perturbation harness.

## 14. Total-station reference validation exists

- **Claim**: Total-station survey data provides ground-truth reference for
  trajectory validation.
- **Evidence path**: `experiments/exp-009-total-station-reference-validation/`
  (empty directory — planning only)
- **Supported level**: **future work**
- **Safe paper wording**: Not applicable to Paper A. "Total-station reference
  validation is planned (exp-009) but not implemented. Paper A does not
  evaluate absolute positional accuracy."
- **Risk**: N/A — explicitly excluded from Paper A scope.
- **Action needed**: None for Paper A.

## 15. Blind LLM audit exists

- **Claim**: A blind LLM audit workflow exists for evaluating representation
  quality.
- **Evidence path**: `experiments/exp-001-audit-comparison/` (demonstration only)
- **Supported level**: **future work** (for Paper A purposes)
- **Safe paper wording**: Not applicable to Paper A. "A demonstration audit
  comparison (exp-001) generates structured audit contexts but does not
  constitute a validated blind LLM audit protocol. Paper A does not evaluate
  audit quality or LLM reasoning."
- **Risk**: High if Paper A cites exp-001 as audit validation.
- **Action needed**: Exclude from Paper A claims. Reserve for Paper B.

---

## Summary

| # | Claim | Level |
|---|-------|-------|
| 1 | Canonical metric track schema | supported |
| 2 | Descriptor table generation | supported |
| 3 | Primitive candidate extraction | supported |
| 4 | Topology candidate extraction | supported |
| 5 | Symbolic graph | supported |
| 6 | Overlay artifact | supported |
| 7 | Robustness experiments | partially supported |
| 8 | CRS/projection enforced | partially supported |
| 9 | Resampling is canonical | unsupported |
| 10 | Smoothing policy frozen | unsupported |
| 11 | Confidence is perturbation-based | unsupported |
| 12 | Topology tolerance policy documented | partially supported |
| 13 | Perturbation framework exists | unsupported |
| 14 | Total-station validation | future work |
| 15 | Blind LLM audit | future work |

**Paper A can honestly claim 6 supported claims, 3 partially supported claims, and must
explicitly disclaim 4 unsupported claims. 2 claims are future work (out of scope).**
