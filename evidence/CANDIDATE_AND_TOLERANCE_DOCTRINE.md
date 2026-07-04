# Candidate and Tolerance Doctrine

This packet uses deterministic code to produce inspectable representation
artifacts. It does not validate physical truth.

## Primitive Candidates

Primitive outputs are threshold-conditioned candidates. A
`stop_candidate`, `turn_candidate`, `left_turn_candidate`,
`right_turn_candidate`, `high_curvature_segment`, or
`direction_reversal_candidate` means that the deterministic extractor fired
under the recorded descriptor method and threshold parameters.

Primitive candidates are not ground-truth movement events, coaching labels, or
validated sport semantics.

## Topology Candidates

Topology outputs are tolerance-conditioned candidates. A
`self_intersection_candidate`, `loop_candidate`, or
`repeated_path_candidate` means that the deterministic extractor fired under
the recorded coordinate contract and tolerance parameters.

The topology tolerance is an observation parameter. It is not a ground-truth
boundary and must not be interpreted as a physical statement about the real
trajectory.

## Confidence Scores

Confidence scores in this packet are deterministic heuristic scores. They are
derived from local evidence such as threshold margins, local consistency,
duration, length, endpoint position, or segment separation depending on the
extractor.

They are not calibrated probabilities, not perturbation survival rates, and not
comparable as statistical confidence across primitive or topology types.

## Paper A Boundary

Paper A demonstrates artifact generation under documented coordinate,
threshold, and tolerance assumptions. It does not provide external validation.

The packet must not claim:

- total-station validation;
- GNSS error characterization;
- blind LLM audit validation;
- robust detection;
- motion recovery;
- autonomous sports AI;
- ground-truth event validation.

Total-station validation and blind audit remain future work outside Paper A.
