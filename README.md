# Replication of "An Integrative Model of Cellular States, Plasticity, and Genetics for Glioblastoma" (Neftel et al., 2019)

## 📖 Introduction

This project aims to replicate the core analysis pipeline and key findings of the landmark study **"An Integrative Model of Cellular States, Plasticity, and Genetics for Glioblastoma"** by Neftel et al., published in *Cell* (2019).

The study revealed that malignant cells in Glioblastoma (GBM) exist in four dominant cellular states: **NPC-like, OPC-like, AC-like, and MES-like**. It further explored the plasticity between these states and their genetic drivers.

By processing raw single-cell RNA-seq data, this project reproduces the complete workflow, including data preprocessing, non-malignant cell filtering, CNV inference, and the visualization of cellular states.

## 🚀 Key Replications

This project successfully reproduces the following key figures and analyses from the original paper:

1.  **Data Loading & Preprocessing**:
    * Loading Smart-seq2 GBM scRNA-seq expression matrices (TPM) and metadata.
    * Quality Control (QC) and filtering of generally highly expressed genes.
2.  **Non-Malignant Cell Identification (Replicating Figure 1B)**:
    * Scoring cells based on marker genes for Macrophages, Oligodendrocytes, and T cells.
    * Visualizing cell classification using t-SNE.
3.  **CNV Inference & Malignant Cell Classification (Replicating Figure 1A & 1C)**:
    * Inferring chromosomal Copy Number Variations (CNV) using `infercnvpy`.
    * Distinguishing malignant from non-malignant cells based on CNV signal intensity and correlation.
    * Generating **Chromosome Heatmaps** to visualize tumor-specific CNV patterns.
4.  **Cellular State Meta-Modules (Replicating Figure 2B & 2C)**:
    * Identifying co-expressed gene modules via Hierarchical Clustering.
    * Defining the four core cellular states (Meta-modules) based on Jaccard similarity.
5.  **2D Cellular State Mapping (Replicating Figure 3F)**:
    * Scoring individual cells using the defined meta-module gene sets.
    * Mapping all malignant cells onto a 2D state space, successfully reproducing the iconic **"Butterfly" plot**, illustrating the continuity and plasticity of GBM cell states.

## 📂 File Structure

```text
.
├── raw_data/                       # Directory for raw data files
│   ├── GSM3828672_Smartseq2_GBM_IDHwt_processed_TPM.tsv
│   └── GSE131928_single_cells_tumor_name_and_adult_or_peidatric.xlsx
├── gbm_sc_analysis.ipynb           # Core replication code (Jupyter Notebook)
├── environment.yml                 # Conda environment configuration
└── README.md                       # Project documentation
```

## 🛠️ Installation

This project relies on `scanpy`, `infercnvpy`, `scikit-learn`, and `scipy`. We recommend using **Conda** to manage the environment.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Da-che/replication_neftel_2019.git
    cd replication_neftel_2019
    ```

2.  **Create and activate the environment:**
    ```bash
    # Create environment from config file
    conda env create -f environment.yml
    
    # Activate environment (Please check the 'name' in environment.yml if it differs)
    conda activate gbm_sc
    ```

## 📊 Results

### 1. Cell Classification & t-SNE Visualization
Non-malignant cells were identified using marker gene scoring and visualized alongside malignant cells in t-SNE space.

### 2. Chromosome CNV Heatmap
The heatmap displays chromosomal amplification and deletion patterns across different tumor samples, confirming the genetic heterogeneity of malignant cells.

### 3. 2D Cellular State Map (Figure 3F Replication)
This is one of the most significant results of the paper. We successfully mapped malignant cells into the four quadrants (**NPC-like, OPC-like, AC-like, MES-like**), validating the continuous state model of Glioblastoma.

*(Note: Please refer to the Jupyter Notebook for high-resolution interactive charts.)*

## 📚 Reference

* Neftel, C., Laffy, J., Filbin, M. G., Hara, T., Shore, M. E., Rahme, G. J., ``` & Suvà, M. L. (2019). **An integrative model of cellular states, plasticity, and genetics for glioblastoma**. *Cell*, 178(4), 835-849. [Link](https://doi.org/10.1016/j.cell.2019.06.024)

## 📬 Contact

If you have any questions or discussions regarding this replication, please contact the author:

* **Author**: Xuanzhi Chen
* **Email**: xuanzhichen@stu.pku.edu.cn

## 📄 License

This project is licensed under the [MIT License](LICENSE).