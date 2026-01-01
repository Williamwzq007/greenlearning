# Reproducibility Report: GreenLearning (Laplace Example)

This document records the reproduction of the **Laplace equation benchmark** from the GreenLearning repository, following the authors’ released code and datasets without modification to the core implementation.

---

## Environment

- OS: Windows 10
- Python: 3.13
- Virtual environment: `paper_venv`
- Deep learning backend: TensorFlow 2 (via compatibility mode used in the repository)

The environment was set up following the repository requirements.  
No changes were made to the GreenLearning library code.

---

## Dataset

- Dataset used: `laplace.mat`
- Location: `examples/datasets/`
- Source: provided directly in the GreenLearning repository (authors’ released datasets)

The dataset was used as-is, without preprocessing or modification.

---

## Experiment Description

The Laplace example was run using the **default model configuration and training pipeline** provided by the repository.

Specifically:
- The Green’s function and homogeneous solution networks were constructed using the standard rational neural network architecture defined in the codebase.
- Training was performed using the authors’ implementation of the GreenLearning method.
- No hyperparameters were changed.

The experiment was executed via the provided `main.py` workflow.

---

## Results

The trained model successfully reproduced the qualitative and quantitative behavior reported in the paper:

- The learned Green’s function closely matches the exact Green’s function in global structure and boundary behavior.
- The relative error reported by the code is on the order of **10⁻³** (approximately 2.5 × 10⁻³ in a representative run).
- The homogeneous solution is numerically close to zero, consistent with the theoretical expectation for the Laplace equation with Dirichlet boundary conditions.

Representative visualizations (exact vs. learned Green’s function, training solutions, and homogeneous solution) were generated and saved during the run.

---

## Notes

- Due to random initialization and non-deterministic behavior in deep learning backends, the reproduced figures are not expected to be pixel-wise identical to those shown in the paper, but they are consistent in structure and error magnitude.
- This reproduction focuses on verifying that the released code and dataset produce the expected results, rather than extending or modifying the method.

---

## Summary

This reproduction confirms that the GreenLearning implementation can successfully recover the Green’s function for the Laplace operator using the authors’ released code and datasets, achieving errors consistent with those reported in the original work.

