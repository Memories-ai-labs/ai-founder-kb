# AlphaGenome 2: Deciphering how cells read DNA to better understand disease
# URL: https://deepmind.google/blog/alphagenome-2-deciphering-how-cells-read-dna-to-better-understand-disease/
# Date: 2026-11-11
# Source: Google DeepMind

Authors: Adam Gayoso, Natasha Latysheva, Pushmeet Kohli, Žiga Avsec (Google DeepMind)
Published: November 11, 2026

## Overview
AlphaGenome 2 is a conditional DNA sequence model that predicts how DNA variants affect gene regulation in specific human cell types. Unlike the original AlphaGenome (which predicted across broad tissues), AlphaGenome 2 takes a DNA sequence plus a target condition (tissue, cell type, or cell state) and predicts effects for that specific context. Trained on bulk and single-cell data from human and mouse, including 107M+ single-cell profiles.

## Key Findings

**Variant detection**: Identifies nearly 2x more variants that change gene expression vs. prior state-of-the-art.

**Cell-type precision**: On TenK10K immune-cell dataset:
- Found causal variants in 30% of cases vs. 16% for prior models
- Directional gene-effect calls correct 43% of the time vs. 23%

**Disease case study**: Reproduced the finding that a specific variant boosts ETS2 gene in gut macrophages in inflammatory bowel disease, isolating the effect to the relevant cell type.

**Cross-modality imputation**: Can predict unmeasured properties (e.g., chromatin accessibility) from one measurement (e.g., single-cell gene activity).

**Generalization without retraining**: A small single-cell RNA-seq sample (few dozen cells) lets it model unseen cell states. COVID-19 vaccine example: distinguished activated vs. resting T cells and showed a severe-COVID-linked variant has a stronger effect in the activated state.

**Precomputed GWAS resources**: Predictions for trait-associated variants across hundreds of cell/tissue conditions provided to researchers.

## Availability
- Non-commercial research: available via API
- Commercial use: private preview
- Not validated for clinical or diagnostic use

## Significance
Connects human genetics with single-cell biology. Helps researchers find disease-relevant variants that broad-tissue models miss, map enhancer-gene links in primary human cells, and move from GWAS associations toward specific causal mechanisms. Major advance for genomic medicine research.
