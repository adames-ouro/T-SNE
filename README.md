# T-distributed stochastic neighbor embedding

## Goal

Is a probabilistic approach based on SNE, used to project data from high dimensions to lower ones while retaining local and preserving global structures.

## Overview

- Is an manifold learning, non-linear, unsupervised learning method.

- Tries to preserve local structure of data.

- Involves Hyperparameters.

- Not affected by outliers.

- Is a randomized, stochastic, method.

- For mixed and categorical data use a distances that considers both, numerica and categorical impact, for example Gower’s distance.

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
