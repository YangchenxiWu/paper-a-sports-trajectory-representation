# Paper A Draft v0.10 Claim Audit Addendum

This addendum audits substantive changes introduced in `PAPER_A_DRAFT_v0.10.md` relative to `PAPER_A_DRAFT_v0.9.md`. It focuses on duplicate removal interpretation, per-sample provenance layout, primitive candidate breakdown, upstream elevation smoothing wording, and angular parameter notation.

## Audit Table

| Location | New or sharpened claim | Evidence source | Status | Boundary / forbidden interpretation |
| --- | --- | --- | --- | --- |
| Methods 2.1 and README | `outputs/provenance.json` is last-sample projection-and-dedup provenance, while both samples' coordinate contracts and summaries are preserved in `outputs/representation_summary.json`; packet layout is described in `outputs/packet_provenance.json`. | `outputs/packet_provenance.json.artifact_layout`; `outputs/representation_summary.json`; `README.md`. | Supported | Do not imply `provenance.json` alone contains per-sample full-pipeline provenance. |
| Methods 2.2 | Upstream-smoothed elevation appears in the skiing source table as source metadata, not as a Paper A `x/y` smoothing policy. | Source CSV columns; `LIMITATIONS.md` no smoothing policy; `outputs/provenance.json.preprocessing`. | Supported with boundary | Do not imply the packet applies coordinate smoothing or that upstream elevation smoothing validates geometry. |
| Methods 2.3 and Results 3.2 | Skiing removes 323 consecutive exact duplicates (48.9%); running removes 1899 (68.6%). | `outputs/representation_summary.json.point_counts`; arithmetic from raw and post-dedup counts. | Supported | Do not infer device behavior, stationary behavior, or export policy as the cause. |
| Methods 2.5 | Turn and reversal thresholds are reported as 0.5236 rad (pi/6, 30 degrees) and 2.0944 rad (2pi/3, 120 degrees). | `outputs/representation_summary.json.samples[*].pipeline_parameters`; `artifact_manifest.json.parameters`. | Supported | Decimal precision is notation for configured constants, not empirical precision. |
| Table 1 and Results 3.2 | Primitive candidate totals are broken down by candidate type for each sample. | `outputs/representation_summary.json.samples[*].primitive_summary.by_type`. | Supported | Candidate counts are not sport-specific events, movement truth, or external correctness. |
| Limitations | Duplicate-row cause is not available in packet metadata. | `outputs/representation_summary.json`; source CSV inspection; absence of cause metadata. | Supported with boundary | Do not speculate beyond observed consecutive exact duplicates. |

## Sensitive Wording Review

- Duplicate removal is reported as observed consecutive-exact-duplicate removal, not as a diagnosed device or behavior mechanism.
- Upstream elevation smoothing is separated from Paper A's no-additional-`x/y`-smoothing boundary.
- `outputs/provenance.json` is explicitly scoped to the last generated sample to avoid misleading per-sample provenance interpretation.

## Forbidden-Claim Check

The v0.10 changes do not claim:

- robust detection;
- external measurement accuracy;
- candidate correctness;
- sport-specific semantic interpretation;
- coaching insight or performance outcome;
- injury-risk assessment;
- device-level validity;
- athlete, session, or device generalization;
- universal CRS enforcement;
- unified perturbation framework;
- production readiness.

## Conclusion

The v0.10 draft addresses reviewer-facing clarity gaps without changing Paper A's core claim boundary. It adds duplicate-rate interpretation, per-sample provenance cross-reference, primitive candidate breakdowns, upstream elevation-smoothing boundary wording, and clearer angular parameter notation.
