# Dimensionality Reduction

## Why Dimensionality Reduction

1. compress the data
2. speed up learning algorithm

## Data Compression
> Reduce data from higher dimension to lower dimension

Creating a new, lower dimensional feature space, and then creating a new set of samples in that space by projecting the original samples on to the lower-dimensional space. This speeds up learning algorithms.

__Preprocessing__(feature scaling/ mean normalisation):

$\mu$<sub>j</sub> = 1/m $\sum$ 1 -> m \[x<sup>(i)</sup><sub>j</sub>]
Replace x<sup>(i)</sup><sub>j</sub> with x<sub>j</sub> - $\mu$<sub>j</sub>

## Principal Component Analysis (PCA)  

To reduce \( n \) dimensions to \( k \) dimensions:  
Find \( k \) vectors \( u^1, u^2, ..., u^k \in \mathbb{R}^n \) onto which to project the data so as to minimize the projection error.

### Steps  

#### Preprocessing: Mean Normalization & Feature Scaling  
- Compute the mean for each feature:  

    $\mu_j = \frac{1}{m} \sum_{i=1}^{m} x_j^{(i)}$

 - Replace each feature value with:  

    $x_j^{(i)} \leftarrow x_j^{(i)} - \mu_j$

#### Compute Covariance Matrix  

   The covariance matrix \( $\Sigma$ \) is given by:  

   $\Sigma = \frac{1}{m} \sum_{i=1}^{m} (x^{(i)})(x^{(i)})^T$

   where \( $x^{(i)}$ \) represents the \($i^{th}$ \) data sample.

#### Compute Eigenvectors and Eigenvalues
   - Compute the eigenvectors and eigenvalues of \( \Sigma \).  
   - The eigenvectors represent the principal components.  
   - The eigenvalues indicate the variance captured by each principal component.  

#### Select Top \( k \) Principal Components 
   - Choose the top \( k \) eigenvectors corresponding to the largest eigenvalues.  
   - Form the projection matrix \( U_k \) from these top \( k \) eigenvectors.  

#### Project Data Onto Lower-Dimensional Space
   - Transform the original dataset \( X \) into the reduced-dimensional space:  

    $Z = X U_k$

   - Here, \( Z \) is the new representation of the data in \( k \)-dimensional space.  


