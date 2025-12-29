# 🎄 Santa 2025 — Gold Medal Solution  
**Irregular Polygon Packing via Heuristic Optimization**

[![Kaggle Competition](https://img.shields.io/badge/Kaggle-Santa%202025-blue?logo=kaggle)](https://www.kaggle.com/)
[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)
[![Optimization](https://img.shields.io/badge/Focus-Optimization-critical)](#)
[![Status](https://img.shields.io/badge/Status-Post--Competition-success)](#)

---

## 🏆 Competition Result

**Final Placement:** 🥇 *Gold Medal*  
**Leaderboard Rank:** `XX / XXXX` (Top `X%`)  
**Best Score:** `0.XXXXX`  
**Runtime per submission:** ~`XX` minutes

> This solution achieved a **top-tier ranking** in a large-scale Kaggle optimization challenge involving NP-hard geometric packing.

---

## 📌 Project Summary (Portfolio Version)

This project solves an **NP-hard 2D irregular polygon packing problem** using a hybrid of **greedy heuristics, rotation optimization, and simulated annealing**.

The goal was to pack up to **200 irregular, non-rectangular polygons** into the smallest possible square while avoiding overlaps—balancing **solution quality**, **runtime**, and **search stability**.

**Core skills demonstrated:**
- Heuristic & metaheuristic optimization
- Computational geometry
- Simulated annealing design
- Large-scale experimentation & tuning
- Writing robust, competition-grade Python

---

## 🧠 Technical Approach

### 1️⃣ Greedy Initialization
- Polygons sorted by descending area
- Multiple rotation angles tested per object
- Placement chosen to minimize bounding square growth

This provides a fast, strong baseline while reducing fragmentation early.

---

### 2️⃣ Rotation-Aware Simulated Annealing
Used to refine layouts and escape local minima.

**Neighborhood moves:**
- Local translation
- Small-angle rotation
- Occasional polygon swaps

**Acceptance function:**
P(accept) = exp(-Δscore / T)


**Why SA worked well here:**
- Highly non-convex search space
- Many near-feasible local minima
- Continuous + discrete decision variables

---

### 3️⃣ Geometry & Performance
- Accurate collision detection using **Shapely**
- Efficient bounding square tracking
- Smart candidate placement generation near existing polygons

---

## 🧩 System Design
Config

├── Temperature schedule

├── Rotation resolution

└── Iteration limits

TreePacker

├── greedy_placement()

├── simulated_annealing()

└── geometry helpers

Execution

├── Multi-strategy runs

├── Score tracking

└── Submission export

---

## 📊 Results Visualization

### Example Packing Output
<p align="center">
  <img src="assets/example_solution.png" width="600">
</p>

> Each tree is rotated and placed without overlap; the enclosing square defines the score.

---

## 📈 Performance Breakdown

| Method | Percentile | Notes |
|------|------------|-------|
| Greedy only | ~35% | Fast baseline |
| Greedy + SA | ~60% | Strong general solution |
| Multi-run SA | **Top tier** | Final submission |

---

## 🧪 Validation & Reliability

- Explicit overlap checks between all polygons
- Score recomputation for verification
- Visual debugging to catch geometric edge cases

---

## 🔬 What I’d Improve Next

- No-Fit Polygon (NFP) computation
- Hybrid Genetic Algorithm + SA
- Parallel multi-start optimization
- ML-guided initial rotations

---

## 🛠️ Tech Stack

- **Python**
- **NumPy**
- **Shapely**
- **Matplotlib**
- **Kaggle Notebooks**


---

## 🏁 Final Notes

This repository is shared **post-competition** for educational and portfolio purposes.  
Feel free to explore, fork, or adapt ideas for related optimization problems.

If you’re working on geometric optimization or heuristic search, I’d be happy to connect.
