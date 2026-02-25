# Assignment #4

## Question 1: BPTT and the Vanishing/Exploding Gradient

Consider an RNN unrolled for $T=3$ time steps. To understand the effect of weight multiplication on gradient stability, we assume the hidden layer has **2 nodes**, while the input and output remain scalars.

* **Hidden State (Vector):** $\mathbf{h}^{(t)} = \sigma(W_{hh}\mathbf{h}^{(t-1)} + \mathbf{w}_{xh}x^{(t)} + \mathbf{b}_h)$ where $\mathbf{h} \in \mathbb{R}^2$ and $W_{hh} \in \mathbb{R}^{2 \times 2}$.
* **Output (Scalar):** $o^{(t)} = \sigma(\mathbf{w}_{ho}^\top \mathbf{h}^{(t)} + b_o)$
* **Loss:** $L = \sum_{t=1}^{3} L^{(t)}$, where $L^{(t)} = \frac{1}{2}(y^{(t)} - o^{(t)})^2$

### Your Task:
1.  **Derive the Gradient:** Write the analytical expression for $\frac{\partial L^{(3)}}{\partial W_{hh}}$.
2.  **The Matrix Product:** Focus specifically on the term $\frac{\partial \mathbf{h}^{(3)}}{\partial \mathbf{h}^{(1)}}$. Write it as a product of two Jacobian matrices.
3.  **Stability Analysis:** * If the eigenvalues of $W_{hh}$ are both $0.1$, what happens to the gradient as $T \to \infty$?
    * If one eigenvalue is $5.0$, what happens?

### Requirements:
* Use the **Chain Rule** to show how the gradient flows from $L^{(3)}$ back to the weight matrix $W_{hh}$ through the hidden states $\mathbf{h}^{(2)}$ and $\mathbf{h}^{(1)}$.
* Identify where the repeated multiplication of $W_{hh}$ occurs in your derivation.

**Assessment:** Submission is not required. We will live-derive the $2 \times 2$ case on the whiteboard to visualize how "exploding gradients" emerge from matrix powers.
