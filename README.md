# QF-LOG: Quantum Forensic Dataset for QKD Networks

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE_MIT)
[![Dataset](https://img.shields.io/badge/dataset-50k%20samples-green.svg)]()
[![Quantum](https://img.shields.io/badge/domain-Quantum%20Forensics-purple.svg)]()

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

## Quick Start

```python
import pandas as pd
df = pd.read_csv("full_qkd_dataset_realistic_50000.csv")
print(df.head())
```

## Citation

> Das, M.C., "QF-LOG: A Machine Learning Forensic Dataset for QKD Networks", 2025.
