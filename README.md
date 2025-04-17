# 📘 SmileAF – Arbitrage-Free Volatility Surface Construction

This project implements an arbitrage-free smile interpolator (SmileAF) as part of the Numerical Methods in Finance coursework. It includes local volatility model construction, PDE-based European option pricing, and comparison against cubic spline interpolation methods.

---

## 🎯 Objectives

- ✅ Implement arbitrage-free smile interpolator: **SmileAF**
- ✅ Construct local volatility surfaces from interpolated smiles
- ✅ Price European options via **PDE solver** using local volatility
- ✅ Compare accuracy against cubic spline-based volatility interpolation
- ✅ Optimize algorithms for speed and stability (parallelization, banded solvers)

---

## ⚙️ Core Methods

- **Quadratic Programming** to enforce:
  - Monotonicity
  - Convexity (butterfly arbitrage-free)
  - Probability density integration = 1
  - Bid-ask aware pricing (future improvement)
- **SABR implied vol fits** used to build synthetic test data
- **Tridiagonal PDE solver** using `solve_banded` for speed and memory efficiency
- **Parallelized calibration and volatility construction** with `ThreadPoolExecutor`

---

## 📊 Key Features

- Fully arbitrage-free smile interpolator using convex optimization
- Local volatility grid computed via Dupire’s formula
- Fast PDE pricing for vanilla options under local vol surface
- Visualization:
  - 3D implied/local volatility surfaces
  - 2D ATM term structure and delta slices
- Calibration report showing error comparison between cubic spline and SmileAF

---

## 🧠 Improvements

- Adaptive smoothing penalties on the implied density
- Parametric tail extrapolation to handle deep OTM/ITM options
- Bid-ask-aware interpolation for more realistic modeling

---

## 📂 Project Files

- 📓 [SmileAF Implementation](./group_project.ipynb)

---

## 👤 Contribution

I contributed to the optimization and enhancement of the SmileAF interpolation framework and PDE pricing, focusing on efficient solver design and numerical stability improvements.

---

## 📎 Reference

- Fengler (2009), *Arbitrage-Free Smoothing of the Implied Volatility Surface*, Quantitative Finance.
