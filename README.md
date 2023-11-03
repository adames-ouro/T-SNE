# T-distributed stochastic neighbor embedding
---

## Goal

Is a probabilistic approach based on SNE, used to project data from high dimensions to lower ones while retaining local and preserving global structures.

## Overview

- Is an manifold learning, non-linear, unsupervised learning method.

- Tries to preserve local structure of data.

- Involves Hyperparameters.

- Not affected by outliers.

- Is a randomized, stochastic, method.

- For mixed and categorical data use a distances that considers both, numerica and categorical impact, for example Gower’s distance.

### Formulas used:
- **Pairwise affinities in high-dimensional space**: 
    ![Pairwise affinities high-dimensional formula](https://latex.codecogs.com/svg.latex?p_{ij}%20=%20\frac{\exp(-||x_i%20-%20x_j||^2%20/%202\sigma^2)}{\sum_{k%20\neq%20l}%20\exp(-||x_k%20-%20x_l||^2%20/%202\sigma^2))

- **Pairwise affinities in low-dimensional space**: 
    ![Pairwise affinities low-dimensional formula](https://latex.codecogs.com/svg.latex?q_{ij}%20=%20\frac{(1%20+%20||y_i%20-%20y_j||^2)^{-1}}{\sum_{k%20\neq%20l}%20(1%20+%20||y_k%20-%20y_l||^2)^{-1})

- **Cost function (Kullback-Leibler divergence)**: 
    ![Kullback-Leibler divergence formula](https://latex.codecogs.com/svg.latex?C%20=%20\sum_{i%20\neq%20j}%20p_{ij}%20\log%20\frac{p_{ij}}{q_{ij}})

---

## Steps for the Algorithm

**Step 1:Standarize data. (continuos variables)***

- Data with mean = 0, standard deviation = 1
  
***Step 2: Compute pairwise distances***

- Distance matrix.

***Step 3: Convert distances in high space into normal distribution conditional probabilities***

- Normal conditional probability matrix using distance matrix.

***Step 4: Updates the probabilities by making them symmetrical***

- Average of symetrical probabilities.

***Step 5: Choose a random lower dimension projection***

- Random initial projection.

***Step 6: Compute distances for lower dimension data***

- Distance matrix for initial projection.

***Step 7: Convert distances in low space into t distibuted conditional probabilities***

- t conditional probability matrix using distance matrix of low space projection.

***Step 8: Compute gradient for optimal direction***

- Find the direction where similarity matrices in original and lower dimensions are less different.

***Step 9: Update the solution of lower dimension***

- After each iteration, update new values of projection coordinates, distances and gradient.

***Step 10: if iteration exceeds max iter parameter, stop, else keep iterating steps 6-9***

- Repeat until done or stops.

---

> **Note:** t-SNE is computationally intensive and can be sensitive to hyperparameters. It's crucial to try different parameter values and interpret the visualizations with caution.
