# 🌊 Underwater Image Enhancement Using PIXMambaNet

## 📖 Overview

Underwater images often suffer from color distortion, low contrast, haze, and loss of detail due to light absorption and scattering in water. These degradations reduce visibility and affect applications such as marine exploration, underwater robotics, and autonomous navigation.

This minor project investigates the use of **PIXMambaNet**, a Mamba-inspired State Space Model (SSM) architecture, for enhancing underwater images. The model leverages efficient bidirectional sequence modeling to capture long-range dependencies while maintaining linear computational complexity.

The project focuses on training, evaluating, and analyzing PIXMambaNet on benchmark underwater image datasets to improve image quality and restore visual information.

---

## 🎯 Objectives

* Enhance underwater image visibility.
* Correct color distortions caused by underwater environments.
* Improve image contrast and sharpness.
* Restore fine details and textures.
* Evaluate enhancement quality using standard image quality metrics.

---

## 🏗️ Methodology

### PIXMambaNet Architecture

The enhancement network follows an encoder-decoder architecture:

* Encoder:

  * Conv Layer (3 → 32)
  * Conv Layer (32 → 64)

* Bottleneck:

  * Two PixelMamba Blocks

* Decoder:

  * Conv Layer (64 → 32)
  * Conv Layer (32 → 3)

### Key Components

* Bidirectional Feature Processing
* Adaptive Gating Mechanism
* Residual Connections
* State Space Model Inspired Design
* Linear Complexity O(N)

---

## 📂 Datasets Used

### UIEB Dataset

**Underwater Image Enhancement Benchmark (UIEB)**

* Approximately 890 paired images
* Raw underwater images and corresponding reference images
* Used for training and evaluation

### U45 Dataset

* Standard benchmark dataset for underwater image enhancement
* Used for additional testing and qualitative evaluation

---

## 🛠️ Tech Stack

### Programming Language

* Python

### Framework

* PyTorch

### Libraries

* TorchVision
* NumPy
* OpenCV
* Matplotlib
* Pillow
* tqdm
* pytorch-msssim

### Development Environment

* Google Colab
* NVIDIA Tesla P100 GPU

---

## ⚙️ Training Configuration

| Parameter     | Value                 |
| ------------- | --------------------- |
| Epochs        | 50                    |
| Batch Size    | 8                     |
| Learning Rate | 1e-4                  |
| Optimizer     | Adam                  |
| Input Size    | 256 × 256             |
| Loss Function | L1 + 0.5 × (1 − SSIM) |

---

## 📊 Evaluation Metrics

The model performance was evaluated using:

### PSNR

Peak Signal-to-Noise Ratio

### SSIM

Structural Similarity Index Measure

Higher values indicate better enhancement quality and structural preservation.

---

## 📈 Results

### UIEB Test Set

| Metric | Score    |
| ------ | -------- |
| PSNR   | 18.15 dB |
| SSIM   | 0.87     |

### U45 Test Set

| Metric | Score    |
| ------ | -------- |
| PSNR   | 15.73 dB |
| SSIM   | 0.74     |

The enhanced outputs showed noticeable improvements in:

* Color correction
* Contrast enhancement
* Haze reduction
* Detail restoration

---

## 📁 Repository Structure

```text
.
├── analyze/                 # Evaluation and analysis scripts
├── src/
│   ├── dataloaders/         # Dataset handling
│   ├── models/              # PIXMamba model components
│   ├── tasks/               # Training and evaluation tasks
│   └── utils/               # Utility functions
├── arch.png                 # Architecture diagram
├── requirements.txt         # Python dependencies
├── environment.yaml         # Conda environment setup
└── README.md
```

---

## 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/your-username/Minor_Project.git
cd Minor_Project
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 🌍 Applications

* Marine Exploration
* Underwater Robotics
* Autonomous Underwater Vehicles (AUVs)
* Underwater Surveillance
* Ocean Monitoring
* Marine Biology Research

---

## 📚 Learning Outcomes

Through this project, we gained experience in:

* Deep Learning for Image Processing
* State Space Models (Mamba)
* PyTorch Model Training
* Dataset Preparation and Preprocessing
* Performance Evaluation using PSNR and SSIM
* GPU-based Training using Google Colab

---

## 👨‍💻 Team Members

* **Aditya Gupta (2304088)**
* **Vaishnavi Verma (2304023)**
* **Ashish Anand (2304089)**

Department of Electronics and Communication Engineering

National Institute of Technology Patna

Session: 2026–27

---

## 🙏 Acknowledgements

We sincerely thank:

* **Dr. Ashish Kumar Bhandari** for his guidance and supervision.
* **Ms. Khushboo Rani** for her technical support and mentorship.
* The contributors of the UIEB dataset.
* The research community working on Mamba and State Space Models.

---

## 📌 Note

This project was completed as part of the Minor Project requirement for the B.Tech program in Electronics and Communication Engineering at NIT Patna. The work focuses on the implementation, training, evaluation, and analysis of a PIXMamba-based underwater image enhancement framework.
