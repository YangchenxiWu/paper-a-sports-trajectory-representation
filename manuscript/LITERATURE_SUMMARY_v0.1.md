# Literature Summary v0.1

This document summarizes candidate literature for the citation placeholders in
`PAPER_A_DRAFT_v0.4.md`. It is a citation-planning document, not a final
reference list. The summaries below preserve the Paper A claim boundary:
representation and provenance, not validation or robust detection.

## Citation Placeholders in v0.4

| Placeholder topic | Draft location | Citation need |
| --- | --- | --- |
| `[REF: sports tracking systems and sports engineering trajectory analysis]` | Introduction paragraph 1 | Establish that sports trajectory/spatio-temporal tracking is a recognized research input. |
| `[REF: measurement uncertainty in sports tracking]` | Introduction paragraph 1 | Support the general claim that sensor-derived sports measures require attention to uncertainty. |
| `[REF: trajectory preprocessing and sampling effects]` | Introduction paragraph 1 | Support the claim that sampling/preprocessing choices affect trajectory summaries. |
| `[REF: reproducible computational pipelines]` | Introduction paragraph 2 | Support provenance, reproducibility, and traceable computational artifacts. |
| `[REF: uncertainty-aware movement analysis]` | Introduction paragraph 2 | Support conservative interpretation of sensor-derived movement representations. |
| `[REF: reproducibility and transparency in sports engineering]` | Discussion paragraph 6 | Support the value of transparent intermediate representations. |
| `[REF: uncertainty reporting in sensor-based analysis]` | Discussion paragraph 6 | Support the need to report uncertainty/limits for sensor-derived artifacts. |

## Candidate References

### 1. Gudmundsson and Horton, 2016 — Spatio-Temporal Analysis of Team Sports

- **Full citation draft**: Gudmundsson, J., & Horton, M. (2016). *Spatio-Temporal Analysis of Team Sports: A Survey*. arXiv:1602.06994.
- **Source**: <https://arxiv.org/abs/1602.06994>
- **Best fit**: `[REF: sports tracking systems and sports engineering trajectory analysis]`
- **Summary**: This survey describes the growth of spatio-temporal sports analysis using player and ball trajectory data. It frames sports tracking data as a timestamped sequence of locations and surveys computational approaches across machine learning, network science, GIS, computational geometry, computer vision, statistics, and sports science.
- **Use in Paper A**: Good support for the opening claim that sports tracking data are now a common computational input and that trajectory-derived representations matter in sports analysis.
- **Do not use to claim**: Do not use this source to claim Paper A validates candidate detection, solves sport semantics, or improves coaching inference.

### 2. Hu et al., 2023 — Spatio-Temporal Trajectory Similarity Measures

- **Full citation draft**: Hu, D., Chen, L., Fang, H., Fang, Z., Li, T., & Gao, Y. (2023). *Spatio-Temporal Trajectory Similarity Measures: A Comprehensive Survey and Quantitative Study*. arXiv:2303.05012.
- **Source**: <https://arxiv.org/abs/2303.05012>
- **Best fit**: `[REF: trajectory preprocessing and sampling effects]`
- **Summary**: This survey treats trajectory analytics as a core function for mobility-related applications and reviews measures for comparing spatio-temporal trajectories. It is useful because it foregrounds trajectory representation choices, transformations, robustness, and evaluation scenarios.
- **Use in Paper A**: Can support the general point that trajectory computations depend on representation and transformation assumptions.
- **Do not use to claim**: Do not use this as evidence that Paper A's candidates are robust, that its topology is stable, or that its staged sensitivity probes are a formal benchmark.

### 3. Sharma et al., 2022 — Spatiotemporal Data Mining

- **Full citation draft**: Sharma, A., Jiang, Z., & Shekhar, S. (2022). *Spatiotemporal Data Mining: A Survey*. arXiv:2206.12753.
- **Source**: <https://arxiv.org/abs/2206.12753>
- **Best fit**: `[REF: trajectory preprocessing and sampling effects]`; secondary fit for broader spatiotemporal representation context.
- **Summary**: This survey reviews spatiotemporal data mining problems and methods and emphasizes that spatiotemporal data introduce domain-specific challenges beyond ordinary relational data. It is not sports-specific, but it helps situate Paper A within broader spatiotemporal computational analysis.
- **Use in Paper A**: Useful as a background citation for why spatiotemporal data require explicit representation choices.
- **Do not use to claim**: Do not use it to support any sport-specific measurement claim or any Paper A validation claim.

### 4. Cuevas-Vicenttin et al., 2013 — Scientific Workflows and Provenance

