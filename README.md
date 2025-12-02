# DHA: Directed Hierarchy Analysis for Topological Data Analysis

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![Status](https://img.shields.io/badge/status-research-orange)

## 📖 Overview

**DHA (Directed Hierarchy Analysis) / AJD (Análisis de Jerarquía Dirigido)** is a novel variable selection and dimensionality reduction algorithm based on **Topological Data Analysis (TDA)**. 

Unlike traditional statistical methods (e.g., PCA) that focus on variance, DHA iteratively evaluates the topological significance of variables by analyzing the stability and structure of their associated **Persistence Diagrams**. This project provides a robust implementation for computing directed hierarchies using multiple topological metrics, including Wasserstein distance, Bottleneck distance, and Persistence Entropy.

## ✨ Key Features

- **Topological Variable Selection**: Iteratively removes variables to preserve or maximize specific topological features ($H_0$ components, $H_1$ loops).
- **Multi-Metric Support**:
  - **`was`**: Wasserstein distance (Optimal Transport).
  - **`btn`**: Bottleneck distance (Stability Metric).
  - **`ent`**: Persistence Entropy (Shannon Entropy of topology).
  - **`pet`**: Total Persistence (Signal strength).
- **Scikit-TDA Integration**: Built upon the industry-standard `ripser` and `persim` libraries for high-performance computation.
- **Theoretical Depth**: Explores finer combinatorial invariants inspired by the cohomology rings of moment-angle complexes.

## 📘 Theoretical Foundation (Thesis)

**Title:** Dimensionality reduction based on persistence entropy

**[📄 Read Full Thesis (PDF)](./Dimensionality reduction based on persistence entropy.pdf)**
**[🔗 View on Google Scholar](https://diposit.ub.edu/items/f23f73ff-79ad-4da8-ad69-dd59a7bc627d)**
The framework bridges **Algebraic Topology** and **Feature Selection** algorithms. The theoretical and algorithmic core involves:

* **Simplicial Homology & Persistence:** Modeling high-dimensional data as **Simplicial Complexes** (e.g., via Rips filtration). The algorithm explicitly tracks the evolution of topological features—specifically **Connected Components ($H_0$)** and **Loops/Holes ($H_1$)**—to generate **Persistence Diagrams**.
* **Topological Information Theory:** Utilizing **Topological Persistence Entropy (TPE)** to quantify the complexity and information content of the dataset's topological structure, serving as a robust measure alongside geometric stability.
* **Backward Elimination Strategy:** Adapting the **Backward Regression** principle from classical statistics to the topological domain. 
    * The algorithm performs an iterative process where, at each step, variables are evaluated based on the **Topological Distance** (Wasserstein, Bottleneck, or Entropy difference) between the reduced dataset's persistence diagram and the original reference diagram.
    * This "Directed Hierarchy" approach identifies the optimal subset of variables that best preserves the intrinsic topological shape of the data.

**Note:** For detailed mathematical definitions, stability proofs of the used metrics, and the complete theoretical derivation, please refer to the full thesis text (available upon request).

## 🛠️ Installation

This project relies on specific versions of scientific computing libraries to ensure reproducibility.

### Setup
```bash
# 1. Clone this repository
git clone https://github.com/JunhanCui/Final-work-for-Bachelor.git
cd Final-work-for-Bachelor

# 2. Install dependencies

pip install -r requirements.txt


