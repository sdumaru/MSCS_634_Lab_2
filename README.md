# MSCS 634 Lab 2: Classification Using KNN and RNN Algorithms

## Purpose
This notebook compares two distance-based classifiers: K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) on the UCI Wine dataset. Tasks include:
- Loading and exploring chemical-feature data for three wine classes
- Evaluating KNN over several k values
- Evaluating RNN over several radius values
- Visualizing accuracy trends, and confusion matrices

## Key Insights
- **KNN Performance**
  - Peak test accuracy ≈ 77.8 % at k = 1 and k = 21
  - Confusion matrix shows perfect classification for classes 0 and 2, with only two misclassifications in class 1
  - Local neighborhoods preserve class boundaries and yield high recall/precision
- **RNN Performance**
  - Peak test accuracy ≈ 55.6 % at radius = 350 and 500
  - Perfect recall for class 1 but severe misclassification of classes 0 and 2 (collapsed into class 1)
  - Fixed-radius neighborhoods can over-smooth and bias toward the dominant cluster
- **Model Comparison**
  - KNN outperforms RNN by a wide margin on overall accuracy and balanced class performance
  - RNN may be useful when neighborhood density varies, but here fixed radii fail on sparse classes

## Challenges and Decisions  
- **Feature Scaling**  
  - Applied StandardScaler to ensure all 13 chemical features contribute equally to distance metrics
- **Parameter Selection**
  - Chose odd k values (1, 5, 11, 15, 21) to avoid voting ties
  - Tested radii (350–600) to span small to large neighborhoods relative to dataset scale
- **Visualization**
  - Added confusion matrices for per-class error patterns

---
**Repository Contents**
- `Lab2_Wine_KNN_RNN.ipynb` – Jupyter notebook with all code and analysis
- `README.md` – This summary of purpose, insights, and implementation notes
