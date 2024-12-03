# scRNAseq-Alzheimers-Microglia

A computational analysis of publicly available scRNA-seq data to explore microglial differences in Alzheimer’s Disease and non-demented individuals.

## Project Overview

This project investigates the transcriptomes of microglial cells in post-mortem brain samples from individuals with and without Alzheimer’s Disease. Using computational tools, I aim to identify patterns of gene expression differences.

## Goals

1. Identify patterns of gene expression differences between microglial cells in Alzheimer’s Disease and non-Alzheimer’s individuals.
2. Differentiate microglial transcriptomes based on disease status using scRNA-seq data.

## Research Questions

- Can we differentiate microglial transcriptomes in patients with and without Alzheimer’s Disease using scRNA-seq data?
- Are there consistent gene expression patterns or mutations associated with Alzheimer’s Disease?

## Dataset

This project utilizes publicly available scRNA-seq data:

- **Source:** [Human Cell Atlas Project](https://explore.data.humancellatlas.org/projects/b51f49b4-0d2e-4cbd-bbd5-04cd171fc2fa)
- **Dataset Description:** Transcriptomes of microglial cells from post-mortem cortical brain specimens of non-demented elderly and Alzheimer’s Disease donors.
- **Anatomical Region:** Superior parietal cortex
- **Cell Count:** ~65.8k
- **Donor Count:** 27

## Methods and Tools

### Workflow
1. **Data Loading:** Utilize the Loompy library to process loom file format and convert it to CSV for analysis.
2. **Data Preprocessing:** Filter and normalize data to remove low-quality cells and genes.
3. **Dimensionality Reduction:** Use PCA, t-SNE, or UMAP for visualization and clustering.
4. **Gene Expression Analysis:** Identify differentially expressed genes and explore biological pathways associated with Alzheimer’s pathology.
5. **Results Interpretation:** Summarize findings with labeled figures and discuss biological implications.

### Tools and Libraries
- **Loompy:** For loading and processing loom files.
- **scprep:** For data preprocessing and normalization.
- **Python Libraries:** `pandas`, `matplotlib`, `seaborn`, and `scikit-learn` for analysis and visualization.


