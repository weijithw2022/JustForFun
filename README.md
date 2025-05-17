# JustForFun
Repository on where I explore stuff

## Restricted Boltzmann Machine (RBM)

An **RBM** is a generative stochastic neural network that learns a probability distribution over its input data. It consists of:
- A **visible layer** (input data)
- A **hidden layer** (latent features)
- No intra-layer connections

---

### 🔄 Training with Contrastive Divergence (CD)

RBMs are trained using **Contrastive Divergence**, which approximates the gradient of the log-likelihood. The process:

1. **Positive Phase**:  
   Compute hidden activations from the real input.

2. **Gibbs Sampling**:  
   Alternate between sampling hidden and visible layers multiple times (typically 1–10 steps).

3. **Negative Phase**:  
   Compute hidden activations from the reconstructed input.

4. **Weight Updates**:  
   Adjust weights and biases using the difference between the positive and negative phases.

---

### ♻️ Gibbs Sampling

Gibbs sampling is used to approximate the data distribution by repeatedly sampling:
- Hidden units given visible units
- Visible units given hidden units

This allows the RBM to reconstruct inputs and learn hidden representations.

---

### 🧪 Loss

The model is trained to minimize the reconstruction error (e.g. Mean Absolute Error) between the original and reconstructed inputs, computed **only on known data**.
