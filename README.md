Molecular Toxicity Prediction: GNNs vs. Traditional ML

Author: Mandana Roosta-Reza Jafari  
Institution: Physics Department of Shahid Beheshti University  

 Project Overview
The prediction of molecular toxicity is a critical challenge in pharmaceutical development. This project compares the performance of a Graph Convolutional Network (GNN) against traditional machine learning baselines (Random Forest and Logistic Regression) for predicting molecular mutagenicity using the MUTAG dataset. 

Key Finding: Traditional feature-based methods significantly outperformed the GNN approach (86.8% vs 65.8% accuracy), highlighting the importance of dataset size and feature engineering in molecular property prediction.

Dataset (MUTAG)
A standard benchmark for molecular classification containing nitroaromatic compounds labeled as mutagenic or non-mutagenic.
Total molecules: 188 (150 Train / 38 Test)
Classes: 2 (Mutagenic / Non-mutagenic)
Average molecular size: 17.9 atoms
Node features: 7 per atom

Models Implemented
1. Graph Convolutional Network (GNN)
3 GCN layers (64 hidden units) with ReLU and Dropout (p=0.2)
Global mean pooling & Linear classifier
Parameters: 8,962

2. Traditional ML Baselines
Extracted 16 molecular features (e.g., number of atoms, bonds, node feature stats).
Random Forest: 100 estimators
Logistic Regression: L2 regularization

Results

| Method | Test Accuracy | Standard Error |
|--------|---------------|----------------|
| Logistic Regression | 86.8% | ±5.4% |
| Random Forest | 84.2% | ±5.8% |
| Graph Neural Network | 65.8% | ±7.7% |
| Random Baseline | 55.3% | ±8.0% |

Why did Traditional ML win?
1. Dataset Size: Deep learning models require thousands of examples. With only 150 training examples, the GNN overfit the data (Train accuracy: 77.3%, Test accuracy: 65.8%).
2. Feature Engineering: Handcrafted molecular descriptors captured essential chemical patterns more efficiently than learning from raw graph structures on a small scale.

Installation & Setup
To run this notebook locally:
bash
Environment: Python 3.11.13
pip install torch torch-geometric scikit-learn rdkit

Future Work
Larger Datasets: Test the GNN on datasets with thousands of molecules.
Architecture Exploration: Implement Graph Attention Networks (GAT) or Graph Transformers.
Transfer Learning: Pre-train GNNs on large molecular datasets before fine-tuning.# Molecular-Toxicity-Prediction-GNN-vs-Traditional-ML
