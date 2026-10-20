# Algerian Lamiaceae: leaf-image classification and molecular docking

Code for the manuscript "Deep Learning-Assisted Leaf Classification and Literature-Informed
Phytochemical Hypothesis Generation for Multitarget Bioactive Compound Discovery in
Algerian Lamiaceae" (Computational Biology and Chemistry, CBAC-D-26-04142).

## Data
Leaf images are not redistributed. Download them from the original sources:
- PlantNet-300K (Garcin et al., 2021)
- MedLeaves (Roopashree and Anitha, 2020)
- Medicinal Leaf Dataset (B R and Rani, 2023)

`datasetpreparation/Algerian_Lamiaceae_Dataset_Preparation_v3.ipynb` builds the dataset
and train/validation/test splits from these sources (Section 3.1).

## Notebooks and manuscript sections
| Folder / notebook | Manuscript |
|---|---|
| `datasetpreparation/Algerian_Lamiaceae_Dataset_Preparation_v3.ipynb` | Section 3.1, Tables 3–6 |
| `datasetpreparation/Notebook00_Setup_PCA300.ipynb` | Section 3.2 (features, SMOTE, PCA) |
| `classifiers/Notebook01`–`Notebook12` | Section 3.3, Table 8 |
| `classifiers/13_Collect_Results.ipynb` | Table 8, Figure 4 |
| `classifiers/17_SMOTE_Scaling_Sensitivity_fast.ipynb` | Section 3.5.2, Figure 7 |
| `efficientnet/14_CNN_EfficientNetB3_PHYTO_v3.ipynb` | Section 3.4, Tables 9–10, Figures 5–6 |
| `efficientnet/16_Near_Duplicate_Screening.ipynb` | Section 3.5.1 |
| `efficientnet/15_Cross_Source_Evaluation_v2_fast.ipynb` | Section 3.5.3, Table 11 |
| `Molecular Docking …/<target>/Redocking_Validation_*.ipynb` | Section 4.4, Table 16 |
| `Molecular Docking …/<target>/1_ … 5_*.ipynb` (one per taxon) | Section 4.7, Table 18, Figure 10 |
| `Molecular Docking …/ACE/smina/` | ACE screening (Smina) |
| `Molecular Docking …/ACE/Vina/` | ACE Vina scores (comparison only) |
| `Molecular Docking …/Cofactor sensitivity/` | Section 4.2 (cofactor sensitivity) |

## Main software
Python 3, PyTorch 2.6, timm 1.0.27, scikit-learn 1.6.1, RDKit, AutoDock Vina 1.2.0,
Smina, Open Babel, Meeko, ProLIF 2.2.1.

## Contact
Wided Ali, wided.ali@univ-tebessa.dz
