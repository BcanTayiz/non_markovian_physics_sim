# Non-Markovian Physics Simulation & System Identification Testbed

An interactive, browser-based experimental lab exploring **non-Markovian lattice dynamics**, **recursive memory kernels**, and **real-time online system identification** using **p5.js**.

---

## 🔬 Overview

Standard physical simulations typically assume Markovian behavior, where future states depend solely on the present. However, complex physical and biological media exhibit history-dependent (non-Markovian) phenomena. 

This project implements a discretized 2D grid coupled with recursive temporal memory ($\mathcal{O}(1)$ updates) and active particle agents. It pits two competing observer architectures against each other in real time to test whether an artificial agent can dynamically discover hidden physical laws ($\alpha, \beta$) purely through prediction error minimization.

---

## 🚀 Key Features

* **Recursive Memory Kernel Framework:** Implements a discrete Generalized Langevin Equation (GLE) combining spatial Laplacian diffusion with a recursive memory field ($M_{t+1} = \alpha M_t + s_t$).
* **Active Particle Agents:** Stochastic particles that navigate the grid, inject energy, and drive the system into non-equilibrium steady states.
* **Competing Observers:**
  * *Markovian Observer:* Naive, memoryless baseline ($\alpha = 0$).
  * *Memory-Augmented Observer:* Adaptive model that learns hidden memory retention ($\alpha$) and coupling ($\beta$) coefficients via **Online Gradient Descent**.
* **Real-Time Telemetry HUD & Oscilloscope:** Live tracking of Mean Squared Error (MSE), parameter convergence, Non-Markovianity Index, and characteristic Memory Horizon ($\tau$).
* **Automated Scientific Interpreter (Verdict Engine):** An embedded diagnostic engine that analyzes telemetry in real time and classifies system regimes (e.g., *Strong Non-Markovian*, *Short-Memory Noise Trap*, *Markovian*, or *Transient Learning*).
* **Stochastic Jitter Suppression:** Uses an **Exponential Moving Average (EMA)** filter on parameter updates to maintain stability in driven non-equilibrium environments.

---

## 📂 Project Structure

```text

├── LICENSE.txt
├── README.md
├── cellular_automata_experiments/
│   ├── motivation.md
│   ├── javascript_simulation_code_walkthrough.md
│   ├── simulation/
│   │   ├── index.html
│   │   ├── sketch.js
├── method/
│   ├── article/
│   │   ├── article.pdf
│   │   
├── tutorial/
│   ├── from_zero.md
│   ├── intro.ipynb
│   ├── mori_zwanzig_and_memory_kernels_arxiv_guide.md
│   ├── resources_to_check.md
```

---

## 🛠️ Getting Started

To run the simulation locally:

1. Clone or download this repository.
2. Ensure both `index.html` and `sketch.js` are in the same folder.
3. Open `index.html` in any modern web browser (or run a local server like Live Server in VS Code).

---

## 🎮 Interactive Controls & Scenarios

Use the control buttons at the top of the viewport to switch physical regimes instantly:
* **Scenario 1: Short Memory ($\alpha = 0.40$):** Tests weak memory coupling.
* **Scenario 2: Long Memory ($\alpha = 0.90$):** Tests strong historical dominance.
* **Scenario 3: Pure Markovian ($\alpha = 0.00$):** Tests baseline memoryless diffusion.
* **Mouse Click:** Click anywhere on the grid to inject an energy pulse and observe observer adaptation.

---

## 📊 Core Empirical Insights

Through rigorous telemetry analysis, the testbed uncovers three foundational principles:

1. **History Dominance:** In long-memory regimes ($\alpha = 0.90$), memory-augmented observers vastly outperform Markovian baselines, proving that historical trajectories are critical for accurate prediction.
2. **The Noise Trap (Occam's Razor):** In short-memory regimes ($\alpha = 0.40$), complex memory models underperform relative to naive Markovian models because extra temporal parameters inject estimation variance and noise rather than predictive value.
3. **Online Parameter Recovery:** Observers successfully track and adapt to shifting physical parameters on the fly via gradient descent without requiring offline batch training.

---

## 📜 License

This project is open-source and available for research, educational, and experimental purposes.

---

## 📄 Citation

If you use this framework or code in your research, please cite our paper draft:

```bibtex
@software{non_markovian_physics_sim,
  title={Non-Markovian Physics Simulation & System Identification Testbed},
  author={Barış Can Tayiz},
  year={2026},
  publisher={Zenodo},
  doi={10.5281/zenodo.24211999},
  url={https://doi.org/10.5281/zenodo.24211999}
}