- **Full citation draft**: Cuevas-Vicenttin, V., Dey, S., Kohler, S., Riddle, S., & Ludäscher, B. (2013). *Scientific Workflows and Provenance: Introduction and Research Opportunities*. arXiv:1311.4610.
- **Source**: <https://arxiv.org/abs/1311.4610>
- **Best fit**: `[REF: reproducible computational pipelines]`
- **Summary**: This paper introduces scientific workflows and provenance as mechanisms for reusable, inspectable, and reproducible computational science. It directly supports the idea that workflow outputs should retain lineage and execution context.
- **Use in Paper A**: Strong support for packet provenance, artifact lineage, and reproducibility framing.
- **Do not use to claim**: Do not use it to imply Paper A follows a formal W3C PROV model or implements a general scientific workflow system.

### 5. Leipzig et al., 2020 — Metadata in Reproducible Computational Research

- **Full citation draft**: Leipzig, J., Nüst, D., Hoyt, C. T., Soiland-Reyes, S., Ram, K., & Greenberg, J. (2020). *The role of metadata in reproducible computational research*. arXiv:2006.08589.
- **Source**: <https://arxiv.org/abs/2006.08589>
- **Best fit**: `[REF: reproducible computational pipelines]`; secondary fit for `[REF: reproducibility and transparency in sports engineering]`
- **Summary**: This article argues that metadata is central to reproducible computational research because it records context for inputs, tools, pipelines, and outputs. It is a good match for Paper A's emphasis on packet metadata, coordinate assumptions, score semantics, and tolerance semantics.
- **Use in Paper A**: Strong support for explicit metadata around generated artifacts.
- **Do not use to claim**: Do not use it to imply that Paper A is FAIR-complete or that all repository artifacts are fully standardized.

### 6. Meijer et al., 2024 — Proactive Reproducible Analysis Transparency

- **Full citation draft**: Meijer, P., Howard, N., Liang, J., Kelsey, A., Subramanian, S., Johnson, E., et al. (2024). *Provide Proactive Reproducible Analysis Transparency with Every Publication*. arXiv:2408.09103.
- **Source**: <https://arxiv.org/abs/2408.09103>
- **Best fit**: `[REF: reproducibility and transparency in sports engineering]`
- **Summary**: This paper argues for granular analysis transparency in computationally intensive research and emphasizes complete reproducible traces from data to methods and executable tools. It is not sports-specific, but it strongly supports the publication-side rationale for Paper A's packet and provenance design.
- **Use in Paper A**: Good support for the Discussion sentence that the packet has value as a reproducible intermediate representation.
- **Do not use to claim**: Do not use it to claim Paper A has full publication-grade reproducibility across every environment or system dependency.

### 7. Garnacho-Castano et al., 2022 — Polar V800 Reliability and Validity

