# Figure and Table Assets v0.2

This file records the main-text figure and table assets integrated into `PAPER_A_DRAFT_v0.10.md`. It uses existing packet artifacts only and does not add new experimental evidence.

## Figure 1. Deterministic Representation Packet Workflow

- Source artifacts: private `artifact_manifest.json`; private `outputs/packet_provenance.json`; private `outputs/provenance.json`
- Current manuscript form: Mermaid workflow embedded in v0.10.
- Intended section: Methods.
- Caption summary: Configured sports trajectory observations are converted into canonical metric trajectories, descriptors, primitive candidates, topology candidates, graph, overlays, provenance, and summaries.
- Forbidden interpretation: Production readiness, external accuracy, or universal CRS enforcement.

## Figure 2. Representative Inspection Overlay

- Source artifacts: private `outputs/overlay.png`; private `outputs/overlay.html`; private `outputs/primitives.json`; private `outputs/topology.json`
- Current manuscript form: restricted-asset note in the public-safe manuscript copy.
- Intended section: Results.
- Caption summary: Representative overlay with generated candidate annotations and linked structured artifact data.
- Forbidden interpretation: Candidate annotations are not true movement structures, ground-reference labels, robust detections, or externally confirmed sport semantics.

## Figure 3. Staged Sensitivity Evidence Overview

- Source artifacts: `tables/robustness_summary.csv`; `ROBUSTNESS_EVIDENCE_SUMMARY.md`
- Current manuscript form: Mermaid overview embedded in v0.10.
- Intended section: Results / Discussion.
- Caption summary: Sensitivity axes include sampling density, gap handling, smoothing, curvature noise, primitive thresholds, and topology tolerance.
- Forbidden interpretation: Unified perturbation benchmark, robust validation, or proof of correct candidate detection.

## Table 1. Two-Sample Representation Summary

- Source artifact: private `outputs/representation_summary.json`
- Current manuscript form: Markdown table embedded in v0.10.
- Intended section: Results.
- Included fields: duration, raw points, post-dedup points, removed exact duplicates, speed statistics, curvature proxy statistics, primitive candidate breakdown by type, topology candidate counts, graph size.
- Forbidden interpretation: Generalization, candidate correctness, unique physical crossings, or external measurement accuracy.

## Table 2. Provenance, Score, and Tolerance Semantics

- Source artifacts: private `outputs/packet_provenance.json`; private `outputs/provenance.json`; private `outputs/representation_summary.json`; `evidence/LIMITATIONS.md`
- Current manuscript form: Markdown table embedded in v0.10.
- Intended section: Methods.
- Included fields: coordinate enforcement scope, input coordinate type, source CRS, projection method, axis convention, units, deduplication policy, score semantics, topology tolerance, parameter locations.
- Forbidden interpretation: Universal CRS enforcement, calibrated probability, perturbation survival, or sensor-error tolerance.
