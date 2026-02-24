
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17773084.svg)](https://doi.org/10.5281/zenodo.17773084)


QF-LOG: Quantum Forensic Dataset for QKD Networks

Author
Madhab Chandra Das
Sam Houston State University
ORCID: https://orcid.org/0000-0003-2724-4315

Overview
QF-LOG is a physics-informed dataset for attack detection and forensic analysis in Quantum Key Distribution (QKD) networks.
It contains labeled QKD operational log records that can be used for machine learning, benchmarking, and forensic rule testing.

Dataset files
full_qkd_dataset_realistic_50000.csv
This is the main dataset file. It contains 50,000 records.

qkd_timeseries_lstm_v2.csv
This is a time-series formatted version for sequence models such as LSTM and 1D-CNN.
Use this file only if you need sequential input.

Classes
The dataset contains four balanced classes.
Each class has 12,500 records.

Class names
normal
partial_intercept_resend
detector_blinding
fiber_tap

Features in the main CSV
QBER
photon_count
latency_ms
abort_flag

Important notes
1) The dataset is synthetic but physics-informed.
2) Feature ranges overlap across classes on purpose. This avoids an unrealistic “too easy” dataset.
3) latency_ms represents controller or system processing and buffering delay. It is not optical propagation delay in fiber.

Reproducibility policy
To reproduce results from the associated paper, use the released dataset files as-is.
Do not regenerate, shuffle, or modify the released CSV when you compare with published results.
Dataset generation scripts can be used for transparency and for future extensions, but the released CSV is the reference file for benchmarking.

Quick start
Python example to load the dataset.

import pandas as pd
df = pd.read_csv("full_qkd_dataset_realistic_50000.csv")
print(df.head())

Suggested scripts to upload to IEEE DataPort
generate_qkd_dataset_realistic_50000.py
load_qkd_logs_numeric.py
train_rf_realistic.py
train_xgb_realistic.py
rf_kfold_realistic.py
xgb_kfold_realistic.py
plot_pca_qkd.py
plot_rf_feature_importance.py
extract_rules_qkd.py
rule_based_detector.py

Links
Zenodo record
https://zenodo.org/records/17773084

GitHub repository
https://github.com/MadhabCD/QKD-Forensic-Dataset

Citation
Please cite the dataset using the Zenodo DOI.
Use the DOI shown on the Zenodo page for the official citation text.
