# Integrative Single-Cell Analysis of the PBMC3k Dataset

## 🧬 Project Overview

This repository contains a comprehensive, end-to-end bioinformatics analysis of the public 3k Peripheral Blood Mononuclear Cells (PBMC) dataset from 10x Genomics. The project goes beyond a standard single-cell workflow by performing a multi-modal, integrative analysis that connects **gene expression dynamics** with the **intrinsic sequence composition** of the transcripts themselves.

The analysis is performed entirely within the `pbmc3k.ipynb` Jupyter Notebook and is divided into two main investigations:

1.  **Gene Expression & Regulation:** Using **Scanpy** and **Decoupler**, this part of the analysis identifies immune cell populations, finds marker genes, and infers the activity of the transcription factors and pathways driving different cell states.
2.  **Sequence Composition Analysis:** Using **Biotite** and **scikit-learn**, this investigation explores the physical properties of the expressed gene sequences, vectorizes them based on their k-mer (nucleotide word) frequencies, and uses dimensionality reduction to uncover hidden structural patterns.

The final step synthesizes these two views to generate novel, data-driven hypotheses about the relationship between a gene's sequence structure and its expression potential in single cells.

---

## ✨ Key Features

* **End-to-End Workflow:** From raw data loading to final integrative plots, all steps are included and annotated.
* **High-Resolution Cell State Annotation:** Moves beyond simple clustering to infer functional regulatory activity using Decoupler.
* **Sequence-Level Analysis:** Implements a robust pipeline for k-mer counting, vectorization, and dimensionality reduction on FASTA sequences.
* **Integrative Hypothesis Generation:** Connects two distinct data modalities (expression and sequence) to uncover a novel correlation between k-mer typicality and gene expression levels.
* **Publication-Quality Visualizations:** Uses Matplotlib and Seaborn to create clear, well-annotated plots to interpret the results.

---

## 🔧 Setup and Installation

To run this analysis, you will need a Python environment with several core bioinformatics libraries installed.

### Dependencies

The main libraries used in this project are:

* `scanpy`
* `decoupler`
* `biotite`
* `scikit-learn`
* `scikit-bio`
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `jupyter`

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Makayacine/Transcriptomics.git
   cd Transcriptomics

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required packages:**
    A `requirements.txt` file is the easiest way to manage this. You can create one with the dependencies listed above and install with:
    ```bash
    pip install -r requirements.txt
    ```
    Alternatively, you can install the key packages manually:
    ```bash
    pip install scanpy decoupler biotite scikit-learn scikit-bio pandas matplotlib seaborn jupyter
    ```

---

## 💾 Data Requirements

You will need to download two main data files to run this notebook:

1.  **Single-Cell Expression Data (`pbmc3k_raw.h5ad`):**
    * This file contains the raw count matrix for the PBMC3k dataset.
    * It can be downloaded directly using Scanpy's built-in datasets.

2.  **Human Reference Transcriptome (`gencode.v32.transcripts.fa` or similar):**
    * This FASTA file contains the nucleotide sequences for all human transcripts.
    * **Source:** Download from the [GENCODE website](https://www.gencodegenes.org/human/). Ensure you download the **"Transcript sequences (FASTA)"** file corresponding to the **GRCh38** genome build (e.g., v32 or newer).
    * After downloading, unzip the file and place it in the same directory as the notebook.

---

## 🚀 How to Run

1.  Ensure you have completed the **Setup and Installation** steps.
2.  Make sure the required **Data** files (`pbmc3k_raw.h5ad` and the reference transcriptome FASTA) are in the project directory.
3.  Launch Jupyter Notebook or JupyterLab:
    ```bash
    jupyter notebook
    ```
4.  Open the `pbmc3k.ipynb` notebook and execute the cells sequentially.

---

## 📈 Key Results

The analysis identified several immune subpopulations along with their regulatory states. We also observed that genes with “typical” 4-mer compositions generally showed higher expression, whereas those with more unusual k-mer profiles tended to have lower expression, indicating that sequence composition may influence transcript detectability.
