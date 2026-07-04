# Public Evidence Index

This repository is intentionally public-safe. It maximizes public review of Paper A while withholding trajectory-derived artifacts and private planning details.

## Publicly Included

| Public file | What it supports |
| --- | --- |
| `manuscript/PAPER_A_DRAFT_v0.10.md` | Public-safe manuscript draft with restricted-asset notes. |
| `manuscript/PAPER_A_DRAFT_v0.10_CLAIM_AUDIT_ADDENDUM.md` | Public-safe audit of v0.10 wording changes. |
| `manuscript/FIGURE_TABLE_ASSETS_v0.2.md` | Figure and table plan with private artifact boundaries. |
| `FIGURES_AND_TABLES.md` | GitHub-rendered public-safe figure and table index. |
| `figures/figure1_workflow.md` | Public workflow figure rendered with Mermaid. |
| `figures/figure2_restricted_overlay.md` | Public note explaining why the private overlay is withheld. |
| `figures/figure3_sensitivity_overview.md` | Public staged sensitivity overview rendered with Mermaid. |
| `tables/table1_representation_summary.md` | Public rendered representation summary table. |
| `tables/table2_provenance_score_tolerance_semantics.md` | Public rendered provenance, score, and tolerance semantics table. |
| `tables/table3_staged_sensitivity_summary.md` | Public rendered staged sensitivity summary table. |
| `evidence/CLAIMS_LEDGER.md` | Public claim boundaries. |
| `evidence/LIMITATIONS.md` | Public limitations without private planning details. |
| `evidence/CANDIDATE_AND_TOLERANCE_DOCTRINE.md` | Candidate, tolerance, and score terminology. |
| `evidence/ROBUSTNESS_EVIDENCE_SUMMARY.md` | Public staged sensitivity summary. |
| `tables/robustness_summary.csv` | Public staged sensitivity aggregation with private planning details removed. |
| `DATA_ACCESS.md` | Explanation of withheld trajectory-derived artifacts. |

## Intentionally Withheld

| Withheld material | Reason |
| --- | --- |
| Source trajectory CSV files | May reveal movement geometry, source-data layout, or location-derived details. |
| Canonical metric trajectory tables | Can reconstruct trajectory geometry. |
| Descriptor tables | Can expose movement geometry and derived trajectory signatures. |
| Primitive, topology, and graph JSON files | Can reveal trajectory structure and derived candidate locations. |
| Overlay HTML/PNG files | Can visually reveal trajectory geometry. |
| Coordinate-provenance JSON files | May contain projection origins or location-derived metadata. |
| Private source code and builder scripts | Not required for public-safe manuscript review and may expose local research implementation details. |
| Private planning documents | Not part of Paper A public evidence. |

## What This Repository Can Support

This repository can support:

- manuscript readability review;
- claim-boundary review;
- checking that Paper A does not overclaim validation, robust detection, sport semantics, or production readiness;
- reviewing staged sensitivity wording at a public-safe level;
- understanding why trajectory-derived artifacts are withheld.

## What This Repository Cannot Support

This repository cannot independently support:

- full packet reproduction;
- private trajectory artifact audit;
- exact recomputation of manuscript tables;
- inspection of private overlay figures;
- verification of coordinate-provenance JSON fields.

Those materials remain private because they may reveal trajectory-level or location-derived information.