- **Full citation draft**: Garnacho-Castano, M. V., Faundez-Zanuy, M., Serra-Paya, N., Mate-Munoz, J. L., Lopez-Xarbau, J., & Vila-Blanch, M. (2022). *Reliability and Validity of the Polar V800 Sports Watch for Estimating Vertical Jump Height*. arXiv:2203.16442.
- **Source**: <https://arxiv.org/abs/2203.16442>
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`, but only as a device-validation example.
- **Summary**: This study evaluates reliability and validity of a sports watch measure against reference systems for vertical jump height. It is useful as an example that sports-device outputs require reliability and validity assessment, but it is not a trajectory-positioning paper.
- **Use in Paper A**: Use only if a general sentence is needed saying wearable/sports-device measurements are commonly evaluated against reliability/validity criteria.
- **Do not use to claim**: Do not use this as evidence about GNSS trajectory accuracy, coordinate error, topology correctness, or Paper A validation.

## Recommended Citation Mapping for v0.4

| v0.4 placeholder | Recommended citation set | Notes |
| --- | --- | --- |
| `[REF: sports tracking systems and sports engineering trajectory analysis]` | Gudmundsson and Horton (2016) | Best current match. Sports-specific and trajectory-focused. |
| `[REF: measurement uncertainty in sports tracking]` | Garnacho-Castano et al. (2022), plus one still-needed GNSS/team-sport tracking validity paper | Current source is device-validity adjacent but not trajectory-specific. Add a GNSS/tracking validity source before final references. |
| `[REF: trajectory preprocessing and sampling effects]` | Hu et al. (2023); Sharma et al. (2022) | Good for broad trajectory-analysis assumptions. Add a more specific trajectory preprocessing source if available. |
| `[REF: reproducible computational pipelines]` | Cuevas-Vicenttin et al. (2013); Leipzig et al. (2020) | Strong match for provenance/metadata framing. |
| `[REF: uncertainty-aware movement analysis]` | Hu et al. (2023); Garnacho-Castano et al. (2022) cautiously | Needs stronger movement/sensor uncertainty source before final manuscript. |
| `[REF: reproducibility and transparency in sports engineering]` | Meijer et al. (2024); Leipzig et al. (2020) | Computational transparency sources are good, but not sport-specific. |
| `[REF: uncertainty reporting in sensor-based analysis]` | Garnacho-Castano et al. (2022) cautiously; still-needed sensor uncertainty reporting source | Needs a stronger sensor-analysis uncertainty source. |

## Remaining Literature Gaps

Before converting v0.4 placeholders into final references, find stronger sources
for:

1. **GNSS/player-tracking measurement validity and reliability in sport**  
   Needed to support the measurement-uncertainty sentence without relying on a
   vertical-jump wearable study.

2. **Trajectory preprocessing / sampling effects in movement or mobility data**  
   Current surveys support the broad idea, but a more direct paper on sampling,
   simplification, or preprocessing effects would strengthen the Introduction.

3. **Sensor-derived movement uncertainty reporting**  
   Needed for the Discussion sentence about uncertainty boundaries in
   sensor-based analysis.

## Safe Manuscript Use

Safe wording supported by the current candidate literature:

> Sports trajectory data are widely used as computational inputs, but their
> downstream interpretation depends on coordinate, sampling, preprocessing, and
> metadata assumptions. Provenance and metadata improve reproducibility and make
> computational artifacts easier to inspect.

Unsafe wording:

> Prior literature validates the Paper A packet, proves candidate correctness,
> establishes robust detection, or supports externally accurate topology
> extraction.

## GNSS / Player-Tracking Validity Addendum

These references were added specifically to cover the weak GNSS/player-tracking
validity and reliability gap.

### 8. Cummins et al., 2013 — GPS and Microtechnology Sensors in Team Sports

- **Full citation draft**: Cummins, C., Orr, R., O'Connor, H., & West, C. (2013). Global Positioning Systems (GPS) and microtechnology sensors in team sports: A systematic review. *Sports Medicine, 43*(10), 1025-1042. https://doi.org/10.1007/s40279-013-0069-2
- **Source checked by**: Crossref title query, DOI `10.1007/s40279-013-0069-2`.
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`
- **Summary**: This systematic review is directly relevant to team-sport GPS and microtechnology sensor use. It supports the general premise that player-tracking outputs require explicit attention to device capabilities, measurement conditions, and validity/reliability limits.
- **Use in Paper A**: Strong support for introducing GNSS/player-tracking uncertainty and measurement-boundary concerns.
- **Do not use to claim**: Do not use it to claim Paper A validates GNSS accuracy or corrects measurement error.

### 9. Scott et al., 2016 — Validity and Reliability of GPS in Team Sport

- **Full citation draft**: Scott, M. T. U., Scott, T. J., & Kelly, V. G. (2016). The validity and reliability of global positioning systems in team sport. *Journal of Strength and Conditioning Research, 30*(5), 1470-1490. https://doi.org/10.1519/JSC.0000000000001221
- **Source checked by**: Crossref title query, DOI `10.1519/JSC.0000000000001221`.
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`; `[REF: uncertainty reporting in sensor-based analysis]`
- **Summary**: This review focuses directly on validity and reliability of GPS in team-sport settings. It is a stronger fit than the earlier Polar V800 vertical-jump example for supporting Paper A's caution around sensor-derived trajectory and movement summaries.
- **Use in Paper A**: Strong support for conservative language that GNSS/player-tracking measurements are finite observations whose interpretation depends on measurement reliability and validity limits.
- **Do not use to claim**: Do not use it to claim the Paper A samples have known GNSS error distributions or have been externally validated.

### 10. Varley et al., 2012 — GPS Instantaneous Velocity

- **Full citation draft**: Varley, M. C., Fairweather, I. H., & Aughey, R. J. (2012). Validity and reliability of GPS for measuring instantaneous velocity during acceleration, deceleration, and constant motion. *Journal of Sports Sciences, 30*(2), 121-127. https://doi.org/10.1080/02640414.2011.627941
- **Source checked by**: Crossref title query, DOI `10.1080/02640414.2011.627941`.
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`; `[REF: uncertainty-aware movement analysis]`
- **Summary**: This study is useful for supporting the narrower point that GPS-derived movement quantities can vary with motion regime, particularly acceleration and deceleration contexts. It supports Paper A's caution around derivative-like quantities such as speed, heading change, and curvature proxy.
- **Use in Paper A**: Use as support for the claim that downstream movement summaries are sensitive to measurement and motion conditions.
- **Do not use to claim**: Do not use it to quantify Paper A's coordinate error, speed error, or curvature error.

### 11. Johnston et al., 2014 — 10 Hz and 15 Hz GPS Units

