# Interactive Multimodal Fetal Medical Image Segmentation Using Nested-SAM and CA-FedAvg

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.10+-red.svg)](https://pytorch.org/)
[![Flower](https://img.shields.io/badge/Flower-1.0+-green.svg)](https://flower.dev/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Official implementation of the paper:**  
> *Interactive Multimodal Fetal Medical Image Segmentation Using Nested Segment Anything Model and Class-adaptive Federated Learning*  
> Lipeng Xie, Lichen Zhao, Shuaiwei Wu, Yi Song, Cheng Dai*  
> *(Accepted to IEEE Journal of Biomedical and Health Informatics, 2025)*

This repository provides the complete code, pretrained models, and interactive GUI for the proposed framework, which combines a lightweight **Nested Segment Anything Model (Nested-SAM)** with a **Class-Adaptive Federated Averaging (CA-FedAvg)** strategy for privacy-preserving, multi-center fetal image segmentation.

---

## 📌 Key Features

- **Nested-SAM** – A novel SAM architecture with dense nested U-Net encoder and early prompt-guided cross‑fusion, achieving 20× smaller model size than SAM‑Med2D while improving Dice on placental vessels by 8.78%.
- **CA-FedAvg** – A class‑adaptive federated aggregation mechanism that balances static class contribution weights and dynamic performance scores, mitigating model drift caused by Non‑IID multi‑center data.
- **Privacy‑Preserving Interactive System** – Full Client/Server software with AES‑256‑GCM encryption and PBKDF2 key derivation; clinical GUI supports point/box prompts with real‑time segmentation feedback.
- **Multimodal Fetal Datasets** – Supports ultrasound, MRI, and fetoscopic images; includes data partitioning scripts for simulating Non‑IID clients.

---

## 🏗️ System Architecture

![System Architecture](docs/system_architecture.png)

*Left*: Local clients train Nested-SAM on private fetal data. *Right*: Central server aggregates model updates using CA-FedAvg (class contribution matrix + performance scoring). Secure encryption is applied to all network transmissions.

---

## 📦 Installation

### 1. Clone the repository
```bash
git clone https://github.com/yourlab/fetal-fed-nested-sam.git
cd fetal-fed-nested-sam
