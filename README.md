# Spatiotemporal Wildfire Risk Prediction using Evolutionary Algorithms

This project presents a **physics-informed Genetic Algorithm (GA)** for efficient spatiotemporal wildfire risk prediction, designed for **autonomous drones and swarm-based scouting** in compute- and bandwidth-constrained environments.

Unlike traditional grid-based risk mapping or deep learning approaches that require exhaustive scanning, this method actively searches for high-risk ignition zones using **local environmental signals**.

---

## 🚀 Key Contributions
- Physics-guided **Genetic Algorithm** for wildfire risk localization
- Achieves **<1% computational cost** compared to exhaustive grid scanning
- Robust to **climate regime shifts** via physics-only ablation study
- Suitable for **real-time autonomous deployment**

---

## 🧠 Method Overview

### Baseline Model
- Random Forest classifier trained on historical wildfire data
- Generates a dense ground-truth wildfire risk map
- Uses spatial, meteorological, fuel, and terrain features

### Heuristic Evolutionary Model
- Genetic Algorithm guided by a physics-informed fitness function
- Fitness integrates:
  - Vegetation density (NDVI / fuel)
  - Terrain slope & elevation
  - Weather risk indices (ERC)
  - Optional historical fire proximity bonus

Fitness formulation:

\[
\mathcal{J}(x) = Fuel \times Weather \times Slope \times (1 + w_h e^{-d})
\]

---

## 📊 Results
- GA consistently converges to high-risk wildfire zones
- Predictive behavior closely matches Random Forest baseline
- Physics-only variant still identifies ignition regions
- Demonstrates feasibility for disconnected, low-compute environments

<img src="images/FeatureImportance.png" width="600"/>

---

## 📁 Repository Structure
.
├── Term_Project.ipynb # Main end-to-end modeling pipeline (start here)
├── ndvi.ipynb # NDVI-based fuel feature extraction
├── DEM.ipynb # Terrain slope and elevation feature engineering
├── data/ # Processed datasets with NDVI & DEM features
├── images/ # Figures and result visualizations
├── poster/ # Academic poster (PDF)
└── requirements.txt


---

## 🛠️ Setup & Usage

Install dependencies:
```bash
pip install -r requirements.txt
```
Run Term_Project.ipynb to reproduce experiments and GA search behavior.



---

## 🔗 Data Sources
Raw datasets are not included due to size and licensing constraints.
- US Wildfire Dataset (2014–2025):
https://www.kaggle.com/datasets/firecastrl/us-wildfire-dataset
- MODIS NDVI via Google Earth Engine
- SRTM DEM for terrain elevation and slope
Processed datasets are available in the data/ directory.



---

## 📌 Applications
- Autonomous wildfire scouting
- UAV / drone swarm deployment
- Risk-aware navigation in dynamic environments
- Active sensing under bandwidth constraints



---

## 👤 Author
Adit Dhall
MS Artificial Intelligence
📧 ad6449@rit.edu
