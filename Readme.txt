========================================================================
README: Chapter 2 - Discrete-Time Multistate Logistic Models with Frailties
========================================================================

1. OVERVIEW
This repository contains the computational implementation for Chapter 2 
of the PhD thesis. One of the primary focuses is the estimation of model 
parameters in LLink models.

A core component is the implementation of marginal likelihood 
estimations where frailties (random intercepts) are integrated out 
using a computationally efficient, vectorised Gauss-Hermite Quadrature 
(GHQ) approach.

2. KEY IMPLEMENTATIONS
• Time-Independent Frailty: Random intercept models where frailties 
  are integrated out via vectorised GHQ.
• Time-Dependent Extensions: Linear and Piecewise time-=-dependent 
  frailty implementations also (including vectorised 2D GHQ).
• Alternative Estimation: EM-type algorithms implemented for 
  benchmark comparisons against GHQ.
• Statistical Testing: Parametric bootstrap Likelihood Ratio Test 
  (LRT) framework for variance components.
• Implementation of the proposed OMCC as well as D&C methods for 
  multistate classification.

3. NOTEBOOK STRUCTURE
• Section 1: Time-Independent Frailty & Simulation Study. 
  Focus: Vectorised GHQ marginal log-likelihood, EM benchmarking, 
  and parameter recovery experiments.
• Section 2: Time-Dependent Frailty Extensions. 
  Focus: 2D GHQ for linear and piecewise frailty likelihoods.
• Section 3: Parametric Bootstrap RLRT. 
  Focus: Bootstrapped distribution construction and p-value computation.
• Section 4: Implementation of OMCC and D&C with use cases

4. DATA & REPRODUCIBILITY
• Original Data: Microfinance data is excluded due to confidentiality.
• Synthetic Data: The notebook includes codes to generate synthetic 
  datasets. These are used to verify the estimation accuracy of the 
  GHQ and EM algorithms as reported in the thesis/paper.
• Requirements: Python 3.x (numpy, pandas, scipy, sklearn, joblib, 
  statsmodels, KTBoost).

5. EXECUTION INSTRUCTIONS
1) Clone the repository.
2) Install dependencies (if not available): 
   pip install numpy pandas scipy scikit-learn joblib statsmodels KTBoost
3) Open 'Chapter_2_codes_final.ipynb' in Jupyter.
4) Run cells sequentially. 

6. CITATION & USAGE
If you use this code or the methodologies described herein, please 
cite the following work:

Koffi, C. H. A., Djeundje, V. B., & Pamen, O. M. (2024). 
Quantifying socio-temporal effects of loan delinquency drivers 
in microfinance. arXiv preprint arXiv:2410.13100.
Link: https://arxiv.org/abs/2410.13100

7. COMPUTATIONAL NOTES
• Vectorisation: The GHQ implementation is vectorised to optimise 
  performance for large-scale simulation studies.
• Accuracy: The 'n_quad' parameter controls the number of quadrature 
  points; higher values increase integration precision.
========================================================================