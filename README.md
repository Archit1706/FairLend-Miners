# FairLend Miners — CS 483 Big Data Mining Final Project

Auditing discriminatory patterns in U.S. mortgage lending using fairness-aware preprocessing and association rule mining.

**Team:** Archit Rathod, Dhwani Chande, Het Nagda  
**Course:** CS 483 Big Data Mining  
**Instructor:** Prof. Abolfazl Asudeh

## Dataset

HMDA 2023 Snapshot National Loan-Level Dataset (CFPB), filtered to Chicago Metropolitan Division (code 16984). 103,481 cleaned records with 20 columns.

Source: https://ffiec.cfpb.gov/data-publication/snapshot-national-loan-level-dataset/2023

## Repository Structure

```
├── code/
│   ├── Data_Pipeline.ipynb      # Data cleaning, standard & fair binning
│   ├── FPGrowth.ipynb           # FP-Growth association rule mining
│   └── Clustering_DI_Audit.ipynb # K-Means clustering & DIR audit
├── data/
│   ├── hmda_chicago_2023_cleaned.parquet       # Cleaned numeric data (for clustering)
│   ├── hmda_chicago_2023_standard_binned.parquet # Standard binned (for FP-Growth)
│   └── hmda_chicago_2023_fair_binned.parquet   # Fair binned (for FP-Growth comparison)
├── plots/
│   ├── standard_binning_bias.png
│   ├── binning_comparison.png
│   ├── memberB_analysis.png
│   ├── memberC_k_selection.png
│   └── memberC_dir_audit.png
├── LICENSE
└── README.md
```

## How to Run

All notebooks run on Google Colab with a T4 GPU. Run them in order: A then B then C. Each notebook mounts Google Drive and reads from the previous notebook's output.

## Key Results

- Standard binning introduces 9.63% racial bias in income discretization
- FP-Growth finds DTI as the dominant denial predictor (67.2% confidence, 2.81 lift)
- K-Means + DIR audit flags 10 of 45 cluster-group pairs for racial disparate impact

## Reference

Asudeh et al., "Unbiased Binning: Fairness-aware Attribute Representation," arXiv:2509.21785, 2025.
