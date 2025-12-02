# AJD: Directed Hierarchy Analysis for Topological Data Analysis

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![Status](https://img.shields.io/badge/status-research-orange)

## 📖 Overview

**AJD (Análisis de Jerarquía Dirigido / Directed Hierarchy Analysis)** is a novel variable selection and dimensionality reduction algorithm based on **Topological Data Analysis (TDA)**. 

Unlike traditional statistical methods (e.g., PCA) that focus on variance, AJD iteratively evaluates the topological significance of variables by analyzing the stability and structure of their associated **Persistence Diagrams**. This project provides a robust implementation for computing directed hierarchies using multiple topological metrics, including Wasserstein distance, Bottleneck distance, and Persistent Entropy.

This research draws theoretical inspiration from **Toric Topology**, specifically the combinatorial structure of **Moment-Angle Complexes ($\mathcal{Z}_K$)**, aiming to bridge the gap between algebraic topology invariants and data feature selection.

## ✨ Key Features

- **Topological Variable Selection**: Iteratively removes variables to preserve or maximize specific topological features ($H_0$ components, $H_1$ loops).
- **Multi-Metric Support**:
  - **`was`**: Wasserstein distance (Optimal Transport).
  - **`btn`**: Bottleneck distance (Stability Metric).
  - **`ent`**: Persistent Entropy (Shannon Entropy of topology).
  - **`pet`**: Total Persistence (Signal strength).
- **Scikit-TDA Integration**: Built upon the industry-standard `ripser` and `persim` libraries for high-performance computation.
- **Theoretical Depth**: Explores finer combinatorial invariants inspired by the cohomology rings of moment-angle complexes.

## 🧮 Mathematical Background

The core philosophy of this algorithm is inspired by the relationship between a simplicial complex $K$ and its associated **Moment-Angle Complex** $\mathcal{Z}_K$. 

According to **Hochster's Formula**, the cohomology of $\mathcal{Z}_K$ decomposes into the cohomology of full subcomplexes of $K$:

$$H^*(\mathcal{Z}_K; \mathbb{k}) \cong \bigoplus_{J \subseteq [m]} \widetilde{H}^{*-|J|-1}(K_J; \mathbb{k})$$

Where $K_J$ is the full subcomplex of $K$ on the vertex set $J$. 
In the context of TDA, we hypothesize that the "optimal" subset of variables corresponds to a subcomplex $K_J$ that maximizes topological signal-to-noise ratio. AJD attempts to algorithmically navigate this combinatorial lattice to find such optimal substructures.

## 🛠️ Installation

This project relies on specific versions of scientific computing libraries to ensure reproducibility.

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/yourusername/AJD-Topology.git](https://github.com/yourusername/AJD-Topology.git)
   cd AJD-Topology