# Table 3. Staged Sensitivity Summary

| Category | Public question | Public finding | Safe manuscript use | Public boundary |
| --- | --- | --- | --- | --- |
| Sampling density | Do generated candidates change under sampling changes? | Candidate counts and descriptor summaries vary with sampling condition. | Supports sensitivity wording around sampling-conditioned representation. | Not robust detection and not a validation benchmark. |
| Gap handling | Does gap handling affect generated representation? | Gap policy changes downstream representation behavior. | Supports explicit treatment of preprocessing assumptions. | Does not identify a universally correct gap policy. |
| Smoothing | Does smoothing remove downstream sensitivity? | Smoothing changes descriptor and candidate behavior but does not by itself establish physical recovery. | Supports cautious discussion of smoothing-conditioned behavior. | Does not prove measurement-noise correction. |
| Curvature sensitivity | How does the curvature proxy respond to noise-like changes? | Curvature proxy behavior is sensitive to configured perturbation and preprocessing conditions. | Supports bounded wording for curvature descriptors. | Does not establish physical continuous curvature. |
| Primitive thresholds | Do primitive candidates persist across threshold conditions? | Candidate persistence depends on configured thresholds and sample conditions. | Supports threshold-conditioned primitive candidate terminology. | Does not prove candidate correctness. |
| Topology tolerance | Do topology candidates depend on tolerance? | Topology candidate persistence depends on the computational tolerance and geometry condition. | Supports tolerance-conditioned topology candidate terminology. | Does not prove unique physical crossings or sensor-error tolerance. |

**Caption draft:** Public-safe staged sensitivity summary used to constrain Results and Discussion wording. The evidence is staged and experimental, not a unified validation benchmark.

**Source basis:** Public `tables/robustness_summary.csv` and public staged sensitivity summary.

**Forbidden interpretation:** This table does not support robust validation, external accuracy, ground-truth detection, or universal stability claims.
