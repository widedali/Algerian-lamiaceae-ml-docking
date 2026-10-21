# Algerian Lamiaceae: leaf-image classification and molecular docking

Code and result tables for the manuscript "Deep Learning-Assisted Leaf Classification and
Literature-Informed Phytochemical Hypothesis Generation for Multitarget Bioactive Compound
Discovery in Algerian Lamiaceae" (Computational Biology and Chemistry, CBAC-D-26-04142).

## Data
Leaf images are not redistributed. Download them from the original public sources:
- PlantNet-300K (Garcin et al., 2021)
- MedLeaves (Roopashree and Anitha, 2020)
- Medicinal Leaf Dataset (B R and Rani, 2023)

`result/metadata_cleaned.csv` lists all 23,168 images of the cleaned dataset with their
source, original identification, study class, split (train/val/test), licence, and SHA-256
hash. `datasetpreparation/Algerian_Lamiaceae_Dataset_Preparation_v3.ipynb` builds the
dataset and splits from the original sources (Section 3.1).

## Notebooks and manuscript sections

### Dataset and classification
| Notebook | Manuscript |
|---|---|
| `datasetpreparation/Algerian_Lamiaceae_Dataset_Preparation_v3.ipynb` | Section 3.1, Tables 3–6 |
| `datasetpreparation/Notebook00_Setup_PCA300.ipynb` | Section 3.2 (features, SMOTE, PCA) |
| `classifiers/Notebook01_SVM_LinearSVC.ipynb` … `classifiers/Notebook12_CatBoost.ipynb` | Section 3.3, Table 8 |
| `classifiers/13_Collect_Results.ipynb` | Table 8, Figure 4 |
| `classifiers/17_SMOTE_Scaling_Sensitivity_fast.ipynb` | Section 3.5.2, Figure 7 |
| `efficientnet/14_CNN_EfficientNetB3_PHYTO_v3(1).ipynb` | Section 3.4, Tables 9–10, Figures 5–6 |
| `efficientnet/16_Near_Duplicate_Screening.ipynb` | Section 3.5.1 |
| `efficientnet/15_Cross_Source_Evaluation_v2_fast.ipynb` | Section 3.5.3, Table 11 |

### Molecular docking
Folder: `Molecular Docking Methodology for five Algerian Lamiaceae-Relevant Protein Targets/`

| Subfolder / notebook | Target (PDB) | Manuscript |
|---|---|---|
| `AchE/` | Acetylcholinesterase (1EVE), AutoDock Vina | Sections 4.4, 4.7 |
| `Cox-2/` | Cyclooxygenase-2 (5IKQ), AutoDock Vina | Sections 4.4, 4.7 |
| `Aldose reductase/` | Aldose reductase (2FZD), AutoDock Vina | Sections 4.4, 4.7 |
| `PPAR-α/vina/` | PPAR-α (1K7L), AutoDock Vina | Sections 4.4, 4.7 |
| `ACE/smina/` | Angiotensin-converting enzyme (1O86), Smina (used for screening) | Sections 4.4, 4.7 |
| `ACE/Vina/` | ACE (1O86), AutoDock Vina (failed redocking; comparison only) | Table 16, Table 18 |
| `Cofactor_Sensitivity_AldoseReductase_2FZD_NADP.ipynb` | Aldose reductase with/without NADP+ | Section 4.2 |
| `Cofactor_Sensitivity_COX2_5IKQ_heme.ipynb` | COX-2 with/without Co-protoporphyrin IX | Section 4.2 |

In each target folder, `Redocking_Validation_*.ipynb` reproduces the reference-ligand
redocking (Table 16), and the notebooks numbered `1_` to `5_` dock the compounds of one
taxon each (Table 18, Figure 10):
1 = *Lamium amplexicaule*, 2 = *Lavandula angustifolia*, 3/4 = *Lavandula dentata* and
*Lavandula stoechas*, 5 = *Mentha spicata*.

## Result tables (`result/`)
| File | Manuscript |
|---|---|
| `metadata_cleaned.csv` | Image metadata and split assignments (Tables 3–4) |
| `results_classifiers.csv` | Classical classifiers, default and Optuna-tuned (Table 8, Section 3.3) |
| `classification_report_cnn.csv` | EfficientNet-B3 per-class results (Table 10) |
| `near_duplicate_summary.csv` | Near-duplicate screening (Section 3.5.1) |
| `smote_order_all_metrics.csv` | SMOTE/standardisation order sensitivity (Section 3.5.2, Figure 7) |
| `cross_source_pairwise.csv` | Cross-source evaluation, Experiment A (Table 11) |
| `cross_source_heldout_class_source.csv` | Cross-source evaluation, Experiment B (Table 11) |
| `v1_vs_v2_comparison.csv` | Cross-source runs with and without background removal (Section 3.5.3) |

## Main software
Python 3, PyTorch 2.6, timm 1.0.27, scikit-learn 1.6.1, RDKit, AutoDock Vina 1.2.0,
Smina, Open Babel, Meeko, ProLIF 2.2.1.

## Contact
Wided Ali, wided.ali@univ-tebessa.dz
