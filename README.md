# Cell-Type-Specific Differential Gene Expression Analysis of scRNA-seq Data in
# Alzheimer's vs. Non-Alzheimer's Patient Entorhinal Cells

A computational analysis of publicly available scRNA-seq data to explore differential expression in Alzheimer's Disease and non-Alzheimer’s Disease individuals Entorhinal cells. 

## Objective

Alzheimer’s disease (AD) is the most prevalent form of dementia in the elderly, affecting more than 6 million Americans today. This progressive disorder slowly destroys memory and thinking skills, and there is currently no cure. Insights into differential gene expression can inform the development of new therapies that may help stop progression or even discover a cure.

The entorhinal cortex is one of the first regions of the brain affected by AD and is critical for memory and navigation. Researchers have documented volume reduction and neural loss in this area, but the underlying molecular mechanisms are still poorly understood. Past research has sought to investigate this with differential gene expression; however, bulk RNA-seq analyses have obscured the unique contributions of different cell types.

This project uses single-cell RNA sequencing data to investigate cell-type-specific differences in gene expression between AD patients and control patients in the entorhinal cortex.

## Data

The dataset used for this analysis was obtained from the **Human Cell Atlas**, consisting of a cell count matrix of 13,214 cells collected from 6 AD patients and 6 age- and sex-matched control patients. The dataset also includes an annotations file with cell type and disease classifications for each cell within the matrix.

## Data Preprocessing

1. **Outlier Filtering**:
   - Thresholds for library size were applied.
   - Low-expression filtering was performed.

2. **Normalization and Gene Count Transformation**:
   - A square root transformation was applied to stabilize variance.

## Dimensionality Reduction and Clustering

1. **Principal Component Analysis (PCA)**:
   - PCA was performed for dimensionality reduction. Given the relatively small size of some cell type-specific groups and their linear separability, PCA was chosen over UMAP and t-SNE.

2. **Spectral Clustering**:
   - Spectral clustering was applied to identify clusters in the dataset. This method was selected because it is effective at separating clusters of varying shapes and sizes.
   - Silhouette scores were used to evaluate cluster separation, and an optimal number of 5 clusters was identified.

3. **Clustering Results**:
   - Clear clustering was observed among cell types such as **oligodendrocytes (Oligo)** and **astrocytes (Astro)**, suggesting notable differences in gene expression between AD and control (CT) groups.
   - Other cell types, such as **endothelial cells** and **microglia**, exhibited less distinct separations.

   
<img width="637" alt="Screenshot 2025-03-07 at 3 03 27 PM" src="https://github.com/user-attachments/assets/77c6a0d2-c93d-4d27-b835-23c89b1d979d" />


## Differential Expression Analysis

1. **Directional t-test**:
   - A directional t-test was used to identify upregulated and downregulated genes within each cell type.
   - The analysis was conducted using the `scprep.stats.differential_expression` function, setting the direction variable to “up” and selecting the AD patient cells in each cell type subset.

2. **Significant Findings**:
   - Both upregulated and downregulated genes were identified across all cell types.
   - **Oligodendrocyte (Oligo)** and **astrocyte (Astro)** cell types showed the most significant changes in gene expression.

3. **Top Genes Identified**:
   - **Astrocytes**:
     - **NEAT1**: The most upregulated gene. NEAT1 is a long non-coding RNA that regulates cellular stress responses and may indicate activation in response to neuroinflammation.
     - **NRXN1**: The most downregulated gene. Deletion of NRXN1 from astrocytes impairs synapse function and may be linked to synaptic loss in AD.
   - **Oligodendrocytes**:
     - **LINC00486**: The most upregulated gene. LINC00486 has been linked to upregulation in both AD and Parkinson's disease in previous studies. It also participates in protein aggregation through epigenetic regulation, which may play a role in AD pathogenesis, particularly through protein aggregation.
     - **IL1RAPL1**: The most downregulated gene. IL1RAPL1 has been associated with the maturation and survival of differentiating oligodendrocytes. Its downregulation in AD may indicate an underlying mechanism contributing to the decline in mature oligodendrocytes, which are responsible for producing myelin essential for supporting the entorhinal cortex.

<img width="745" alt="Screenshot 2025-03-07 at 3 03 03 PM" src="https://github.com/user-attachments/assets/f80e0feb-2a3c-47a6-afbd-73b7af26d2bb" />

       
## Conclusion

- The findings support the presence of differential gene expression between AD patients and control patients, with significant changes observed in **oligodendrocytes** and **astrocytes**.
- The results suggest that these cell types may be most significantly affected by AD.
- Future research should aim to validate these findings with larger datasets and investigate the potential impact of cell-type-specific genes in disease progression.

## Future Directions

1. **Dataset Expansion**: Our current study includes only 12 individuals, and interindividual variability may have influenced the results. Expanding the dataset size could strengthen the findings.

2. **Gene Knockout Studies**: Employing gene knockouts on the identified cell-type-specific genes in healthy non-human test subjects (for ethical reasons) could help determine if this induces Alzheimer’s-like cognitive decline.

3. **Mechanistic Understanding**: Further investigation into the molecular mechanisms behind brain volume reduction and neural loss in AD patients could lead to better therapeutic targets and understanding of the disease.

   

---
