## 🗺️ PHASE 2 - Mathematics & Statistics for AI

> **Goal:** Understand the math behind what models do - you don't need to derive everything, but you must understand it.

### 2.1 Linear Algebra

**Vectors**
- What a vector is - geometrically and algebraically
- Vector addition, scalar multiplication
- Dot product - geometric intuition (similarity, projection)
- Vector magnitude / norm (`L1`, `L2`, `Lp` norms)
- Unit vectors and normalization
- Cosine similarity - how embeddings work
- Orthogonality

**Matrices**
- Matrix operations: addition, multiplication, transpose
- Element-wise vs matrix product
- Identity matrix, inverse matrix
- Determinant - geometric intuition
- Rank of a matrix

**Matrix Operations in ML Context**
- Linear transformations
- Systems of linear equations: `Ax = b`
- Overdetermined systems and least squares
- Trace of a matrix

**Decompositions**
- Eigenvalues and eigenvectors
- Why eigenvalues matter in PCA
- Singular Value Decomposition (SVD) - high-level intuition
- How SVD relates to dimensionality reduction

### 2.2 Calculus

**Derivatives**
- What a derivative is - rate of change, slope
- Power rule, chain rule, product rule
- Derivative of `log`, `exp`, `sigmoid`
- Minima, maxima, saddle points
- Second derivative - concavity, convexity

**Partial Derivatives & Multivariable**
- Partial derivative - rate of change w.r.t. one variable
- Gradient - vector of all partial derivatives
- Gradient points uphill - minimizing means going opposite
- Jacobian matrix
- Hessian matrix

**Chain Rule (Critical for ML)**
- Chain rule for single variable
- Chain rule for multivariable - how backpropagation works
- Computational graphs - forward and backward pass

**Key Functions to Differentiate**
- Sigmoid: `σ(x) = 1/(1+e^-x)` and its derivative
- ReLU and its derivative
- Softmax gradient
- Cross-entropy loss gradient
- MSE loss gradient

### 2.3 Probability & Statistics

**Probability Basics**
- Sample space, events, outcomes
- Joint, marginal, conditional probability
- Independence
- Law of total probability

**Bayes' Theorem**
- Formula: `P(A|B) = P(B|A) * P(A) / P(B)`
- Prior, likelihood, posterior
- Bayesian updating
- Naive Bayes as direct application

**Random Variables & Distributions**
- Discrete vs continuous random variables
- PMF, PDF, CDF
- Expected value, variance, standard deviation
- Covariance and correlation

**Key Distributions**
- Bernoulli, Binomial, Gaussian (Normal), Uniform
- Poisson, Exponential, Multinomial (used in NLP)

**Statistical Concepts**
- Central Limit Theorem
- Law of Large Numbers
- MLE (Maximum Likelihood Estimation)
- MAP (Maximum A Posteriori)
- Entropy, KL Divergence, Cross-entropy

### 2.4 Optimization

**Core Concepts**
- Objective / loss function
- Convex vs non-convex functions
- Local minima vs global minima vs saddle points
- Constrained vs unconstrained optimization

**Gradient Descent**
- Intuition - ball rolling downhill
- Update rule: `θ = θ - α * ∇L(θ)`
- Learning rate - too high vs too low
- Batch GD vs SGD vs Mini-batch

**Optimizers**
- Momentum
- RMSProp
- Adam - combines momentum + RMSProp (most common)
- Learning rate schedules: step decay, cosine annealing, warmup

**Key Challenges**
- Vanishing gradients
- Exploding gradients + gradient clipping
- Saddle points in high dimensions
- Plateau regions

**Regularization**
- L2 regularization (weight decay)
- L1 regularization - promotes sparsity
- Dropout
- Early stopping

### 2.5 Information Theory

- Entropy `H(X) = -Σ p(x) log p(x)`
- Cross-entropy loss - natural loss for classification
- KL Divergence - used in VAEs, distillation, RL
- Mutual information
- Bits vs nats

---

### 📦 Phase 2 Projects

**🟢 Easy: Cosine Similarity Search**
- Implement cosine similarity from scratch using NumPy
- Build a mini semantic search: given a query, find the most similar sentences
- Visualize vector space with matplotlib

**🟡 Medium: Gradient Descent Visualizer**
- Implement gradient descent from scratch for linear regression and logistic regression
- Visualize loss curves, decision boundaries
- Compare SGD vs Adam vs RMSProp convergence
- Stack: Python, NumPy, Matplotlib

**🔴 Hard: Build Your Own Neural Network from Scratch**
- Implement forward pass, backward pass (backprop), weight updates
- Support: Linear, ReLU, Sigmoid, Softmax layers
- Train on MNIST, achieve >95% accuracy
- No PyTorch/TensorFlow - pure NumPy
- Stack: Python, NumPy, Matplotlib

---

