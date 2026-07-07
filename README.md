## KAN Physics Recovery: Damped Harmonic Oscillator

**Project status:** `In progress` (Weeks 1–3 of internship)

This repository contains my practical work on Kolmogorov–Arnold Networks (KAN). 
The main goal is to demonstrate the **interpretability** of KAN by recovering the analytical form of a physical law (Newton's second law for a damped oscillator) from synthetic observational data.

## Objective

- Generate synthetic data for the equation: `a = -(k/m)*x - (c/m)*v` using numerical integration (`scipy.integrate.solve_ivp`).
- Train a small KAN model and compare its performance with a classical MLP with a comparable number of parameters.
- Use the built-in `auto_symbolic` feature in `pykan` to extract the exact formula and verify the discovered coefficients against true physical constants.

## Repository Structure

```text
├── notes/                  # Personal notes, ideas, and questions during the internship
├── papers/                 # Original PDFs of referenced scientific articles
├── notebooks/              # Jupyter/Google Colab notebooks with all experiments
├── reports/                # Final report and presentation slides (Week 3)
├── .gitignore              # Ignored files (caches, envs, datasets)
├── requirements.txt        # Fixed package versions for reproducibility
└── README.md               # Project overview (this file)
```

## Setup
To reproduce the environment, clone this repository and install the dependencies:

```text
pip install -r requirements.txt
```
Note: requirements.txt will be finalized after fixing the exact pykan version during Week 1.

## Methodology
1. Data Generation:
Trajectories are generated using solve_ivp with varied initial conditions and damping constants (k, c) to cover different physical environments. Gaussian noise (1–5%) is added to simulate real measurements.
2. Models:
A KAN with shape [2, 1] (or [2, 2, 1]) is compared to an MLP with a similar number of trainable parameters (±30%). Training and validation losses are tracked.
3. Symbolic Regression:
The trained KAN is processed via model.auto_symbolic() to retrieve the mathematical expression. Recovered coefficients are compared with the true -k/m and -c/m.

## Preliminary Results
(To be updated after Week 2 experiments)

## Timeline
Week 1: Literature review (reading papers, understanding KAN vs MLP) and writing a mini-survey.

Week 2: Experiments: data generation, training, symbolic regression, and extracting the formula.

Week 3: Finalizing the report, preparing the presentation, and optional PIKAN bonus.

## Author
Ksenia Andreeva
Student

## Acknowledgments
Supervisor: Viktor Kuzminov 

Institution: [Name of your university/organization]
