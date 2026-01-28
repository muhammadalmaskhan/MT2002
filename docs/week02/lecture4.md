# Lecture 4

## Notes

### Focus
We study how Bayesian inference changes with:
- Data size (small vs large)
- Prior strength (weak vs strong)

### Single-parameter inference (Beta–Bernoulli)

**Data**
- True probability: `p = 0.7`
- Small sample: `size = 10`
- Large sample: `size = 1000`

**Model**
- Likelihood: Bernoulli
- Parameter: `p`
- Prior: Beta(`alpha`, `beta`)
  - Weak prior: e.g., Beta(1, 1)
  - Strong prior: e.g., larger `alpha`, `beta`

### Results (four cases)

1) **Small data + weak prior**  
Posterior is wide; results vary more.

2) **Large data + weak prior**  
Posterior concentrates; data dominates.

3) **Small data + strong prior**  
Posterior follows the prior strongly.

4) **Large data + strong prior**  
Posterior becomes data-driven; prior influence decreases.

### Multi-parameter inference (mu, sigma)
We also demonstrate inference for two parameters:
- Data from Cauchy
- Model uses Normal likelihood
- Infer `mu` and `sigma` jointly

Key point: uncertainty in parameters interacts, and more data reduces uncertainty for both.

### Takeaways
- Small data → more uncertainty and more prior sensitivity
- Large data → tighter posterior and less prior sensitivity

## Resources
- Slides (PDF): —
- Slides (PPTX): —
- Notebook (Rendered): Available via site navigation
- Notebook (Download): https://raw.githubusercontent.com/muhammadalmaskhan/MT2002/main/docs/week02/notebooks/lecture4.ipynb
