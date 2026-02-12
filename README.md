# Gene Expression Feature-Reduced PCA

#### Methodological evaluation of variance-based feature filtering in high-dimensional RNA-seq data

---

## Overview

This repository presents a **method-focused evaluation** of how variance-based gene filtering influences the behavior and interpretability of Principal Component Analysis (PCA) in high-dimensional RNA-seq datasets.

The objective is **not biological discovery**, but to examine how upstream preprocessing decisions reshape:

- variance concentration across principal components,
- cumulative explained variance efficiency,
- PCA geometry in sample space,
- and gene-level contributions to principal axes.

The project reflects analytical reasoning commonly required in translational research and industry environments, where preprocessing choices directly condition downstream interpretation.

---

## What This Repository Demonstrates

This repository demonstrates:

- how preprocessing decisions alter unsupervised multivariate analyses,
- how to design controlled methodological comparisons,
- how to reason about PCA behavior beyond default or black-box usage.

The emphasis is on **analytical judgment, experimental control, and interpretability**, rather than on optimized models or task-specific performance.

---

## Study Design

Two controlled PCA scenarios are evaluated:

- **Scenario A:** PCA without feature filtering  
- **Scenario B:** PCA after variance-based gene filtering  

All analyses isolate the effect of feature reduction on PCA behavior.  
No supervised labels, prediction targets, or optimization criteria are involved.

---

## Data

- **Data type:** RNA-seq gene expression counts  
- **Source:** Public Gene Expression Omnibus (GEO) dataset  
- **Dataset:** Tumor-Educated Platelet (TEP) RNA-seq  

The dataset includes a large number of samples and heterogeneous conditions, making it suitable for stress-testing PCA behavior under feature reduction.

Raw data are publicly available from GEO and are not redistributed here.

---

## Analytical Flow (Conceptual)

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
Scree plots show that variance-based filtering concentrates variance into earlier components, reducing dispersion across higher PCs.

### Cumulative Explained Variance
Filtered data reach equivalent variance thresholds using fewer components, indicating improved dimensional efficiency.

### PCA Geometry
PC1–PC2 projections show preservation of global sample-space geometry after filtering, with subtle tightening but no artificial separation.

### Metadata Projection
Overlaying sample metadata reveals non-random biological structure without trivial condition separation, consistent with unsupervised variance capture.

Representative figures included:
- `pca_pc1_pc2_by_condition.png`
- `cumulative_variance_comparison.png`
- `filtered/scree_plot.png`

---

## Interpretation Boundaries

- PCA loadings are **not** differential expression.
- No biomarkers or predictive claims are made.
- All conclusions are **methodological**, not biological.

---

## Scope

**Intended for:**
- methodological evaluation,
- preprocessing strategy assessment,
- exploratory PCA behavior analysis.

**Out of scope:**
- differential expression analysis,
- supervised learning or clustering,
- biological interpretation of gene sets,
- multi-omic integration.

---

## Implementation and Method Exposure

This repository documents **analytical outcomes and methodological framing**.

Detailed implementation logic, parameterization heuristics, and upstream decision rules are intentionally not distributed. This mirrors applied research and industry practice, where methodological insight resides in analytical reasoning rather than in executable scripts alone.

Access to deeper methodological reasoning or adaptation to new datasets requires direct collaboration.

---

## License

This repository is released under the MIT License.  
The license applies only to the material distributed here (documentation and figures).