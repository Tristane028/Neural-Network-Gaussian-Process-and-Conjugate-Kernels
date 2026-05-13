# Neural Network Gaussian Process and Conjugate Kernels

**Authors:** Tristan Endo, Professor Alexander Cloninger  
**Institution:** University of California, San Diego  
**Year:** 2026
**[NNGPCK Paper (PDF)](NNGP_paper.pdf)**

## Overview

This project examines commonly used activation functions on neural networks. We derive closed-form conjugate kernels for the respective activation functions and experiment on finite-width networks. The goal of this experiment was to see what happens when we increase network width and how the network kernels behave when such a condition is met.

The framework we use is the Neural Network Gaussian Process (NNGP), where a fully connected neural network with random Gaussian weights converges to a Gaussian process as its width goes to infinity. The covariance of this process is captured by a kernel function — called the **conjugate kernel** — which depends on the activation function, depth, and weight variance.

## Contents

- Derivation of closed-form conjugate kernels for **ReLU**, **erf**, and **tanh** activation functions
- Analysis of kernel recursion and how input correlations evolve layer by layer
- Study of kernel degeneracy, fixed points, and expressivity as depth increases
- Experiments on finite-width networks to see how they compare to the infinite-width NNGP predictions

## Key Results

- **ReLU** networks show kernel degeneracy — correlations increase toward 1 with depth, and the kernel becomes nearly constant across inputs.
- **erf** and **tanh** networks decorrelate inputs across depth, which avoids degeneracy and keeps the network more expressive.
- Larger weight variance (σ²_w) speeds up degeneracy, while input normalization helps stabilize the kernel.
- As we increase network width, the finite-width correlation trajectories get closer to the deterministic recursion predicted by NNGP theory.

## Background

The NNGP framework goes back to Neal (1994), who showed that single-layer networks with random weights converge to Gaussian processes in the infinite-width limit. Lee et al. (2018) extended this to deep networks, which is the recursive kernel formulation we build on here.

## References

- Jaehoon Lee et al. *Deep Neural Networks as Gaussian Processes.* 2018.
- Christopher K.I. Williams. *Computing with Infinite Networks.* NeurIPS, 1997.
- Youngmin Cho and Lawrence K. Saul. *Kernel Methods for Deep Learning.* NeurIPS, 2009.
- Radford M. Neal. *Bayesian Learning for Neural Networks.* PhD thesis, University of Toronto, 1994.
