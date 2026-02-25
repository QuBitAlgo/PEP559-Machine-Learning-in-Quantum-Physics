# Assignment #4

## Question 1: Many-to-One BPTT

Consider a **many-to-one** RNN architecture unrolled for $T=3$ time steps. The network receives three sequential inputs but only produces a single output at the final step (see page 11 of the slides). All units are scalars (e.g., the input $x^{(t)}$ is a single real number, not a vector.

* **Hidden States:** $h^{(t)} = \sigma(w_{hh}h^{(t-1)} + w_{xh}x^{(t)} + b_h)$ for $t=1, 2, 3$.
* **Final Output:** $o^{(3)} = \sigma(w_{ho}h^{(3)} + b_o)$
* **Total Loss:** $L = \frac{1}{2}(y - o^{(3)})^2$

### Your Task:
Derive the analytical expressions for the following:

1.  **Output Weight Gradient:** $\frac{\partial L}{\partial w_{ho}}$
2.  **Recurrent Weight Gradient:** $\frac{\partial L}{\partial w_{hh}}$

### Requirements:
* **The "Unrolled" Chain Rule:** For $\frac{\partial L}{\partial w_{hh}}$, show how the gradient flows from the loss $L$ back through $h^{(3)}$, $h^{(2)}$, and $h^{(1)}$. 
* **Term Expansion:** Specifically, show that:
  $$\frac{\partial h^{(3)}}{\partial w_{hh}} = \frac{\partial h^{(3)}}{\partial z_h^{(3)}} \left[ h^{(2)} + \frac{\partial h^{(3)}}{\partial h^{(2)}} \left( h^{(1)} + \dots \right) \right]$$
* **Stability Discussion:** Explain why the repeated term $(w_{hh} \cdot \sigma')$ could lead to a vanishing gradient if $T$ were increased from 3 to 100.

**Assessment:** Submission is not required. Be prepared to show the "Many-to-One" gradient flow on the whiteboard.
