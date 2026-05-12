# Federated Learning for Brain Tumor Classification with Homomorphic Encryption

This repository implements a **privacy‑preserving federated learning** framework for brain tumor classification from medical images (MRI). It combines federated averaging with **CKKS** and **BFV** homomorphic encryption schemes to securely aggregate model updates without exposing raw patient data.

## Overview

Centralized medical AI requires pooling sensitive patient scans into one server – a privacy risk. Federated learning (FL) trains models locally on hospital data and only shares encrypted gradients/weights with a central server. This project:

- Implements FL using a CNN‑based brain tumor classifier (binary or multi‑class).
- Encrypts local model updates with Microsoft SEAL’s **CKKS** (for floating‑point) and **BFV** (for integers).
- Provides notebooks to reconstruct and validate encryption/decryption.
- Includes a baseline **centralized learning** approach for comparison.

## Repository Structure
├── Centralized_learning/ # Baseline training on pooled data
├── Federated_learning/ # Standard FL (no encryption)
├── Federated_Learning_Encryption/ # FL + homomorphic encryption (CKKS/BFV)
├── Brain_Tumor_Classification_Based_on_Federated_Learning/ # Main classifier code
├── Encrypt_ckks_bfv1.ipynb # Notebook: CKKS & BFV reconstruction & tests
├── Paper.pdf # Related research paper (e.g., reference or pre‑print)
└── README.md # This file



## Features

- **Two encryption schemes** – CKKS (approximate floating‑point) and BFV (exact integer).
- **Modular design** – Easily swap between plain FL, CKKS‑encrypted FL, and BFV‑encrypted FL.
- **Brain tumor dataset** – Supports popular datasets (Figshare, BraTS, or custom) with preprocessing.
- **Reconstruction notebook** – `Encrypt_ckks_bfv1.ipynb` demonstrates encryption, aggregation, and decryption step‑by‑step.
- **Reproducible experiments** – Compare accuracy, communication cost, and overhead.

## Getting Started

### Prerequisites

- Python 3.8+
- [Microsoft SEAL](https://github.com/microsoft/SEAL) (homomorphic encryption library)
- TensorFlow / PyTorch (depending on implementation)
- Jupyter Notebook or JupyterLab

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/amintunig/IEEE_BigData_2025-Dataset-with-code.git
2. **Install dependencies
pip install -r requirements.txt

If requirements.txt is not present, install manually:
pip install numpy pandas matplotlib tensorflow torch seal-python notebook

3. **Install Microsoft SEAL

Pre‑built wheels: pip install seal

Or build from source: SEAL GitHub
