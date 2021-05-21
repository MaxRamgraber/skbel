SKBEL
==========

Bayesian Eviential Learning - A Prediction-Focused Approach
-----------------------------------------------------------------------------------------
### Introduction

<p align="center">
<img src="/docs/img/evidential.png" height="350">
</p>
<p align="center">
  Figure 1: The concept of BEL. d = predictor (observed data), h = target (parameter of interest), m = model.
<p align="center">

- The idea of BEL is to find a direct relationship between `d` (predictor) and `h` (target) in a reduced dimensional space with machine learning.
- Both `d` and `h` are generated by forward modelling from the same set of prior models `m`.
- Given a new measured predictor `d*`, this relationship is used to infer the posterior probability distribution of the target, without the need for a computationally expensive inversion. 
- The posterior distribution of the target is then sampled and backtransformed from the reduced dimensional space to the original space to predict posterior realizations of `h` given `d*`.
  
### Workflow

#### Forward modeling
- Examples of both `d` and `h` are generated through forward modeling from the same model `m`. Target and predictor are real, multi-dimensional random variables.
#### Pre-processing
- Specific pre-processing is applied to the data if necessary.
#### Dimensionality reduction
- Principal Component Analysis (PCA) is applied to both target and predictor to aggregate the correlated variables into a few independent Principal Components (PC’s).
#### Learning
- Canonical Correlation Analysis (CCA) transforms the two sets into pairs of Canonical Variates (CV’s) independent of each another.
#### Post-processing
- Specific post-processing is applied to the CV's if necessary (such as CV normalization).
#### Posterior distribution inference
- The mean `μ` and covariance `Σ` of the posterior distribution of an unknown target given an observed `d*` can be directly estimated from the CV's distribution.
#### Sampling and back-transformation to the original space
- The posterior distribution is sampled to obtain realizations of `h` in canonical space, successively back-transformed to the original space.

<p align="center">
<img src="/docs/img/img.png" height="500">
</p>
<p align="center">
  Figure 2: Typical BEL worflow.
<p align="center">
 
Example
-----------------------------------------------------------------------------------------


