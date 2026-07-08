# Intrusion Detection System using Deep Reinforcement Learning

An AI-powered **Network Intrusion Detection System (IDS)** that performs **multi-class cyberattack detection** using the **CICIDS2017 dataset**. The project combines deep learning, feature engineering, generative models, and reinforcement learning to accurately identify different categories of network attacks.

---

## Project Overview

Traditional intrusion detection systems often struggle with highly imbalanced datasets and complex attack patterns.

This project addresses those challenges by integrating:

- Attention-Based Feature Selection
- Autoencoder-based Feature Compression
- CTGAN-based Minority Class Oversampling
- Dueling Double Deep Q Network (D3QN)
- Deep Neural Network Classifier

The complete pipeline improves feature representation, balances minority attack classes, and enhances multi-class intrusion detection performance.

---

## Dataset

**Dataset Used:** CICIDS2017

The dataset contains network flow statistics extracted using CICFlowMeter and includes both benign traffic and multiple attack categories.

Examples of attack classes include:

- Benign
- DDoS
- DoS Hulk
- DoS GoldenEye
- Slowloris
- PortScan
- Bot
- FTP-Patator
- SSH-Patator
- Web Attack
- Infiltration
- Heartbleed

Each flow contains **78 statistical features** describing packet counts, timing, TCP flags, packet lengths, flow duration, and many other network characteristics.

---

# Project Pipeline

```
CICIDS2017 Dataset
        │
        ▼
Data Cleaning
        │
        ▼
Normalization
        │
        ▼
Attention-Based Feature Selection
        │
        ▼
Autoencoder Feature Compression
        │
        ▼
CTGAN Oversampling
        │
        ▼
Dueling Double DQN
        │
        ▼
Dense Neural Network Classifier
        │
        ▼
Attack Prediction
```

---

# Features

- Multi-class intrusion detection
- Automatic feature importance learning
- Deep feature extraction
- Minority class balancing using CTGAN
- Reinforcement Learning based classifier
- High-dimensional network traffic analysis
- Model saving and loading support
- Performance visualization
- Confusion matrix generation
- Classification report generation

---

# Technologies Used

## Programming Language

- Python

## Deep Learning

- TensorFlow
- Keras

## Machine Learning

- Scikit-learn

## Data Processing

- NumPy
- Pandas

## Visualization

- Matplotlib

## Other Libraries

- Kneed
- Pickle
- JSON

---

# Deep Learning Architecture

## 1. Attention Feature Selection Network

The first neural network learns the importance of each feature using an attention mechanism.

Architecture:

```
Input Features
      │
Dense (Softmax Attention)
      │
Feature Weighting
      │
Dense (128)
      │
Dense (64)
      │
Output
```

---

## 2. Autoencoder

The autoencoder compresses the selected features into a compact latent representation.

```
Input
   │
Dense
   │
Dense
   │
Bottleneck Layer
   │
Dense
   │
Dense
   │
Reconstructed Output
```

---

## 3. CTGAN

Conditional Tabular GAN is used to generate synthetic samples for minority attack classes.

Components:

- Generator
- Discriminator
- Conditional Sampling

Benefits:

- Handles class imbalance
- Improves minority attack detection
- Generates realistic synthetic traffic

---

## 4. Dueling Double DQN

The reinforcement learning model predicts attack classes using separate value and advantage streams.

Architecture:

```
Input
   │
Shared Dense Layers
   │
 ┌───────────────┐
 │               │
Value Stream  Advantage Stream
 │               │
 └───────Combine─┘
        │
      Q Values
```

Advantages:

- Better convergence
- Stable learning
- Improved classification accuracy

---

## 5. Final Neural Network Classifier

Features extracted from the DQN are passed to a dense neural network for final attack classification.

Architecture:

```
Input
 │
Dense
 │
Batch Normalization
 │
Dropout
 │
Dense
 │
Output Layer
```

---

# Data Preprocessing

The preprocessing pipeline includes:

- Removing missing values
- Handling infinite values
- Feature scaling using Min-Max Normalization
- Label Encoding
- Train/Test Split
- Feature Selection
- Feature Compression

---

# Model Training

The notebook trains:

- Attention Network
- Autoencoder
- CTGAN
- Dueling Double DQN
- Dense Classifier

Early stopping is used to prevent overfitting.

---

# Evaluation Metrics

The project evaluates performance using:

- Accuracy
- Precision
- Recall
- F1 Score
- Macro F1
- Weighted F1
- Confusion Matrix
- Classification Report
- Detection Rate
- False Alarm Rate
- Matthews Correlation Coefficient (MCC)


---

# Installation

Install dependencies:

```bash
pip install tensorflow
pip install pandas
pip install numpy
pip install matplotlib
pip install scikit-learn
pip install kneed
```

---

# Running the Project

Open the notebook:

```bash
jupyter notebook Finalyearproject.ipynb
```

or

```bash
Google Colab
```

Run all cells sequentially.

---

# Model Saving

The notebook automatically saves:

- Encoder
- DQN Model
- Classifier
- Scaler
- Label Encoder
- Metadata
- Class Names

---

# Future Improvements

- Real-time packet capture
- Live network monitoring
- Explainable AI (XAI)
- REST API deployment
- Web dashboard
- Cloud deployment
- Edge device support

---

# Applications

- Enterprise Network Security
- Cybersecurity Research
- Intrusion Detection Systems
- Security Operations Centers (SOC)
- Smart Networks
- Cloud Security
- Critical Infrastructure Protection

---

# Author

**Vurvik Korukonda**

Computer Science Engineering

---

# Acknowledgements

- CICIDS2017 Dataset
- TensorFlow
- Keras
- Scikit-learn
- Google Colab
- Canadian Institute for Cybersecurity

---

# License

This project is intended for educational and research purposes.
