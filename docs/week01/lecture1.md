# Lecture 1

## Textbook
- **Book:** Osvaldo Martin, *Bayesian Analysis with Python* (2024), Packt Publishing  
- **Access link:** [Access link](https://drive.google.com/file/d/1Y4V95w5-eUT2ufC85Rk-1jIccm4hh_St/view?usp=sharing)

- **Chapter:** —
- **Sections:** —

---
## Notes

### 1. Purpose of the Lecture

This lecture establishes the foundational setup required for the course. The objectives are to:

- Introduce the primary textbook used throughout the semester
- Define the computational environment used in the course
- Install and verify the PyMC probabilistic programming library
- Prepare students for Bayesian modeling workflows introduced in later lectures

This lecture is primarily preparatory and practical, ensuring that all students begin the course with a consistent and reproducible computational environment.


---

### 2. Course Assessment Structure

The assessment components and their respective weights for the course are summarized below.

| Component      | Count (Min–Max) | Weight (%) |
|---------------|------------------|------------|
| Quizzes       | 4 – 8            | 5          |
| Assignments   | 4 – 8            | 15         |
| Sessional 1   | 1                | 15         |
| Sessional 2   | 1                | 15         |
| Final Exam    | 1                | 50         |
| **Total**     |                  | **100**    |

---

### 2. Python Environment Overview

The following configuration is recommended for the course:

- **Python version:** 3.12.5  
- **Environment manager:** Conda  
- **Conda version:** 25.1.1  
- **Package channel:** conda-forge  
- **Primary library:** PyMC  

A dedicated Conda environment is required to avoid dependency conflicts and ensure reproducibility across platforms.

---

### 3. Environment Setup

#### 3.1 Installing Conda

If Conda is not already installed, choose one of the following:

- **Miniconda (recommended):**  
  https://docs.conda.io/en/latest/miniconda.html

- **Anaconda:**  
  https://www.anaconda.com/products/distribution

After installation, open:
- **Windows:** Anaconda Prompt  
- **Linux/macOS:** Terminal

---

#### 3.2 Creating and Activating a Conda Environment

```bash
conda create -n pymc_env python=3.12.5
```

```bash
conda activate pymc_env
```

---

#### 3.3 Updating Conda (Recommended)

```bash
conda update -n base -c defaults conda
```

---

#### 3.4 Installing PyMC

```bash
conda install -c conda-forge pymc
```

---

#### 3.5 Optional: Installing ArviZ

```bash
conda install -c conda-forge arviz
```

---

#### 3.6 Optional: Installing JupyterLab

```bash
conda install -c conda-forge jupyterlab
```

```bash
jupyter lab
```

---

### 4. Verifying the Installation

```bash
python
```

```python
import pymc as pm
import arviz as az
import numpy as np

print(pm.__version__)
print(az.__version__)
```

---

### 5. Minimal PyMC Test Model

```python
import pymc as pm

with pm.Model():
    p = pm.Beta("p", alpha=1, beta=1)
    y = pm.Bernoulli("y", p=p, observed=[1, 0, 1, 1, 0])
    trace = pm.sample(1000, tune=1000, progressbar=False)
```

---

### 6. Common Issues to Avoid

- Installing PyMC using pip in the base environment
- Mixing pip and conda for core scientific libraries
- Installing unnecessary system compilers or MSYS2

---

### 7. Key Takeaways

- Always use conda-forge
- Always create a dedicated Conda environment
- No compiler installation is required
- PyMC works reliably on major operating systems

---

## Resources
- **Slides [will be availble soon] (PDF/PPT):** —
- **Notebook** [Download lecture notebook](notebooks/lecture1.ipynb)
- **Dataset [N/A]:** 
<!-- - [Download dataset](datasets/dataset1.csv) -->

