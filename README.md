# Generator-B Robustness Validation Extension

## Overview

Generator-B is a domain-shifted physics-inspired QKD operational simulator developed to evaluate forensic machine learning robustness under unseen operational conditions.

The original QF-LOG dataset used a single synthetic generator (Generator-A). Although the original machine learning models achieved high internal validation accuracy, robustness under operational variation remained uncertain.

Generator-B was developed to address this limitation through cross-generator robustness evaluation.

---

## Purpose

The Generator-B framework was designed to evaluate whether machine learning models trained on Generator-A can generalize under:

- unseen hardware conditions
- detector calibration drift
- varying fiber attenuation and loss
- temporal operational instability
- environmental noise
- shifted feature distributions
- overlapping operational boundaries

The framework supports forensic robustness testing for QKD attack detection systems.

---

## Generator-B Features

Generator-B introduces multiple operational domain-shift factors, including:

- unseen hardware profiles
- detector calibration drift
- varying fiber attenuation/loss
- temporal operational noise
- environmental instability
- shifted photon-count distributions
- shifted latency distributions
- noisy QBER behavior
- overlapping class boundaries

Generator-B also optionally supports an additional:

- calibration_drift_attack class

for future robustness research.

---

## Generator-B Variants

### Generator-B v1

Extreme domain-shift scenario designed to stress-test forensic model robustness under severe operational drift.

Characteristics:
- strong feature distribution shifts
- high operational instability
- substantial class overlap
- severe latency drift
- aggressive photon-count variation

---

### Generator-B v2

Calibrated moderate domain-shift scenario designed to simulate more realistic deployment conditions while preserving operational uncertainty and overlap.

Characteristics:
- moderated feature drift
- reduced operational instability
- calibrated overlap conditions
- more realistic deployment variation

---

## Dataset Files

### data/qkd_generator_b_domain_shifted.csv
Full Generator-B v1 dataset with extreme operational domain shift.

### data/qkd_generator_b_filtered_testset.csv
Filtered four-class evaluation dataset derived from Generator-B v1.

### data/qkd_generator_b_v2_calibrated.csv
Full Generator-B v2 dataset with calibrated moderate domain shift.

### data/qkd_generator_b_v2_filtered_testset.csv
Filtered four-class evaluation dataset derived from Generator-B v2.

---

## Metadata Files

### metadata/generator_b_parameters.json
Contains Generator-B v1 operational generation parameters.

### metadata/generator_b_v2_parameters.json
Contains Generator-B v2 calibrated operational parameters.

---

## Scripts

### Dataset Generation
- qkd_generator_b_domain_shifted.py
- qkd_generator_b_v2_calibrated.py

### Testset Preparation
- create_generator_b_filtered_testset.py
- create_generator_b_v2_filtered_testset.py

### Cross-Generator Evaluation
- train_generator_a_test_generator_b.py
- train_generator_a_test_generator_b_v2.py

### Analysis and Visualization
- analyze_domain_shift.py
- visualize_generator_b.py
- generate_robustness_comparison.py

---

## Cross-Generator Robustness Evaluation

Training dataset:
- Generator-A

Testing datasets:
- Generator-B v1
- Generator-B v2

Models evaluated:
- Random Forest
- XGBoost

---

## Main Robustness Results

| Test Dataset | RF Accuracy | XGBoost Accuracy |
|---|---|---|
| Generator-B v1 | 0.2591 | 0.2451 |
| Generator-B v2 | 0.3358 | 0.2856 |

The results demonstrate substantial degradation under operational domain shift, indicating that internal validation alone may overestimate forensic robustness.

---

## Main Findings

- Internal validation alone overestimated robustness.
- Latency distribution shift was the strongest degradation factor.
- Photon-count drift significantly reduced class separability.
- Detector-blind and fiber-tap classes became highly overlapping under shifted operational conditions.
- Cross-generator testing exposed generator-specific learning behavior.
- Robustness validation is necessary for realistic forensic deployment assessment.

---

## Repository Structure

generator_b/
├── data/
├── metadata/
├── scripts/
└── results/

---

## Reproducibility

Generator-B includes:

- dataset generation scripts
- reproducible parameter files
- robustness evaluation scripts
- visualization scripts
- feature-shift analysis workflow
- cross-generator evaluation workflow

For reproducibility of published results, use the released dataset files as-is.

---

## License

Dataset files follow the repository dataset license.

Scripts and source code follow the repository code license.

---

## Citation

If you use Generator-B or the robustness evaluation framework in academic work, please cite the associated dataset and paper resources from the main repository README.