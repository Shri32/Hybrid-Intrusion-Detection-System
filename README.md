# Neuro-Symbolic Intrusion Detection System (NS-IDDS)

AI-Powered Intrusion Detection using Isolation Forest, LightGBM, SHAP Explainability, and MITRE ATT&CK Reasoning.

---

## Overview

This project presents a hybrid neuro-symbolic intrusion detection system designed for multi-class cyber attack detection using the UNSW-NB15 dataset.

The system combines:

* Unsupervised anomaly detection using Isolation Forest
* Supervised multi-class classification using LightGBM
* Explainable AI using SHAP
* Symbolic reasoning using MITRE ATT&CK mappings

Unlike traditional IDS systems that only classify traffic, this architecture also explains:

* Why a flow was flagged
* Which features influenced the decision
* Which MITRE ATT&CK tactics and techniques were triggered
* How anomaly signals contributed to the final prediction

The objective is to build an interpretable, explainable, and intelligence-aware intrusion detection pipeline.

---

## Key Features

### Hybrid Detection Architecture

* Isolation Forest used for anomaly signal generation
* LightGBM used for multi-class attack classification
* Anomaly outputs appended as augmented features

### Explainable AI Pipeline

* SHAP-based global and local explainability
* Per-class anomaly contribution analysis
* Top feature attribution visualization

### Neuro-Symbolic Reasoning Layer

* MITRE ATT&CK tactic mapping
* Technique-level symbolic matching
* Human-readable attack explanations

### Advanced Visual Analytics

* Confusion Matrix
* SHAP Global Importance Plot
* Isolation Forest Distribution Analysis
* MITRE ATT&CK Coverage Visualization

---

## Architecture

```text
Raw Network Flows
        │
        ▼
Preprocessing + Encoding
        │
        ▼
Isolation Forest
(Anomaly Scoring)
        │
        ├── anomaly_score_norm
        └── is_anomaly_flag
                │
                ▼
Augmented Feature Matrix
                │
                ▼
LightGBM Multi-Class Classifier
                │
                ▼
SHAP Explainability Engine
                │
                ▼
MITRE ATT&CK Symbolic Mapping
                │
                ▼
Human-Readable Threat Intelligence
```

---

## Dataset

Dataset Used:

* UNSW-NB15

The dataset contains modern network traffic with multiple attack categories including:

* Analysis
* Backdoor
* DoS
* Exploits
* Fuzzers
* Generic
* Reconnaissance
* Shellcode
* Worms
* Normal traffic

---

## Tech Stack

### Machine Learning

* LightGBM
* Isolation Forest
* SHAP
* Scikit-learn

### Data Processing

* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Environment

* Python
* Google Colab

---

## Detection Pipeline

### Stage 1 — Data Preprocessing

* Dataset loading
* Missing value handling
* Label encoding
* Standard scaling

### Stage 2 — Anomaly Detection

Isolation Forest generates:

* Continuous anomaly scores
* Binary anomaly flags

These outputs are appended to the original feature space.

### Stage 3 — Multi-Class Classification

LightGBM performs:

* Multi-class intrusion classification
* Weighted training using class balancing
* Early stopping optimization

### Stage 4 — Explainability

SHAP is used for:

* Global feature importance
* Per-flow reasoning
* Per-class anomaly contribution analysis

### Stage 5 — Symbolic Threat Reasoning

Predictions are mapped to:

* MITRE ATT&CK tactics
* ATT&CK techniques
* Human-readable intelligence explanations

---

## MITRE ATT&CK Integration

The symbolic reasoning engine maps predictions to real-world cyber attack behaviors.

Example mappings:

| Attack Class   | MITRE Tactic     | Example Technique                         |
| -------------- | ---------------- | ----------------------------------------- |
| DoS            | Impact           | T1498 - Network Denial of Service         |
| Reconnaissance | Reconnaissance   | T1595 - Active Scanning                   |
| Backdoor       | Persistence      | T1571 - Non-Standard Port                 |
| Shellcode      | Execution        | T1059 - Command and Scripting Interpreter |
| Worms          | Lateral Movement | T1021 - Remote Services                   |

---

## Explainability Features

### Global SHAP Analysis

The model computes:

* Mean feature contribution
* Top anomaly-driven features
* Class-wise interpretability

### Local Flow Explanations

For each network flow:

* Top SHAP features are extracted
* MITRE techniques are matched
* Human-readable alerts are generated

Example:

```text
VERDICT: ATTACK
PREDICTED CLASS: DOS
MITRE TACTIC: TA0040 - Impact
TECHNIQUE: T1498 - Network Denial of Service
TOP FEATURES:
- sload
- dload
- anomaly_score_norm
```

---

## Visual Outputs

The pipeline generates:

* Confusion Matrix
* SHAP Global Importance Plot
* Isolation Forest Distribution Plot
* MITRE ATT&CK Coverage Chart
* Per-Class Metrics CSV
* Full IDS Reasoning CSV

---

## Performance Metrics

The model evaluates:

* Accuracy
* Precision
* Recall
* F1-score
* Per-class metrics

Additional explainability metrics:

* SHAP contribution analysis
* Anomaly feature importance
* Technique-level symbolic matches

---

## Project Structure

```text
NeuroSymbolic-IDS/
│
├── notebooks/
│   └── neuro_symbolic_ids.ipynb
│
├── images/
│   ├── confusion_matrix.png
│   ├── shap_global_importance.png
│   ├── mitre_tactic_coverage.png
│   └── if_score_distribution.png
│
├── results/
│   ├── idds_full_results.csv
│   ├── per_class_metrics.csv
│   └── anomaly_shap_contribution.csv
│
├── README.md
├── requirements.txt
└── LICENSE
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/your-username/NeuroSymbolic-IDS.git
cd NeuroSymbolic-IDS
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Project

Open the notebook:

```bash
jupyter notebook
```

OR run using Google Colab.

Dataset ZIP should be placed inside Google Drive before execution.

---

## Future Improvements

* Real-time packet capture integration
* Deep learning sequence models (LSTM/Transformer)
* Streaming IDS architecture
* Threat intelligence API integration
* SIEM integration
* Real-time dashboard deployment
* Adversarial robustness evaluation

---

## Research Focus

This project explores:

* Explainable cybersecurity AI
* Neuro-symbolic intrusion detection
* Human-interpretable machine learning
* Hybrid anomaly + classification systems
* Cyber threat intelligence mapping

---

## Author

### Shrimant Sharma

AI/ML • Cybersecurity • Backend Systems • Full Stack Development

Interested in:

* Explainable AI
* Intelligent Security Systems
* Neuro-Symbolic Architectures
* AI-driven Cyber Defense

---

## License

This project is intended for research and educational purposes.
