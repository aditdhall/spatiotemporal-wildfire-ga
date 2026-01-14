# Spatiotemporal Wildfire Risk Prediction using Evolutionary Algorithms

This project presents a **physics-informed Genetic Algorithm (GA)** for efficient spatiotemporal wildfire risk prediction, designed for **autonomous drone and swarm-based scouting** in compute- and bandwidth-constrained environments.

Unlike traditional grid-based or deep learning approaches that require exhaustive scanning, this method actively searches high-risk regions using local environmental signals.

---

## 🚀 Key Contributions
- Physics-guided **Genetic Algorithm** for wildfire risk localization
- Achieves **<1% computational cost** compared to exhaustive grid scanning
- Robust to **climate regime shifts** (validated via physics-only ablation)
- Suitable for **real-time autonomous deployment**

---

## 🧠 Method Overview
### Baseline
- Random Forest classifier trained on विपक्ष on historical wildfire data
- Generates ground-truth wildfire risk maps

### Heuristic Model
- GA fitness function combines:
  - Vegetation density (NDVI / fuel)
  - Terrain slope & elevation
  - Weather risk indices (ERC)
  - Optional historical fire bonus

Fitness formulation:
\[
\mathcal{J}(x) = Fuel \times Weather \times Slope \times (1 + w_h e^{-d})
\]

---

## 📊 Results
- GA consistently converges on high-risk fire zones
- Ablation study confirms effectiveness using physics alone
- Demonstrates feasibility for disconnected environments

<img src="images/FeatureImportance.png" width="600">

---

## 📁 Repository Structure
.
├── Term_Project.ipynb # Main pipeline
├── ndvi.ipynb # Fuel extraction
├── DEM.ipynb # Terrain processing
├── data/ # Processed datasets
├── images/ # Result figures
├── poster/ # Academic poster
└── requirements.txt


---

## 🛠️ Setup
```bash
pip install -r requirements.txt

