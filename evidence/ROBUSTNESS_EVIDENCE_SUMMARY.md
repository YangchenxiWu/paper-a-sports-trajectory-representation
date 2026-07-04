# Robustness Evidence Summary

This document aggregates existing staged experiment evidence for Paper A. It
uses only existing experiment documentation and outputs from `exp-002` through
`exp-008`.

This is not a unified validation benchmark. The current evidence is staged,
experimental, and heterogeneous: each experiment probes one sensitivity axis
under fixed assumptions. It supports bounded manuscript wording about
sensitivity, stability boundaries, candidate persistence, and
tolerance-conditioned behavior. It does not support claims of robust detection,
ground-truth validation, or external measurement accuracy.

The tabular version is:

- `tables/robustness_summary.csv`

## Evidence Boundary

Paper A can use this evidence to show that the representation pipeline exposes
assumptions and failure modes. It cannot use this evidence to claim that the
pipeline detects true movement events or true topology.

The experiments are completed staged probes:

- `exp-002`: arc-length resampling sensitivity;
- `exp-002b`: segment-first resampling prototype;
- `exp-003`: segment-resample API metadata validation;
- `exp-004`: synthetic sampling-density invariance check;
- `exp-005`: smoothing sensitivity trial;
- `exp-006`: curvature estimator sensitivity;
- `exp-007`: primitive candidate persistence under jitter;
- `exp-008`: topology tolerance-conditioned behavior.

The missing piece remains a unified perturbation framework. The rows below must
not be rewritten as a single benchmark or statistical validation suite.

## Summary By Experiment

| Experiment | Stage | Main Finding | Safe Use |
| --- | --- | --- | --- |
| exp-002 | Stage 1 trajectory normalization | Arc-length resampling exposes step-sensitive primitive counts and locations. | Limitations: sampling affects candidate artifacts; resampling is experimental. |
| exp-002b | Stage 1 segment-first prototype | Gap-aware per-segment processing changes topology counts substantially. | Discussion: gap handling is a stability boundary, not proof of better detection. |
| exp-003 | Stage 1 API validation | Segment-resample metadata was internally consistent on two real samples and five step sizes. | Methods: experimental API can be described as internally checked. |
| exp-004 | Stage 1 synthetic density check | Straight, L-shape, and gap cases matched; sparse curved arcs retained approximation error. | Results: simple structures normalize better than curved sparse observations. |
| exp-005 | Stage 2 smoothing | Smoothing improved position RMS but did not restore clean structural descriptors. | Limitations: smoothing is not transparent to geometry. |
| exp-006 | Stage 3 curvature | Coordinate noise strongly inflates apparent curvature; jitter dominated nonuniform sampling in the tested sine case. | Results: curvature method is explicit but has a measured noise floor. |
| exp-007 | Stage 4 primitives | Primitive candidate counts and boundaries are noise- and threshold-sensitive. | Limitations: primitive outputs are threshold-conditioned candidates. |
| exp-008 | Stage 5 topology | Topology candidates are tolerance-conditioned; endpoint/overlap cases are fragile under jitter. | Discussion: tolerance is an observation parameter, not a truth boundary. |

## Manuscript Language

Safe wording:

> Existing staged experiments characterize how sampling density, gap handling,
> smoothing, curvature estimation, primitive thresholds, and topology tolerance
> affect the generated representation artifacts. These experiments support
> sensitivity and limitation claims, not robust detection or external
> validation claims.

Do not write:

> The pipeline robustly detects primitives and topology.

Use:

> The pipeline deterministically emits primitive and topology candidates under
> fixed thresholds and tolerances, and staged experiments expose where those
> candidates persist, shift, appear, or disappear under controlled changes.

## Completed Evidence Versus Missing Framework

Completed:

- individual step sweeps;
- synthetic sparse/dense comparisons;
- synthetic jitter probes;
- internal metadata consistency checks;
- topology tolerance sweeps;
- candidate count and boundary-shift summaries.

Still missing:

- a unified perturbation harness;
- cross-experiment matching rules;
- artifact-level survival rates;
- graph persistence metrics;
- real measurement-error calibration;
- total-station reference validation;
- blind LLM audit validation.

## Paper A Implication

Paper A is closer to a defensible representation paper after this aggregation,
because the manuscript can now cite one packet-local table for staged
sensitivity evidence. The aggregation does not remove the main scientific
blockers: coordinate assumptions, heuristic confidence, threshold sensitivity,
tolerance-conditioned topology, and lack of unified perturbation validation must
remain explicit.
