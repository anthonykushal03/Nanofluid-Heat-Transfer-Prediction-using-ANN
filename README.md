# Nanofluid Heat Transfer Prediction

This project uses Artificial Neural Networks (ANNs) to predict the heat transfer coefficient of nanofluids. It also compares ANN settings and applies K-Means clustering to explore patterns in flow velocity and heat transfer.

Completed as part of the Machine Learning course (CH6870) at IIT Hyderabad.

## Dataset

The dataset (`data/nanofluid_dataset.xlsx`) contains 10,293 records. Inputs include nanoparticle type, base fluid, volume fraction, temperature, flow velocity and thermophysical properties. The target is the heat transfer coefficient (W/m²K).

## Notebooks

| Notebook | Work |
|---|---|
| `01_ann_baseline.ipynb` | Builds a baseline ANN and compares Adam and RMSProp. |
| `02_ann_hyperparameter_study.ipynb` | Tests network layers, neurons, activation functions, epochs and training data size. |
| `03_kmeans_clustering.ipynb` | Uses K-Means to group records by flow velocity and heat transfer coefficient. |

## Method

The ANN dataset is split into training, validation and test sets (70:15:15). Categorical features are one-hot encoded, and numerical features and the target are scaled using the training data. Model predictions are converted back to the original units for evaluation.

## Key Results

- **Baseline ANN:** Adam achieved a test R² of **0.9874**, slightly better than RMSProp (0.9843).
- **Hyperparameter study:** The `tanh` activation achieved the best validation R² (**0.9936 ± 0.0002**). The selected `[64, 32]` network achieved a test R² of **0.9935 ± 0.0004**.
- **K-Means:** Three clusters were selected for easier interpretation. They represent groups with low, moderate and high heat transfer coefficients across different flow velocities.
