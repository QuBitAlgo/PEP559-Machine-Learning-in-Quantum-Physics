# Hamiltonian Matrix Representation for Two-Qubit Transmon System

In this assignment, you'll explore the structure of the Hamiltonian used in reinforcement learning optimization of superconducting quantum circuits, as seen in the paper.

We will walk through how to construct the Hamiltonian matrix for a system of **two transmon qubits**, including:
- The **anharmonic (nonlinear) energy levels**
- The **external drive terms**
- The **coupling interaction** between the qubits

We adopt the notation from Eq. (1) in the paper, written in the rotating wave approximation (RWA):

![image](https://github.com/user-attachments/assets/99461bb4-07f3-4290-98c5-d97f1f98b782)



Where:
- $\hat{a}_j, \hat{a}_j^\dagger$: annihilation and creation operators for qubit $j$
- $\hat{n}_j = \hat{a}_j^\dagger \hat{a}_j$: number operator
- $\eta$: anharmonicity
- $g(t)$: time-dependent coupling strength between the qubits
- $\delta_j(t)$: detuning of qubit $j$
- $f_j(t)$: drive amplitude
- $\varphi_j(t)$: drive phase

---

## 1. Basis States

We model each transmon as a nonlinear oscillator with discrete energy levels.

Let $|n_1, n_2\rangle$ denote a Fock basis state where:
- $n_1$ is the excitation level of qubit 1
- $n_2$ is the excitation level of qubit 2

Examples:
- $|0, 0\rangle$: both qubits in ground state
- $|1, 0\rangle$: qubit 1 excited, qubit 2 in ground state
- $|0, 1\rangle$: qubit 2 excited
- $|1, 1\rangle$: both qubits excited
- $|2, 0\rangle$, $|2, 1\rangle$, $|2, 2\rangle$, $|1, 2\rangle$, $|0, 2\rangle$, etc.: higher excitation (leakage states)

We will construct the matrix representation of the Hamiltonian in a truncated Hilbert space with:
- $n_1, n_2 \in \{0, 1, 2\}$ → total of 9 basis states, among which, the lowest four form the so-called **qubit subspace**

---

## 2. Operators

Annihilation and creation operator actions:

$$
\hat{a} |n\rangle = \sqrt{n} |n-1\rangle
$$

$$
\hat{a}^\dagger |n\rangle = \sqrt{n+1} |n+1\rangle
$$

Let:
- $\hat{a}_1$, $\hat{a}_1^\dagger$: operators for qubit 1
- $\hat{a}_2$, $\hat{a}_2^\dagger$: operators for qubit 2
- $\hat{n}_1 = \hat{a}_1^\dagger \hat{a}_1$, $\hat{n}_2 = \hat{a}_2^\dagger \hat{a}_2$: number operators

---

## 3. Building the Matrix

### step 1: Define the basis

Write out all 9 basis states in lexicographic order:

$$
|0,0\rangle, |0,1\rangle, |1,0\rangle, |1,1\rangle, |0,2\rangle, |1,2\rangle, |2,0\rangle, |2,1\rangle, |2,2\rangle
$$

---

### step 2: Apply operators

Show how the operators act on a few basis states:

$$
\hat{a}_1 |1,0\rangle = \sqrt{1} |0,0\rangle
$$

$$
\hat{a}_2^\dagger |1,0\rangle = \sqrt{1} |1,1\rangle
$$

$$
\hat{n}_1 |2,1\rangle = 2 |2,1\rangle
$$

---

### step 3: Compute matrix elements

Using the full Hamiltonian above, compute matrix elements like:

$$
\langle 1,0| \hat{H}_{\text{RWA}}(t) |0,0\rangle = i f_1(t) e^{-i\varphi_1(t)} \sqrt{1}
$$

$$
\langle 1,1| \hat{H}_{\text{RWA}}(t) |0,2\rangle = g(t) \sqrt{1 \cdot 2}
$$

Build the full $9 \times 9$ Hamiltonian matrix. Specifically, you will find that
- The diagonal terms arise from $\hat{n}_j(\hat{n}_j - 1)$ and $\delta_j(t)\hat{n}_j$
- The off-diagonal terms arise from coupling and drive

---

### step 4: Identify leakage

- Highlight the computational qubit subspace, a 4x4 block of the 9x9 full matrix, spanned by the four basis states:

$$
|0,0\rangle, |1,0\rangle, |0,1\rangle, |1,1\rangle
$$

- Identify which terms in the Hamiltonian can cause transitions from the qubit subspace to leakage levels (where $n_1$ or $n_2 = 2$).
- Discuss how the drive or coupling contributes to leakage.


