# Computational Geometry Literature Supplement v0.1

This supplement records computational-geometry references that can support the Paper A discussion of line-segment intersection, geometric predicates, numerical tolerance, and interpretation limits for topology candidates. These references are background support only. They do not imply that Paper A implements exact arithmetic, floating-point filters, a sweep-line algorithm, topology persistence, or robust detection.

## Candidate References for Main Text

### de Berg et al. (2008)

de Berg, M., Cheong, O., van Kreveld, M., & Overmars, M. (2008). *Computational Geometry: Algorithms and Applications* (3rd ed.). Springer.

Use: Standard computational-geometry background for segment intersection and finite geometric algorithms.

Safe integration: Cite in Methods 2.5 to establish that segment intersection is a standard computational-geometry operation.

Forbidden interpretation: Do not imply that the packet implements textbook sweep-line algorithms or exact topology algorithms.

### Bentley and Ottmann (1979)

Bentley, J. L., & Ottmann, T. A. (1979). Algorithms for reporting and counting geometric intersections. *IEEE Transactions on Computers, C-28*(9), 643-647.

Use: Classical reference for reporting and counting line-segment intersections.

Safe integration: Cite alongside de Berg et al. when describing topology candidate extraction as line-segment-intersection based computation.

Forbidden interpretation: Do not imply that Paper A reports unique physical crossings or uses the Bentley-Ottmann algorithm.

### Shewchuk (1997)

Shewchuk, J. R. (1997). Adaptive precision floating-point arithmetic and fast robust geometric predicates. *Discrete & Computational Geometry, 18*, 305-363. https://doi.org/10.1007/PL00009321

Use: Background support that floating-point geometric predicates can require numerical-robustness treatment.

Safe integration: Cite when explaining why the packet distinguishes computational predicate tolerance from measurement-error tolerance.

Forbidden interpretation: Do not imply that Paper A implements adaptive precision predicates, exact arithmetic, or a mathematically robust geometry kernel.

### Bartels et al. (2022)

Bartels, T., Fisikopoulos, V., & Weiser, M. (2022). Fast floating-point filters for robust predicates. arXiv:2208.00497. https://arxiv.org/abs/2208.00497

Use: Optional modern background for floating-point filters and robust predicates.

Safe integration: Keep out of the main v0.6 text unless a reviewer asks for a modern reference. The main manuscript can stay cleaner with de Berg et al., Bentley and Ottmann, and Shewchuk.

Forbidden interpretation: Do not imply Paper A implements generated robust predicates or state-of-the-art predicate filtering.

## Recommended Manuscript Placement

Methods 2.5 should include one sentence that positions line-segment intersection and predicate tolerance within computational geometry:

> Line-segment intersection and predicate decisions are standard computational-geometry operations, and numerical robustness of such predicates is a recognized implementation issue (Bentley and Ottmann, 1979; de Berg et al., 2008; Shewchuk, 1997).

The following sentence should immediately constrain the claim:

> Paper A records tolerance semantics and generated candidates; it does not claim exact-arithmetic predicates, robust topology recovery, or persistence-tested topology detection.

## Claim Boundary

These references support the manuscript's limitation language, not stronger algorithmic claims. The safe claim is that Paper A treats topology outputs as tolerance-conditioned topology candidates and records computational predicate tolerance separately from sensor-error tolerance.
