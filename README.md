# Optimal Learning Protocols: Code and Simulations

This repository contains the code used in the paper:

> **A statistical physics framework for optimal learning**  
> Francesca Mignacco, Francesco Mori  
> [arXiv:2507.07907](https://arxiv.org/abs/2507.07907)

We provide code and simulations for analyzing optimal learning protocols using a theoretical framework that combines tools from statistical physics and optimal control theory. The results include optimal curricula, dropout schedules, and noise schedules in denoising autoencoders.

---

## Overview

Learning dynamics are described via a closed set of ODEs for order parameters in two-layer neural networks trained with online stochastic gradient descent (SGD). Training protocols are optimized using control-theoretic tools to minimize generalization error.

The repository includes simulations for three representative scenarios:

- **Curriculum learning**: optimal task ordering in student–teacher perceptrons.
- **Dropout regularization**: optimal schedules for node activation in two-layer soft-committee machines.
- **Denoising autoencoders (DAEs)**: optimal noise and data augmentation schedules in shallow DAEs, including applications to MNIST.

---

## Repository Structure

```
├── curriculum/
│   ├── curriculum.ipynb               # Optimal schedule (indirect method: Pontryagin)
│   └── simulations_curriculum.ipynb   # Validation of ODEs via numerical experiments
│
├── dropout/
│   ├── dropout.ipynb                  # Optimal schedule (direct method via CasADi)
│   └── simulations_dropout.ipynb      # Validation of ODEs via numerical experiments
│
├── DAE/
│   ├── DAE.ipynb                      # Optimal schedule (direct method via CasADi)
│   ├── simulations_DAE.ipynb          # Validation of ODEs via numerical experiments
│   └── MNIST/
│       ├── MNIST_simulations_DAE.ipynb
│       ├── MNIST_b_trained.ipynb
│       └── data/
│           ├── schedule_Delta=0.1_Treal=1_eta=5.pickle
│           ├── schedule_Delta=0.2_Treal=1_eta=5.pickle
│           ├── schedule_Delta=0.3_Treal=1_eta=5.pickle
│           └── schedule_Delta=0.4_Treal=1_eta=5.pickle
│
├── README.md
└── requirements.txt  
```

---


Each notebook is self-contained and can be executed top to bottom.

---

## Notebooks Description

- `simulations_*.ipynb`: used to **validate the theoretical ODEs** by comparing them to direct numerical experiments.
- `curriculum.ipynb`: derives optimal training schedules using **indirect optimal control** (Pontryagin's Maximum Principle).
- `dropout.ipynb` and `DAE.ipynb`: derive optimal training schedules using **direct methods via CasADi**.
- `MNIST_simulations_DAE.ipynb` and `MNIST_b_trained.ipynb`: derive and evaluate **optimal denoising schedules for MNIST**.

---


- **Curriculum Learning** → `simulations_curriculum.ipynb`, `curriculum.ipynb`  
- **Dropout Regularization** → `simulations_dropout.ipynb`, `dropout.ipynb`  
- **DAE (Toy model)** → `simulations_DAE.ipynb`, `DAE.ipynb`  
- **DAE (MNIST)** → `MNIST_simulations_DAE.ipynb`, `MNIST_b_trained.ipynb`  
- **Optimal Schedules** → `data/schedules/*.pickle` (used in DAE simulations for MNIST)

---

## 📄 License

This repository is released under the MIT License.
