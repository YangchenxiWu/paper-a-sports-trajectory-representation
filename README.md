# Representation Packet Technical Report

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21340626.svg)](https://doi.org/10.5281/zenodo.21340626)

This public-safe companion repository contains the **Representation Packet
Technical Report v1.0.0**, released as a **Preprint / Technical Report** on
2026-07-13. It is **not peer reviewed**.

The report documents a deterministic representation layer for finite, noisy
sports trajectories under explicit coordinate, threshold, tolerance, score,
and staged sensitivity assumptions. It documents representation and
interpretation boundaries; it does not present application-specific validation.

## Release identity

- Release branch: `codex/representation-packet-technical-report-v1.0.0`
- Git tag: `representation-packet-technical-report-v1.0.0`
- Version DOI: `10.5281/zenodo.21340626`
- Zenodo concept DOI: `10.5281/zenodo.21192883`
- Historical public version: `v0.10.3-public-safe`
- Historical version DOI: `10.5281/zenodo.21193034`

## What This Repository Contains

- `manuscript/`: the technical-report manuscript and historical public-safe
  manuscript-support files.
- `evidence/`: claim ledger, limitations, candidate/tolerance doctrine, and
  staged sensitivity evidence summary.
- `FIGURES_AND_TABLES.md`: public-safe index of figure and table views.
- `figures/`: standalone public-safe figure views and restricted-asset notes.
- `tables/`: standalone public-safe rendered tables plus staged sensitivity
  CSV.
- `CITATION.cff`: citation metadata for the current release.
- `RELEASE_NOTES_v1.0.0-technical-report.md`: current release summary.
- `DATA_ACCESS.md`: explanation of withheld trajectory-derived artifacts.

## What Is Not Included

This public-safe repository intentionally does **not** include:

- source trajectory CSV files;
- canonical track tables;
- descriptor tables;
- primitive/topology/graph JSON artifacts;
- overlay HTML/PNG artifacts;
- projection origins or location-resolving provenance;
- private source-code modules from the local `sports-spatial-core` repository.

Those materials remain private because they can reveal trajectory geometry,
source-data layout, or location-derived information.

## Claim Boundary

The technical report is a representation contribution. It demonstrates
assumption-explicit artifact generation under packet-level coordinate,
threshold, tolerance, score, and staged sensitivity assumptions.

It does not claim:

- external measurement accuracy;
- robust detection;
- sport-specific semantic interpretation;
- calibrated probability confidence;
- universal CRS enforcement;
- production deployment readiness;
- application-specific validation.

## Historical material

The earlier public-safe manuscript draft remains available at
`manuscript/PAPER_A_DRAFT_v0.10.md` as historical release material. The current
technical report is
`manuscript/REPRESENTATION_PACKET_TECHNICAL_REPORT_v1.0.0.md`.

## Citation and License

Please use `CITATION.cff` when citing this technical report. Public manuscript,
figure, table, and documentation materials are licensed under CC BY 4.0. Any
code snippets or scripts later added to this public repository are licensed
under MIT unless a file states otherwise. Private trajectory-derived artifacts
and private implementation materials are not distributed or licensed by this
repository.
