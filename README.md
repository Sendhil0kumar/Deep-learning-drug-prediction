# 💊 Deep Learning for Drug Property Prediction

## Project Description
This project implements and compares two distinct Deep Learning methodologies—a **Dense Neural Network (DNN)** and a **Graph Neural Network (GNN)**—to predict drug properties from molecular structure using the **DrugLib dataset**.

The task is a **Regression** problem aimed at predicting the user-assigned drug **`rating`** (1-10) based on the molecule's chemical identifier.

---

## 1. Methodology and Model Comparison

The core of the assignment lies in the feature engineering required to transform the molecular structure into an input for the neural networks.

### Model A: Dense Neural Network (DNN)
* **Input:** **1024-bit Molecular Fingerprints** (A fixed-length, binary vector that encodes the presence of chemical fragments).
* **Architecture:** Fully connected (Dense) layers with ReLU activation and Dropout regularization.
* **Performance (Test Set):**
    * **Mean Absolute Error (MAE):** **2.3530** (The average error in rating points).

### Model B: Graph Neural Network (GNN)
* **Input:** **Molecular Graph Structure** (Atoms = Nodes, Bonds = Edges).
* **Architecture:** Conceptually uses **Graph Convolutional Layers ($\text{GCN}$)** followed by a **Global Pooling** layer.

#### 💡 Theoretical Advantage of GNN
The GNN is theoretically superior for Cheminformatics because it processes the molecule's true **graph topology** 

[Image of chemical structure diagram]
, capturing atomic connectivity and local chemical environments that are lost when the structure is simplified into a flat fingerprint vector for the DNN.

---

## 2. Data and Execution

### Dataset
The project utilizes the DrugLib dataset, split into `drugLibTrain_raw.tsv` and `drugLibTest_raw.tsv`.

### Dependencies
The project relies on the following key Python libraries:
* `tensorflow` / `keras` (For model building)
* `pandas` / `numpy` (For data handling)
* `matplotlib` / `seaborn` (For visualization)

### Setup
The model training can be replicated by running the main Jupyter Notebook (`drug_prediction_assignment.ipynb`) located in the `notebooks/` directory.
