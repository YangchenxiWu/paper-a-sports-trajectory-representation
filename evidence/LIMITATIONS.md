# Public Limitations

This public-safe limitations file preserves Paper A's claim boundaries without exposing private planning details or trajectory-level artifacts.

## Scope

Paper A is a deterministic representation manuscript. It demonstrates assumption-explicit artifact generation under recorded coordinate, threshold, tolerance, score, and staged sensitivity assumptions.

It is not a validation, performance-analysis, coaching, or production-deployment manuscript.

## Limitations

### Packet-Level Coordinate Enforcement Only

The coordinate contract is enforced for the Paper A packet builder. This does not imply universal CRS enforcement across all possible code paths or downstream uses.

### Private Trajectory Artifacts Withheld

Raw trajectories, canonical tracks, descriptor tables, candidate JSON files, graph artifacts, overlays, and coordinate-provenance JSON files are not included in this public repository. They may reveal movement geometry, source-data layout, or location-derived information.

### Candidate Semantics

Primitive and topology outputs are candidates generated under recorded thresholds and tolerances. They are not confirmed movement structures, sport-specific semantics, or external reference labels.

### Heuristic Scores

Score fields are deterministic heuristic scores. They are not calibrated probabilities, artifact-survival rates, or comparable statistical confidence across candidate types.

### Topology Tolerance

Topology tolerance is a computational predicate tolerance recorded for candidate extraction. It is not a measurement-error model.

### Sampling and Preprocessing Sensitivity

Staged evidence indicates that sampling density, duplicate removal, smoothing choices, curvature sensitivity, primitive thresholds, and topology tolerance affect generated artifacts. These results support sensitivity discussion, not robust validation.

### Two-Sample Demonstration

The manuscript demonstrates artifact generation on two sports trajectory samples. It does not establish generalization across athletes, sports, sessions, devices, or recording conditions.

### Public Repository Boundary

This repository is a public-safe companion repository. It can support public review of manuscript wording, claim boundaries, staged sensitivity summaries, and data-access rationale. It cannot independently reproduce or fully audit the private packet artifacts.
