Functional Transcriptomic Analysis of Human PBMCs
This repository contains a complete, end-to-end single-cell RNA-seq (scRNA-seq) analysis of a 3k human Peripheral Blood Mononuclear Cell (PBMC) dataset from 10x Genomics. The goal is to identify distinct immune cell populations and explore the transcription factor (TF) and pathway activities driving their functional heterogeneity.

## Project Workflow
1. Data Loading & Quality Control (QC)
Load filtered feature-barcode matrix into an AnnData object.

Filter out low-quality cells (genes per cell > 200, mitochondrial reads < 5%).

2. Normalization & Feature Selection
Normalize counts to 1×10⁴ reads per cell and log-transform.

Identify top 2,000 highly variable genes (HVGs).

3. Dimensionality Reduction & Clustering
Run PCA on HVGs.

Build neighborhood graph (20 PCs).

Compute UMAP for 2D visualization.

Apply Leiden clustering to identify cell groups.

4. Cell-Type Annotation
Annotate clusters via canonical markers: CD8A (T cells), MS4A1 (B cells), NCAM1 (NK cells), CD14 (monocytes).

5. Functional Analysis with Decoupler
Infer TF activities using DoRothEA regulons.

Infer pathway activities using PROGENy footprints.

Perform t-tests to identify cluster-specific TFs and pathways.

## Key Findings
Populations Identified: Classical monocytes, non-classical monocytes, B cells, NK cells, and CD8+ T cells.

Functional Heterogeneity: E2F1 activity marks proliferative subpopulations; MAPK pathway highlights immune activation/stress states.

Regulatory Drivers: STAT1 drives interferon response in monocytes; HIF1A regulates metabolic stress in NK cells.

## Technologies Used
Core Analysis: Scanpy, Decoupler

Data Manipulation: pandas, AnnData

Visualization: Matplotlib, Seaborn

Environment: Python 3, Jupyter Notebook

## Reproduction
Clone the repo:

git clone https://github.com/Makayacine/Transcriptomics.git
cd Transcriptomics

Download data:

Obtain the "3k PBMCs from a Healthy Donor" dataset from 10x Genomics.

Place filtered_feature_bc_matrix.h5 in the data/ directory.

Install dependencies:

pip install -r requirements.txt

Run the analysis:

jupyter notebook Transcriptomics.ipynb
