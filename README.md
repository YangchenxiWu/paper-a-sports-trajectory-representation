# Paper A Sports Trajectory Representation

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21193034.svg)](https://doi.org/10.5281/zenodo.21193034)

This is a public-safe companion repository for Paper A:

> A Deterministic Spatial Representation Packet for Sports Trajectories Under Explicit Coordinate, Threshold, and Tolerance Assumptions

The repository contains manuscript drafts, claim-boundary documents, staged sensitivity summaries, and literature notes for a conservative sports-engineering representation paper.

## What This Repository Contains

- `manuscript/`: current manuscript draft and manuscript-support files.
- `evidence/`: claim ledger, limitations, candidate/tolerance doctrine, and staged sensitivity evidence summary.
- `FIGURES_AND_TABLES.md`: public-safe index of GitHub-rendered figure and table views.
- `figures/`: standalone public-safe figure views and restricted-asset notes.
- `tables/`: standalone public-safe rendered tables plus staged sensitivity CSV.
- `CITATION.cff`: citation metadata for GitHub's repository citation panel.
- `LICENSE.md`: public licensing terms and excluded private material boundary.
- `RELEASE_NOTES_v0.10-public-safe.md`: release summary and DOI status note.
- `DATA_ACCESS.md`: explanation of withheld trajectory-derived artifacts.

## What Is Not Included

This public-safe repository intentionally does **not** include:

- source trajectory CSV files;
- canonical track tables;
- descriptor tables;
- primitive/topology/graph JSON artifacts;
- overlay HTML/PNG artifacts;
- coordinate-provenance JSON files;
- private source-code modules from the local `sports-spatial-core` repository.

Those artifacts are retained locally because they can reveal trajectory geometry, source-data layout, or location-derived information.

## Claim Boundary

Paper A is a representation manuscript. It demonstrates assumption-explicit artifact generation under packet-level coordinate, threshold, tolerance, score, and staged sensitivity assumptions.

It does not claim:

- external measurement accuracy;
- robust detection;
- sport-specific semantic interpretation;
- calibrated probability confidence;
- universal CRS enforcement;
- production deployment readiness.

## Current Draft

The current public-safe manuscript draft is:

- `manuscript/PAPER_A_DRAFT_v0.10.md`

The public copy replaces trajectory-revealing figure assets and coordinate/location details with restricted-asset notes. The private working packet retains the full generated artifacts for internal review.

## Citation and License

Please use `CITATION.cff` when citing this public companion repository. The archived version DOI is `10.5281/zenodo.21193034`; the Zenodo concept DOI for all versions is `10.5281/zenodo.21192883`.

Public manuscript, figure, table, and documentation materials are licensed under CC BY 4.0. Any code snippets or scripts later added to this public repository are licensed under MIT unless a file states otherwise. Private trajectory-derived artifacts and private implementation materials are not distributed or licensed by this repository.
