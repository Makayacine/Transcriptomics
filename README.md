# Transcriptomics Project Repository

This repository showcases a collection of end-to-end bioinformatics projects focused on transcriptomics, ranging from single-cell to bulk RNA-seq analysis. Each project is self-contained and demonstrates a complete workflow, from raw data processing to functional interpretation and integrative analysis.

-----

## Projects Overview

This repository contains the following analyses:

1.  **Integrative Single-Cell Analysis of the PBMC3k Dataset (`pbmc3k/`)**
      * A multi-modal analysis connecting gene expression with the intrinsic sequence composition of transcripts in a 3k PBMC dataset.
2.  **Functional Transcriptomic Analysis of Human PBMCs (`PBMC scRNA-seq Regulatory Activity Atlas/`)**
      * A focused workflow to identify immune cell populations and explore the transcription factor and pathway activities driving their functional heterogeneity.
3.  **End-to-End Bulk RNA-Seq Pipeline for CRC (`PRJNA413956/`)**
      * A complete pipeline to process raw RNA-seq data from a colorectal cancer (CRC) project, quantify expression, and perform downstream analysis using PySpark.

-----

### 1\. Integrative Single-Cell Analysis of the PBMC3k Dataset

🧬 **Project Goal:**
This project performs a comprehensive, end-to-end analysis of the public 3k PBMC dataset from 10x Genomics. It goes beyond a standard single-cell workflow by connecting **gene expression dynamics** with the **intrinsic sequence composition** of the transcripts themselves.

**Workflow:**

  * **Gene Expression & Regulation:** Uses **Scanpy** and **Decoupler** to identify immune cell populations, find marker genes, and infer the activity of transcription factors and pathways.
  * **Sequence Composition Analysis:** Uses **Biotite** and **scikit-learn** to vectorize transcripts based on their k-mer frequencies and uses dimensionality reduction to uncover structural patterns.

**Key Findings:**
The analysis identified several immune subpopulations and their regulatory states. A key observation was that genes with “typical” 4-mer compositions generally showed higher expression, whereas those with more unusual k-mer profiles tended to have lower expression, indicating that sequence composition may influence transcript detectability.

**To run this analysis:**
Navigate to the `pbmc3k/` directory and follow the instructions in its dedicated `README.md`.

### 2\. Functional Transcriptomic Analysis of Human PBMCs

🔬 **Project Goal:**
This repository contains a complete, end-to-end single-cell RNA-seq (scRNA-seq) analysis of a 3k human Peripheral Blood Mononuclear Cell (PBMC) dataset. The goal is to identify distinct immune cell populations and explore the transcription factor (TF) and pathway activities driving their functional heterogeneity.

**Workflow:**

  * **Data Processing:** QC, normalization, feature selection, and dimensionality reduction using **Scanpy**.
  * **Cell-Type Annotation:** Clusters are annotated via canonical markers (CD8A, MS4A1, NCAM1, CD14).
  * **Functional Analysis:** TF and pathway activities are inferred using **Decoupler**.

**Key Findings:**

  * **Populations Identified:** Classical monocytes, non-classical monocytes, B cells, NK cells, and CD8+ T cells.
  * **Functional Heterogeneity:** E2F1 activity marks proliferative subpopulations; the MAPK pathway highlights immune activation/stress states.

**To run this analysis:**
Navigate to the `PBMC scRNA-seq Regulatory Activity Atlas/` directory and follow the instructions in its `README.md`.

### 3\. End-to-End Bulk RNA-Seq Pipeline for CRC

🦀 **Project Goal:**
This project contains a complete, reproducible pipeline to process raw RNA-seq data from a colorectal cancer (CRC) project, quantify transcript expression, and perform downstream exploratory analysis using PySpark.

**Workflow:**

  * **Command-Line Data Processing:** Raw sequencing reads are downloaded, cleaned, and quantified using **SRA-Tools**, **Trim Galore**, and **Salmon**.
  * **Downstream Analysis (Jupyter Notebook):** Quantification results are loaded into a **PySpark** DataFrame, joined with sequence-level features, and analyzed to compare expression patterns between tumor and normal samples.

**Key Outputs:**
The final notebook contains a PCA plot for quality control and a comparative plot of gene expression vs. GC content for tumor and normal samples.

**To run this analysis:**
Navigate to the `PRJNA413956/` directory and follow the instructions in its `README.md`.

-----

## Getting Started

To explore these projects, first clone the repository to your local machine:

```bash
git clone https://github.com/Makayacine/Transcriptomics.git
cd Transcriptomics
```

Each project is located in its own directory and contains a specific `README.md` with detailed instructions for setup and execution. Please refer to the individual project directories for more information.
