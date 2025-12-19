# multimodal-breast-cancer-fusion
Biologically structured multimodal framework integrating MRI, histopathology, and multi-omics for breast cancer modeling (TCGA-BRCA). Accepted at AIPR 2025; to appear in Springer LNCS. Code and pretrained components will be released following publication.

# Multimodal Fusion of Imaging and Multi-Omics Data for Enhanced Breast Cancer Detection

## Overview

This repository accompanies the research work titled:

**Multimodal Fusion of Imaging and Multi-Omics Data for Enhanced Breast Cancer Detection**

The study was accepted for **oral presentation at the Applied Imagery Pattern Recognition (AIPR) 2025 Conference** and is scheduled to appear in the **Springer Lecture Notes in Computer Science (LNCS)** series.

This work presents a biologically grounded multimodal learning framework that integrates medical imaging, histopathology, and molecular data to model how structural, cellular, and molecular processes jointly shape breast cancer phenotypes.

---

## Research Motivation

Modern biomedical datasets provide rich but heterogeneous views of disease biology. However, most multimodal models treat modalities as independent feature sources and focus primarily on predictive accuracy, often sacrificing interpretability and biological consistency.

The goal of this work is to develop a multimodal framework that:

- Preserves biological structure across modalities  
- Learns interpretable intermediate representations  
- Enables mechanistic understanding of imaging–omics relationships  
- Remains computationally tractable for large-scale multimodal fusion  

---

## Data Modalities

The framework was developed and evaluated using matched patient data from the **TCGA-BRCA** cohort, integrating:

- Dynamic Contrast-Enhanced MRI (DCE-MRI)
- Dual-resolution histopathology whole-slide images (20× and 40×)
- Multi-omics profiles:
  - RNA sequencing
  - Copy number variation (CNV)
  - DNA methylation
  - microRNA expression
  - RPPA proteomics

All modalities correspond to the same patients but are not spatially co-registered, reflecting realistic clinical and research constraints.

---

## Methodological Overview

The proposed framework follows a biologically structured, multi-stage design:

### 1. Modality-Specific Representation Learning
Each modality is first encoded into compact latent representations using domain-appropriate neural encoders and dimensionality reduction, preserving key biological variation while reducing noise.

### 2. Prototype-Level Biological Abstraction
Latent representations are clustered to learn prototype-level biological concepts (e.g., tumor core morphology, DNA repair deficiency, immune activation). Each prototype is associated with biologically meaningful labels derived from imaging annotations or pathway enrichment analyses.

### 3. Graph-Structured Biological Organization
Prototype representations are organized using graph neural networks:

- A graph neural network (GNN) captures spatial and morphological relationships among imaging prototypes.
- A graph attention network (GAT) captures regulatory and pathway-level dependencies among molecular prototypes.

This stage produces coherent, biologically organized modality graphs that replace thousands of isolated features.

### 4. Multimodal Fusion via Transformer Architecture
Graph-encoded prototype tokens are aligned and fused using a Transformer architecture optimized with FlashAttention. The model employs:

- Intra-modality self-attention to refine modality-specific structure  
- Cross-modality attention to learn mechanistic imaging–omics interactions  

### 5. Interpretability and Biological Attribution
Model decisions are interpreted using prototype-level SHAP analysis combined with cross-attention weights, enabling explicit phenotype–genotype correspondences to be recovered and traced back to biological sources.

---

## Key Results

The proposed framework achieved strong predictive and calibration performance on breast cancer subtype classification, while maintaining biological interpretability:

- Area Under ROC Curve (AUC): 0.92  
- Classification Accuracy: 93.2%  
- Expected Calibration Error (ECE): approximately 0.02  

Ablation studies demonstrated that graph-based organization, prototype learning, and cross-modal attention each contribute significantly to performance and stability.

---

## Repository Status

This repository is currently provided for **documentation and transparency purposes**.

To comply with publication policies and ensure a clean, well-documented release, the following are **not yet included**:

- Full training scripts  
- Dataset preprocessing pipelines  
- End-to-end reproduction code  

These components will be released in a subsequent update following final LNCS publication.

---

## Planned Release

Following publication, this repository will be updated to include:

- Full model implementation  
- Configuration files for reproducibility  
- Pretrained model weights (where permissible)  
- Detailed usage instructions  

---

## Citation

If you use or reference this work, please cite the associated LNCS paper.  
A citation file (`CITATION.cff`) will be provided upon publication.

---

## Author

**Dattatreya Kantha**  
George Washington University  
Medical Imaging and Image Analysis Laboratory
