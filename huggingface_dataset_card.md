---
pretty_name: "QF-LOG: Quantum Forensic Dataset for QKD"
task_categories:
  - anomaly-detection
  - time-series-forecasting
tags:
  - quantum
  - security
  - forensics
  - qkd
license: mit
language:
  - en
size_categories:
  - 10K<n<100K
---

# QF-LOG: Quantum Forensic Dataset for QKD

## Dataset Description

QF-LOG is a synthetic, physics-grounded dataset for detecting attacks in
Quantum Key Distribution (QKD) networks using machine learning.

### Features

- `qber` (float)
- `photon_count` (int)
- `latency_ms` (float)
- `abort_flag` (int)
- `label` (categorical)
- `session_id`, `frame_index` (for time-series v2)

### Splits

No predefined split. Users commonly use 75/25 train/test and 5-fold CV.

### Licensing

Recommended: MIT for code & generation scripts, CC-BY-4.0 for the dataset itself.

