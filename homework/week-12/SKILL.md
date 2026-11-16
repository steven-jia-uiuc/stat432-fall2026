---
name: cluster-one-page
description: >-
  Compare clustering methods and write a one-page report. Use only when the
  user explicitly invokes $cluster-one-page; do not load automatically for
  other analysis requests.
---

# Cluster one page

Use the dataset, observation unit, feature columns, identifiers, and optional
known labels supplied in the invocation. Do not assume a particular dataset.

## Prepare the data

1. Check dimensions, numeric types, missing values, duplicate observations,
   constant features, and unusual observations. Report any important issue.
2. Keep identifiers and known class labels out of all preprocessing, fitting,
   tuning, and method selection. Use labels only after the final fit is fixed.
3. Check what preprocessing has already been done. Explain whether further
   scaling, filtering, or imputation is needed. Do not automatically rescale
   already processed measurements. Set and record random seeds.

## Compare and choose

4. Fit at least three different clustering algorithms, such as K-means,
   hierarchical clustering, and spectral clustering. Different linkage rules
   count as one algorithm. PCA or UMAP alone is not a clustering algorithm.
5. Before fitting, record a reasonable range of cluster counts, tuning values,
   and a minimum cluster size for the sample size. Use several random starts
   for K-means. If using PCA for fitting, explain the retained information.
6. Compare mean silhouette widths using the same preprocessing and distance
   matrix for all methods. Larger values favor clearer separation. Exclude
   fits below the predeclared minimum cluster size; do not choose using labels.
7. For fits within 0.01 of the best eligible silhouette, check stability under
   repeated feature subsampling or observation subsampling, as appropriate.
   Refit the whole pipeline. Compare assignments on shared observations using
   adjusted Rand index (ARI); record the resampling size and number of repeats.
8. Among these near-best fits, choose the largest mean stability ARI. If mean
   ARIs differ by at most 0.01, prefer fewer clusters, then the simpler method.
   If no fit is eligible or separation is weak, say so rather than claim that
   clear natural groups exist. Preserve the comparison calculations separately.

## Explain the selected result

9. Fix the selected method, settings, and assignments before viewing labels.
   Give group sizes and a meaningful plot, such as a PCA scatterplot colored
   by cluster. State the variance shown and that a projection may hide structure.
   If labels are available, use a small cross-tabulation for interpretation.
10. Limit the generated analysis report to ONE PRINTED PAGE, including ALL
    text, figures, and tables. Present clustering results from ONLY ONE selected
    method. Briefly name the other algorithms and selection criteria, but do
    not show their assignments, plots, scores, or result tables in this report.
11. Use simple language. Explain the selected groups and important limitations,
    including sensitivity to preprocessing and the limits of a small sample.
    Label agreement is descriptive, not prediction accuracy or proof of biology.
12. Render and check the printed page for readability and clipping. Keep code,
    seeds, tuning details, and validation records outside the one-page report.
