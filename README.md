[![Data License: CC BY 4.0](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-blue.svg)](LICENSE_CC-BY-4.0)
[![Code License: MIT](https://img.shields.io/badge/Code%20License-MIT-green.svg)](LICENSE)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17773084.svg)](https://doi.org/10.5281/zenodo.17773084)

License
The dataset files (CSV and any dataset ZIP files) are licensed under CC-BY-4.0.
The code and scripts in this repository are licensed under the MIT License.

QF-LOG: Quantum Forensic Dataset for QKD Networks

Author
Madhab Chandra Das
Sam Houston State University
ORCID: https://orcid.org/0000-0003-2724-4315

Overview
QF-LOG is a physics-informed dataset for attack detection and forensic analysis in Quantum Key Distribution (QKD) networks.
It contains labeled QKD operational log records that can be used for machine learning, benchmarking, and forensic rule testing.

Dataset files
full_qkd_dataset_realistic_50000_v2.csv
This is the main dataset file. It contains 50,000 records.

Classes
The dataset contains four balanced classes.
Each class has 12,500 records.

Class names
normal
partial_intercept_resend
detector_blind
fiber_tap

Features in the main CSV
qber
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
df = pd.read_csv("full_qkd_dataset_realistic_50000_v2.csv")
print(df.head())

Suggested scripts to upload to IEEE DataPort
generate_qkd_dataset_realistic_50000_v2.py
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



## Generator-B Robustness Validation Extension

### Motivation
The original QF-LOG dataset was generated using a single physics-informed synthetic generator (Generator-A). Although the initial machine learning models achieved high internal validation accuracy, robustness under unseen operational conditions remained uncertain.

To address this limitation, Generator-B was developed as a domain-shifted QKD operational simulator for cross-generator forensic robustness evaluation.

### Generator-B Features
Generator-B introduces multiple operational variations and domain-shift factors, including:

- unseen hardware profiles
- detector calibration drift
- varying fiber attenuation and loss
- temporal operational noise
- environmental instability
- shifted photon-count distributions
- shifted latency distributions
- noisy QBER behavior
- overlapping operational class boundaries
- optional calibration_drift_attack scenario
Generator-B optionally supports an additional calibration_drift_attack class for future robustness research.
### Generator-B Variants

#### Generator-B v1
Extreme domain-shift scenario designed to stress-test forensic model robustness under severe operational drift.

#### Generator-B v2
Calibrated moderate domain-shift scenario designed to simulate more realistic deployment conditions while preserving operational uncertainty and class overlap.

### Cross-Generator Robustness Evaluation

Training dataset:
- Generator-A

Testing datasets:
- Generator-B v1
- Generator-B v2

Models evaluated:
- Random Forest
- XGBoost

Cross-generator evaluation showed substantial degradation compared with internal validation results, demonstrating that single-generator evaluation may overestimate forensic model robustness.

| Test Dataset | RF Accuracy | XGBoost Accuracy |
|---|---|---|
| Generator-B v1 | 0.2591 | 0.2451 |
| Generator-B v2 | 0.3358 | 0.2856 |

### Main Findings

- Internal validation alone overestimated robustness.
- Latency distribution shift was the strongest degradation factor.
- Photon-count drift significantly reduced class separability.
- Detector-blind and fiber-tap attacks became highly overlapping under shifted operational conditions.
- Cross-generator evaluation exposed generator-specific learning behavior.
- Robustness validation is necessary for realistic QKD forensic deployment assessment.

### Generator-B Dataset Files

qkd_generator_b_domain_shifted.csv
- Full extreme domain-shift dataset.

qkd_generator_b_filtered_testset.csv
- Four-class filtered evaluation dataset for Generator-B v1.

qkd_generator_b_v2_calibrated.csv
- Calibrated moderate domain-shift dataset.

qkd_generator_b_v2_filtered_testset.csv
- Four-class filtered evaluation dataset for Generator-B v2.


### Generator-B Repository Structure

generator_b/
├── data/
├── metadata/
├── scripts/
└── results/
Full Generator-B resources are available in the `generator_b/` directory.
### Reproducibility
Generator-B includes:
- dataset generation scripts
- parameter metadata JSON files
- robustness evaluation scripts
- visualization scripts
- reproducible robustness analysis workflow
This repository now provides both a QKD forensic dataset and a cross-generator robustness benchmarking framework for QKD forensic machine learning research.
