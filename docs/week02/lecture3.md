# Lecture 3

## Notes  
### Week 2: PyMC Distributions, Prior Predictive, and a Coin Flip Model

---

### Learning Goals
- Understand common PyMC distributions (discrete and continuous)
- Learn prior predictive sampling
- Build a simple Bayesian coin-flip model

---

## Why Do We Need Distributions?

Distributions help us model uncertainty in Bayesian modeling:

- **Prior**: belief about unknown parameters before data  
- **Likelihood**: how data is generated  
- **Posterior**: updated belief after data  

Bayesian update rule:

$$
Posterior \propto Likelihood \times Prior
$$

---

## PyMC Distributions (Quick Reference)

### Discrete Distributions

| Distribution | PyMC Name | Parameters | Models |
|---|---|---|---|
| Bernoulli | `pm.Bernoulli(p=...)` | `p`: success probability | One 0/1 outcome |
| Binomial | `pm.Binomial(n=..., p=...)` | `n`: trials, `p`: success prob | Successes in `n` trials |
| Categorical | `pm.Categorical(p=...)` | `p`: category probs | One of K categories |
| Multinomial | `pm.Multinomial(n=..., p=...)` | `n`: total, `p`: probs | Counts across K categories |
| Poisson | `pm.Poisson(mu=...)` | `mu`: rate | Count per interval |
| ZeroInflatedPoisson | `pm.ZeroInflatedPoisson(psi=..., mu=...)` | `psi`: extra zeros, `mu`: rate | Counts with extra zeros |

---

### Continuous Distributions

| Distribution | PyMC Name | Parameters | Models |
|---|---|---|---|
| Beta | `pm.Beta(alpha=..., beta=...)` | `alpha`, `beta`: shape | Probabilities in (0,1) |
| Normal | `pm.Normal(mu=..., sigma=...)` | `mu`: mean, `sigma`: std dev | Bell-shaped real values |
| HalfNormal | `pm.HalfNormal(sigma=...)` | `sigma`: scale | Positive-only values |
| Cauchy | `pm.Cauchy(alpha=..., beta=...)` | `alpha`: location, `beta`: scale | Heavy-tailed real values |
| HalfCauchy | `pm.HalfCauchy(beta=...)` | `beta`: scale | Positive heavy-tailed |
| Uniform | `pm.Uniform(lower=..., upper=...)` | bounds | Flat in a range |
| StudentT | `pm.StudentT(nu=..., mu=..., sigma=...)` | `nu`: df, `mu`: mean, `sigma`: std dev | Robust bell-shape |

---

## Prior Predictive Sampling

Used to check if your **priors make sense** before observing data.

Steps:

1. Define priors  
2. Sample prior predictive draws  
3. Plot and verify results  

---

## Coin Flip Model (Beta + Bernoulli)

Convert outcomes:
- Heads → `1`
- Tails → `0`

Model:

$$
p \sim Beta(1, 5)
$$

$$
y_i \sim Bernoulli(p)
$$

Goal: estimate the probability of heads `p` from observed flips.

### Resources
- Slides: —
- Notebook: [visit](notebooks/lecture3.ipynb)
