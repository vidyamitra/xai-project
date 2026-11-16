# Explainable AI (DS5622) Course Project

Faster Formal Explanations by Guided Deletion:Vidya M,Ben George

An abductive explanation (or prime implicant) for a classifier prediction is a minimal subset
of input feature values that guarantees the same prediction across the entire input domain
[1]. Ignatiev et al. (AAAI 2019) give two algorithms for computing abductive explanations
using a Mixed-Integer Linear Programming (MILP) solver. Algorithm 1 tests features for
removal one at a time in a fixed order, using n solver calls for n features, but the size of the
resulting explanation depends on the order in which features are tested. Algorithm 2 finds an
explanation of minimum cardinality by solving an implicit hitting set problem, which requires
many more solver calls. In this report, we study two simple modifications to Algorithm 1 for
ReLU neural networks: (1) we order candidate deletions by the range-scaled input gradient of
the class margin, testing the least sensitive features first, and (2) we test features in contiguous
groups with recursive binary splitting and counterexample reuse. Across 120 held-out test
instances from the UCI breast-cancer (n = 9) and heart-statlog (n = 13) datasets over three
random seeds, gradient-guided group deletion (k = 4) reduces mean explanation size from
5.77 ± 1.25 to 5.48 ± 1.37 features on breast-cancer (p = 0.0130) and from 7.50 ± 1.16 to 6.93 ± 1.22
features on heart-statlog (p = 2.85 × 10−5). This closes about half of the size gap to Algorithm 2
while reducing MILP solver calls by 44.6% to 46.8% relative to Algorithm 1 and running roughly
9× faster than Algorithm 2.
