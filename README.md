# PCA Variance Filtering

## Methodological evaluation of variance-based feature filtering effects on PCA structure in high-dimensional gene expression data

---

## Overview

This repository presents a **method-focused analysis** evaluating how variance-based feature filtering reshapes the behavior of Principal Component Analysis (PCA) in high-dimensional gene expression datasets.

The objective is **not biological discovery**, but to examine how upstream preprocessing decisions influence:

- variance concentration across principal components,
- cumulative variance efficiency,
- PCA geometry in sample space,
- and gene-level contributions to dominant axes.

The project is designed to reflect analytical reasoning commonly required in **translational research and industry settings**, where preprocessing choices critically shape downstream interpretations.

---

## Study Design

Two controlled PCA scenarios were evaluated:

- **Scenario A:** No feature filtering  
- **Scenario B:** Variance-based gene filtering  

All comparisons isolate the effect of feature reduction on PCA behavior.  
No supervised labels, classification tasks, or predictive objectives are involved.

---

## Data

- **Data type:** Gene expression count data (RNA-seq)
- **Source:** Public Gene Expression Omnibus (GEO)
- **Dataset:** Tumor-Educated Platelet (TEP) RNA-seq cohort

The dataset comprises a large number of biologically independent samples and heterogeneous conditions, making it suitable for stress-testing PCA behavior under variance-based feature reduction.

Raw data are publicly available from GEO and were **not redistributed** in this repository.

---

## Processing Summary

Conceptual analytical flow:

Raw counts  
→ CPM normalization  
→ log₂(x + 1) transformation  
→ gene-wise variance estimation  
→ controlled feature filtering  
→ PCA  
→ comparative analyses  

This structure emphasizes transparency of analytical decisions while remaining independent of any specific implementation.

---

## Key Outputs

### Variance Structure
Scree plots show that variance-based filtering concentrates variance into earlier components, reducing dispersion across higher principal components.

### Cumulative Explained Variance
Comparative analysis demonstrates that variance-filtered data reach equivalent variance thresholds using fewer components, indicating improved dimensional efficiency.

### PCA Geometry
PCA scatter plots (PC1 vs PC2) show that global sample-space geometry is largely preserved after filtering, with subtle tightening but no artificial separation introduced by preprocessing.

### Metadata Projection
When sample metadata are projected onto PCA space, major components do not trivially separate conditions. However, non-random biological structure is observable, consistent with PCA capturing real but unsupervised variation.

Representative figures included in this repository:
- `pca_pc1_pc2_by_condition.png`
- `cumulative_variance_comparison.png`
- `filtered/scree_plot.png`

---

## Interpretation Notes

- PCA loadings do **not** represent differential expression.
- No biomarkers or predictive claims are made.
- All conclusions are **methodological**, not biological.

The focus is on understanding how preprocessing decisions shape exploratory multivariate analysis.

---

## Scope

This repository is intended for:
- methodological evaluation,
- preprocessing strategy assessment,
- exploratory PCA behavior analysis in high-dimensional data.

It is **not intended** for:
- differential expression analysis,
- supervised learning or clustering,
- biological interpretation of gene sets,
- multi-omic integration.

---

## Implementation Notes

This repository focuses on **analytical results and methodological reasoning**.

The implementation code used to generate these outputs is maintained separately and is **not distributed** as part of this repository.

This design reflects common industry practice, where analytical approaches are demonstrated through results and documented decision-making, while implementation details are adapted to specific data, infrastructure, and regulatory contexts.

**Internal project ID:** 1000

---

## License

This repository is released under the MIT License.  
The license applies only to the material distributed here (documentation and figures).