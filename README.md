

# Transcriptomics Analysis Repository

This repository contains a collection of Jupyter notebooks and projects focused on single-cell transcriptomics (scRNA-seq) analysis. The projects range from foundational workflows using standard datasets to more advanced analyses of gene regulatory networks.

## Repository Structure

The repository is organized into a project-based layout, where each folder represents a distinct, self-contained analysis:

```
Transcriptomics/
│
├── PBMC scRNA-seq Regulatory Activity Atlas/
│   ├── PBMC scRNA-seq Regulatory Activity Atlas.ipynb
│   ├── Single-Cell RNA-Seq Project README.md
│   └── requirements.txt
│
├── PRJNA413956/
│   ├── PRJNA413956.ipynb
│   ├── Dockerfile
│   ├── README.md
│   └── quants_manifest.csv
│
└── pbmc3k/
    ├── pbmc3k.ipynb
    └── README.md
```

## Project Details

### 1\. `pbmc3k`

  * **Notebook:** `pbmc3k.ipynb`
  * **Purpose:** This notebook serves as a foundational walkthrough of a standard single-cell RNA-seq analysis pipeline using the `scanpy` library.
  * **Dataset:** It uses the classic "pbmc3k" dataset from 10x Genomics, which consists of 3,000 Peripheral Blood Mononuclear Cells (PBMCs).
  * **Key Steps:**
      * Loading the dataset.
      * Quality control (filtering cells and genes).
      * Normalization and log-transformation.
      * Identification of highly variable genes.
      * Dimensionality reduction (PCA and UMAP).
      * Cell clustering (Leiden algorithm).
      * Finding marker genes for cluster identification.
      * Annotation of cell types (e.g., Monocytes, B cells, T cells).

### 2\. `PRJNA413956`

  * **Notebook:** `PRJNA413956.ipynb`
  * **Purpose:** This project applies a complete scRNA-seq workflow to a specific public dataset, identified by its NCBI BioProject ID `PRJNA413956`.
  * **Analysis:** Similar to the `pbmc3k` notebook, this analysis moves from raw count data (or a quantifications manifest) to a fully annotated cell atlas.
  * **Key Files:**
      * `quants_manifest.csv`: A manifest file, likely listing the paths to quantification data (e.g., from `salmon` or `kallisto`).
      * `Dockerfile`: Defines a reproducible computing environment, allowing this analysis to be run consistently anywhere.

### 3\. `PBMC scRNA-seq Regulatory Activity Atlas`

  * **Notebook:** `PBMC scRNA-seq Regulatory Activity Atlas.ipynb`
  * **Purpose:** This is a more advanced analysis project that moves beyond standard gene expression clustering.
  * **Analysis:** The goal is to create an "atlas" of **gene regulatory activity**. This typically involves:
      * Starting with a pre-processed and annotated PBMC scRNA-seq dataset.
      * Using computational methods (like `pyscenic` or similar tools) to infer **Gene Regulatory Networks (GRNs)**.
      * Calculating the activity of specific **Transcription Factors (TFs)** within each cell.
      * Visualizing this "regulon" activity to understand which regulatory programs are active in which cell types.

## Core Technologies

The analyses in this repository primarily rely on the Python scientific computing stack, especially:

  * **`scanpy`**: The core library for single-cell analysis.
  * **`anndata`**: The data structure used by `scanpy` to store expression matrices and annotations.
  * **`pandas` & `numpy`**: For data manipulation and numerical computation.
  * **`matplotlib` & `seaborn`**: For plotting and visualization.
  * **`Jupyter Notebooks` / `Jupyter Lab`**: As the interactive development environment.
  * **`Docker`**: For creating reproducible analysis environments (seen in `PRJNA413956`).