- **Full citation draft**: Johnston, R. J., Watsford, M. L., Kelly, S. J., Pine, M. J., & Spurrs, R. W. (2014). Validity and interunit reliability of 10 Hz and 15 Hz GPS units for assessing athlete movement demands. *Journal of Strength and Conditioning Research, 28*(6), 1649-1655. https://doi.org/10.1519/JSC.0000000000000323
- **Source checked by**: Crossref title query, DOI `10.1519/JSC.0000000000000323`.
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`
- **Summary**: This paper supports the point that GPS unit sampling frequency and interunit differences matter for athlete movement-demand assessment. It is useful background for Paper A's sampling and measurement caution.
- **Use in Paper A**: Supports conservative discussion of sampling and device-dependent measurement limits.
- **Do not use to claim**: Do not use it to claim Paper A normalizes across devices or sampling rates.

### 12. Pino-Ortega et al., 2022 — Local Positioning Systems in Team Sport

- **Full citation draft**: Pino-Ortega, J., Oliva-Lozano, J. M., Gantois, P., Nakamura, F. Y., & Rico-Gonzalez, M. (2022). Comparison of the validity and reliability of local positioning systems against other tracking technologies in team sport: A systematic review. *Proceedings of the Institution of Mechanical Engineers, Part P: Journal of Sports Engineering and Technology, 236*(2), 73-82. https://doi.org/10.1177/1754337120988236
- **Source checked by**: Crossref title query, DOI `10.1177/1754337120988236`.
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`; `[REF: uncertainty reporting in sensor-based analysis]`
- **Summary**: This JSET-relevant systematic review compares validity and reliability of local positioning systems against other team-sport tracking technologies. It is valuable for a JSET-style manuscript because it places measurement validity/reliability concerns inside the target journal's domain.
- **Use in Paper A**: Strong support for the Introduction and Discussion claims that tracking-derived representations should remain explicit about measurement assumptions and interpretation limits.
- **Do not use to claim**: Do not use it to claim Paper A evaluates local positioning systems or compares tracking technologies.

### 13. Akenhead et al., 2014 — Acceleration-Dependent GPS Validity

- **Full citation draft**: Akenhead, R., French, D., Thompson, K. G., & Hayes, P. R. (2014). The acceleration dependent validity and reliability of 10 Hz GPS. *Journal of Science and Medicine in Sport, 17*(5), 562-566. https://doi.org/10.1016/j.jsams.2013.08.005
- **Source checked by**: Crossref title query, DOI `10.1016/j.jsams.2013.08.005`.
- **Best fit**: `[REF: measurement uncertainty in sports tracking]`; `[REF: uncertainty-aware movement analysis]`
- **Summary**: This study is useful for supporting the specific point that GPS validity and reliability can depend on movement conditions such as acceleration. It strengthens Paper A's conservative framing around speed, heading-change, and curvature-derived summaries.
- **Use in Paper A**: Supports the Introduction claim that sport-tracking outputs should be interpreted through measurement and motion-condition limits.
- **Do not use to claim**: Do not use it to quantify error in Paper A samples or to justify any specific threshold.

## Updated Recommended Citation Mapping for v0.5

| v0.4 placeholder | Recommended citation set | Notes |
| --- | --- | --- |
| `[REF: sports tracking systems and sports engineering trajectory analysis]` | Gudmundsson and Horton (2016); Cummins et al. (2013) | Sports trajectory/tracking context. |
| `[REF: measurement uncertainty in sports tracking]` | Cummins et al. (2013); Scott et al. (2016); Varley et al. (2012); Johnston et al. (2014); Akenhead et al. (2014); Pino-Ortega et al. (2022) | Stronger GNSS/player-tracking validity coverage now available. |
| `[REF: trajectory preprocessing and sampling effects]` | Hu et al. (2023); Johnston et al. (2014); Varley et al. (2012) | Mix broad trajectory representation and sports-GPS sampling/motion-regime evidence. |
| `[REF: reproducible computational pipelines]` | Cuevas-Vicenttin et al. (2013); Leipzig et al. (2020) | Strong match for provenance/metadata framing. |
| `[REF: uncertainty-aware movement analysis]` | Scott et al. (2016); Varley et al. (2012); Akenhead et al. (2014); Pino-Ortega et al. (2022) | Use conservatively for measurement-boundary framing. |
| `[REF: reproducibility and transparency in sports engineering]` | Meijer et al. (2024); Leipzig et al. (2020) | Computational transparency sources are still broader than sports engineering. |
| `[REF: uncertainty reporting in sensor-based analysis]` | Scott et al. (2016); Pino-Ortega et al. (2022); Varley et al. (2012) | Stronger than v0.1. |

## Current Status

This literature set is now sufficient for a v0.5 referenced draft. The strongest
coverage is sports spatio-temporal tracking, GNSS/player-tracking validity and
reliability, and computational provenance/metadata. Remaining citation work
before final submission should focus on replacing arXiv preprints with final
journal versions where available and checking JSET reference style.
