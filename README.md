# QF-LOG: Quantum Forensic Dataset for QKD Networks

 QKD Forensic Dataset

This repository contains a realistic and physics-informed Quantum Key Distribution (QKD) forensic dataset.
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Dataset Size](https://img.shields.io/badge/Dataset-50k%20samples-brightgreen)
![Time Series](https://img.shields.io/badge/Version-LSTM%20timeseries-blueviolet)
![Domain](https://img.shields.io/badge/Domain-Quantum%20Forensics-purple)
![QKD](https://img.shields.io/badge/QKD-Security%20Dataset-blue)
![ML Ready](https://img.shields.io/badge/ML-Ready-green)
![DL Ready](https://img.shields.io/badge/Deep%20Learning-LSTM%20Compatible-orange)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Format](https://img.shields.io/badge/Format-CSV-lightgrey)
![Research Ready](https://img.shields.io/badge/Research-Publication%20Ready-yellowgreen)
![Open Source](https://img.shields.io/badge/Dataset-Open%20Source-success)
![GitHub stars](https://img.shields.io/github/stars/YOUR_USERNAME/QKD-Forensic-Dataset?style=social)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Dataset Size](https://img.shields.io/badge/Dataset-50k%20samples-brightgreen)
![Time Series](https://img.shields.io/badge/Version-LSTM%20timeseries-blueviolet)
![Domain](https://img.shields.io/badge/Domain-Quantum%20Forensics-purple)
![QKD](https://img.shields.io/badge/QKD-Security%20Dataset-blue)
![ML Ready](https://img.shields.io/badge/ML-Ready-green)
![DL Ready](https://img.shields.io/badge/Deep%20Learning-LSTM%20Compatible-orange)
![Format](https://img.shields.io/badge/Format-CSV-lightgrey)
![Research Ready](https://img.shields.io/badge/Research-Publication%20Ready-yellowgreen)
![Open Source](https://img.shields.io/badge/Dataset-Open%20Source-success)

![Downloads](https://img.shields.io/github/downloads/YOUR_USERNAME/QKD-Forensic-Dataset/total)
![Last Commit](https://img.shields.io/github/last-commit/YOUR_USERNAME/QKD-Forensic-Dataset)
![Issues](https://img.shields.io/github/issues/YOUR_USERNAME/QKD-Forensic-Dataset)
![PRs](https://img.shields.io/github/issues-pr/YOUR_USERNAME/QKD-Forensic-Dataset)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
[![HuggingFace](https://img.shields.io/badge/Dataset-HuggingFace-yellow.svg)](https://huggingface.co/datasets/YOUR_USERNAME/QKD-Forensic-Dataset)

QF-LOG is a physics-grounded synthetic dataset for attack detection in Quantum Key Distribution (QKD) networks.

## Contents

- `full_qkd_dataset_realistic_50000.csv` – main tabular dataset
- `qkd_timeseries_lstm_v2.csv` – time-series version for LSTM/1D-CNN
- `dataset_card.md` – dataset card
- `huggingface_dataset_card.md` – template for HuggingFace Hub
- `website/index.html` – simple dataset website
- `supplementary_dataset_description.pdf` – paper-ready dataset description
- `README.md` – this file
- `LICENSE_MIT`, `LICENSE_Apache2`, `LICENSE_GPL3`, `LICENSE_CC-BY-4.0` – choose one

## Attack Classes
- normal
- intercept_resend
- detector_blind
- fiber_tap

  ## Features
- QBER  
- Photon Count  
- Latency  
- Abort Flag  

## Quick Start

```python
import pandas as pd
df = pd.read_csv("full_qkd_dataset_realistic_50000.csv")
print(df.head())
```

## Citation

> Das, M.C., "QF-LOG: A Machine Learning Forensic Dataset for QKD Networks", 2025.
