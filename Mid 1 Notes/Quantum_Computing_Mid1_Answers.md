# Quantum Computing — Mid-I Complete Answer Notes
### Vignan's Institute of Information Technology (A)
### Based exclusively on handwritten class notes (Units 1, 2 & 3)

---

> **How to use this document**
> - Answers follow the **exact order** of the Question Bank.
> - Section-I = 2-mark short answers | Section-II = 6-mark long answers.
> - All notation, symbols, and derivations match the handwritten notes exactly.

---

# UNIT 1 — Qubits, Hilbert Space, Density Matrix, Bloch Sphere, Quantum Gates

---

## SECTION-I (2-Mark Questions)

---

### Q1. Define Hilbert Space. **(2M)**

**Answer:**

A **Hilbert Space** is a **linear vector space over complex numbers**. An element in Hilbert space is called a **state vector** $|\psi\rangle$.

Any state in Hilbert space can be expressed as a **linear combination** (superposition) of basis vectors:
$$|\psi\rangle = c_1|\psi_1\rangle + c_2|\psi_2\rangle + c_3|\psi_3\rangle \quad (c \text{ — complex numbers})$$

The basis vectors must satisfy the **orthonormality** condition: $\langle\psi_i|\psi_j\rangle = \delta_{ij}$ (Kronecker delta), making them both **orthogonal and normalized**.

---

### Q2. What is a Density Matrix? **(2M)**

**Answer:**

A **density matrix** (denoted $\rho$) is a matrix representation of the quantum state of a system that handles both **pure states** and **mixed states** (statistical ensembles). It is defined as:
$$\rho = \sum_i p_i |\psi_i\rangle\langle\psi_i|$$
where $p_i$ is the classical probability of each state $|\psi_i\rangle$.

**Key property:** $\text{Tr}(\rho) = 1$ always. For a **pure state**, $\text{Tr}(\rho^2) = 1$; for a **mixed state**, $\text{Tr}(\rho^2) < 1$.

---

### Q3. Explain the significance of the Inner Product in Hilbert Space. **(2M)**

**Answer:**

The **inner product** (scalar product / bra-ket notation $\langle\psi|\phi\rangle$) maps a bra and a ket to a single **scalar (complex number)**. It is fundamental because:

1. **Orthonormality check:** $\langle\psi_i|\psi_j\rangle = \delta_{ij}$ — basis vectors are orthogonal & normalized.
2. **Probability:** If a qubit is in state $|\phi\rangle$, the probability of measuring it as $|\psi\rangle$ is $|\langle\psi|\phi\rangle|^2$.

**Example:** For $|\psi\rangle = |0\rangle = \begin{bmatrix}1\\0\end{bmatrix}$ and $|\phi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle$:
$$\langle\psi|\phi\rangle = \begin{bmatrix}1&0\end{bmatrix}\begin{bmatrix}1/\sqrt{2}\\1/\sqrt{2}\end{bmatrix} = \frac{1}{\sqrt{2}} \implies P = \frac{1}{2} \; (50\%)$$

---

### Q4. Differentiate between Pure State and Mixed State. **(2M)**

**Answer:**

| Property | Pure State | Mixed State |
|---|---|---|
| Description | Complete quantum knowledge (100% certainty) | Classical uncertainty / environmental noise |
| Density matrix | $\rho = |\psi\rangle\langle\psi|$ | $\rho = \sum_i p_i|\psi_i\rangle\langle\psi_i|$ |
| $\text{Tr}(\rho^2)$ | $= 1$ | $< 1$ |
| Off-diagonal elements | Non-zero (quantum coherence) | Zero (decoherence) |
| Example | $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$ — $\rho = \begin{bmatrix}\frac{1}{2}&\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{bmatrix}$ | 50-50 mixture: $\rho = \frac{1}{2}I = \begin{bmatrix}\frac{1}{2}&0\\0&\frac{1}{2}\end{bmatrix}$ |

---

### Q5. Explain the purpose of the Bloch Sphere in representing a qubit. **(2M)**

**Answer:**

The **Bloch Sphere** is a geometric representation of a single qubit's state on the surface of a unit sphere. Any single qubit state can be written as:
$$|\psi\rangle = \cos\frac{\theta}{2}|0\rangle + e^{i\phi}\sin\frac{\theta}{2}|1\rangle$$
where $\theta \in [0, \pi]$ is the polar angle and $\phi \in [0, 2\pi)$ is the azimuthal angle.

- The **North pole** ($\theta=0$) = $|0\rangle$; **South pole** ($\theta=\pi$) = $|1\rangle$.
- Points on the **surface** represent pure states; points **inside** represent mixed states.
- It provides an intuitive visualization of quantum gate operations as rotations.

---

### Q6. *(Question text missing/blank in Question Bank PDF)* **(2M)**

> **FLAG:** Q6 text is not readable/present in the scanned Question Bank PDF. This item cannot be answered. Please check the original printed Question Bank for the question text.

---

---

## SECTION-II (6-Mark Questions)

---

### Q7. Explain the concept of Hilbert Space, basis vectors, orthogonality, completeness, and inner product with suitable mathematical expressions. **(6M)**

**Answer:**

#### 1. Hilbert Space

A **Hilbert Space** $\mathcal{H}$ is a **linear vector space over complex numbers**. Each element in it is a **state vector** $|\psi\rangle$. Any state can be written as a linear combination of basis vectors:
$$|\psi\rangle = c_1|\psi_1\rangle + c_2|\psi_2\rangle + c_3|\psi_3\rangle \quad (c_i \in \mathbb{C})$$

**Analogy — 3D physical space:**
$$\vec{A} = A_x\hat{i} + A_y\hat{j} + A_z\hat{k}$$
where $\hat{i}, \hat{j}, \hat{k}$ are **basis states** satisfying:
- **Normalized:** $\hat{i}\cdot\hat{i} = \hat{j}\cdot\hat{j} = \hat{k}\cdot\hat{k} = 1$
- **Orthogonal:** $\hat{i}\cdot\hat{j} = \hat{j}\cdot\hat{k} = \hat{k}\cdot\hat{i} = 0$

Similarly, in Hilbert space, basis vectors $|\psi_i\rangle$ must satisfy both conditions.

#### 2. Orthogonality and Completeness

When basis is **complete**, the orthonormality condition is:
$$\int \psi_i^* \psi_j \, d\psi = \delta_{ij} \quad \text{(Kronecker delta)}$$
$$\text{In bra-ket: } \langle\psi_i|\psi_j\rangle = \delta_{ij} \quad \rightarrow \text{Orthogonal \& Normalized}$$

#### 3. Inner Product (Scalar Product / Bra-ket)

The **inner product** $\langle\psi|\phi\rangle$ maps a bra and ket to a **single complex scalar**. The computational basis:
$$|0\rangle = \begin{bmatrix}1\\0\end{bmatrix}, \quad |1\rangle = \begin{bmatrix}0\\1\end{bmatrix}$$

**Example:**
$$|\psi\rangle = |0\rangle = \begin{bmatrix}1\\0\end{bmatrix}, \quad \langle\psi| = \begin{bmatrix}1&0\end{bmatrix}$$
$$|\phi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle = \begin{bmatrix}1/\sqrt{2}\\1/\sqrt{2}\end{bmatrix} \quad \text{(the } |+\rangle \text{ state)}$$
$$\langle\psi|\phi\rangle = \begin{bmatrix}1&0\end{bmatrix}\begin{bmatrix}1/\sqrt{2}\\1/\sqrt{2}\end{bmatrix} = \frac{1}{\sqrt{2}}$$

**Probability** of measuring $|\phi\rangle$ as $|0\rangle$: $\left|\frac{1}{\sqrt{2}}\right|^2 = \frac{1}{2} = 50\%$.

#### 4. Outer Product (Ket-Bra)

The **outer product** $|\psi\rangle\langle\phi|$ produces a **matrix (operator)**:
$$|0\rangle\langle+| = \begin{bmatrix}1\\0\end{bmatrix}\begin{bmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}}\end{bmatrix} = \begin{bmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}}\\0&0\end{bmatrix}$$

**Projection operators and completeness:**
$$|0\rangle\langle0| = \begin{bmatrix}1&0\\0&0\end{bmatrix}, \quad |1\rangle\langle1| = \begin{bmatrix}0&0\\0&1\end{bmatrix}$$
$$|0\rangle\langle0| + |1\rangle\langle1| = \begin{bmatrix}1&0\\0&1\end{bmatrix} = I \quad \text{(Identity — completeness relation)}$$

---

### Q8. Describe the Density Matrix Formalism and derive the density matrix for a pure quantum state. **(6M)**

**Answer:**

The **density matrix** $\rho$ is defined as:
$$\rho = \sum_i p_i |\psi_i\rangle\langle\psi_i|$$
where $p_i$ is the classical probability. It handles three types of quantum states:

#### Case 1: Pure States (100% Certainty)

$$\rho = |\psi\rangle\langle\psi|$$

**Example (a) — Computational basis state $|0\rangle$:**
$$|\psi\rangle = |0\rangle = \begin{bmatrix}1\\0\end{bmatrix}$$
$$\rho = |0\rangle\langle0| = \begin{bmatrix}1\\0\end{bmatrix}\begin{bmatrix}1&0\end{bmatrix} = \begin{bmatrix}1&0\\0&0\end{bmatrix}$$

**Example (b) — Superposition state $|+\rangle$:**
$$|\psi\rangle = |+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) = \begin{bmatrix}1/\sqrt{2}\\1/\sqrt{2}\end{bmatrix}$$
$$\rho = |+\rangle\langle+| = \begin{bmatrix}1/\sqrt{2}\\1/\sqrt{2}\end{bmatrix}\begin{bmatrix}1/\sqrt{2}&1/\sqrt{2}\end{bmatrix} = \begin{bmatrix}\frac{1}{2}&\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{bmatrix}$$
$$\text{Tr}(\rho^2) = 1 \quad \text{(off-diagonal elements} = \tfrac{1}{2} \text{, showing quantum coherence)}$$

#### Case 2: Mixed States (Classical Uncertainty / Noise)

Occurs when there is **classical ignorance** or environmental noise. We know only probabilities.

**Example — Maximally Mixed state:**

Suppose a faulty device prepares $|0\rangle$ with $p_1 = 0.5$ and $|1\rangle$ with $p_2 = 0.5$. This is a **statistical mixture**, not a superposition.
$$\rho = 0.5|0\rangle\langle0| + 0.5|1\rangle\langle1|$$
$$= 0.5\begin{bmatrix}1&0\\0&0\end{bmatrix} + 0.5\begin{bmatrix}0&0\\0&1\end{bmatrix} = \begin{bmatrix}\frac{1}{2}&0\\0&\frac{1}{2}\end{bmatrix} = \frac{1}{2}I$$
Off-diagonal elements = 0, indicating **quantum decoherence**. $\text{Tr}(\rho^2) = \frac{1}{2} < 1$.

#### Case 3: Subsystem of Entangled State (Reduced Density Matrix)

If two qubits are entangled (e.g., Bell state $|\phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$), take the **partial trace** $\text{Tr}_B$ to get the reduced density matrix $\rho_A$.

$$|00\rangle = \begin{bmatrix}1\\0\\0\\0\end{bmatrix}, \quad |11\rangle = \begin{bmatrix}0\\0\\0\\1\end{bmatrix}, \quad |\phi^+\rangle = \frac{1}{\sqrt{2}}\begin{bmatrix}1\\0\\0\\1\end{bmatrix}$$
$$\rho_{AB} = |\phi^+\rangle\langle\phi^+| = \frac{1}{2}\begin{bmatrix}1&0&0&1\\0&0&0&0\\0&0&0&0\\1&0&0&1\end{bmatrix}$$

---

### Q9. Explain the Bloch Sphere Representation of a qubit and derive the corresponding density matrix. **(6M)**

**Answer:**

#### Bloch Sphere Representation

Any single qubit can be written as:
$$|\psi\rangle = \cos\frac{\theta}{2}|0\rangle + e^{i\phi}\sin\frac{\theta}{2}|1\rangle = \begin{bmatrix}\cos\frac{\theta}{2}\\e^{i\phi}\sin\frac{\theta}{2}\end{bmatrix}$$

#### Derivation of Density Matrix $\rho = \frac{1}{2}[I + \hat{n}\cdot\vec{\sigma}]$

Starting from $\rho = |\psi\rangle\langle\psi|$:
$$\rho = \begin{bmatrix}\cos^2\frac{\theta}{2} & e^{-i\phi}\sin\frac{\theta}{2}\cos\frac{\theta}{2}\\e^{i\phi}\sin\frac{\theta}{2}\cos\frac{\theta}{2} & \sin^2\frac{\theta}{2}\end{bmatrix}$$

**Applying trigonometric identities:**
$$\cos^2\frac{\theta}{2} = \frac{1+\cos\theta}{2}, \quad \sin^2\frac{\theta}{2} = \frac{1-\cos\theta}{2}, \quad \sin\frac{\theta}{2}\cos\frac{\theta}{2} = \frac{\sin\theta}{2}$$
$$e^{\pm i\phi} = \cos\phi \pm i\sin\phi$$

$$\rho = \frac{1}{2}\begin{bmatrix}1+\cos\theta & e^{-i\phi}\sin\theta\\e^{i\phi}\sin\theta & 1-\cos\theta\end{bmatrix}$$

**Expanding and separating into Pauli matrices:**
$$\rho = \frac{1}{2}\left\{\begin{bmatrix}1&0\\0&1\end{bmatrix} + \begin{bmatrix}\cos\theta & (\cos\phi - i\sin\phi)\sin\theta\\(\cos\phi + i\sin\phi)\sin\theta & -\cos\theta\end{bmatrix}\right\}$$

$$= \frac{1}{2}\left\{I + \cos\theta\underbrace{\begin{bmatrix}1&0\\0&-1\end{bmatrix}}_{\sigma_z} + \cos\phi\sin\theta\underbrace{\begin{bmatrix}0&1\\1&0\end{bmatrix}}_{\sigma_x} + \sin\phi\sin\theta\underbrace{\begin{bmatrix}0&-i\\i&0\end{bmatrix}}_{\sigma_y}\right\}$$

$$\rho = \frac{1}{2}\left[I + \sin\theta\cos\phi\,\sigma_x + \sin\theta\sin\phi\,\sigma_y + \cos\theta\,\sigma_z\right]$$

Since the Bloch vector $\hat{n} = \sin\theta\cos\phi\,\hat{i} + \sin\theta\sin\phi\,\hat{j} + \cos\theta\,\hat{k}$, and $\hat{n}\cdot\vec{\sigma} = \sin\theta\cos\phi\,\sigma_x + \sin\theta\sin\phi\,\sigma_y + \cos\theta\,\sigma_z$:

$$\boxed{\rho = \frac{1}{2}\left[I + \hat{n}\cdot\vec{\sigma}\right]}$$

*(Any point on the Bloch sphere surface has $|\hat{n}| = 1$ — pure state. A point inside has $|\vec{a}| < 1$ — mixed state: $\rho = \frac{1}{2}[I + \vec{a}\cdot\vec{\sigma}]$)*

---

### Q10. Derive the matrix representation and operation of Pauli-X, Pauli-Y, Pauli-Z, Hadamard, Phase (S), and T gates with suitable examples. **(6M)**

**Answer:**

A quantum gate $U$ is a **unitary matrix**: $UU^\dagger = I \Rightarrow U^{-1} = U^\dagger$.

Single qubit gates are derived from $U = \vec{\sigma}\cdot\hat{n}$:

#### 1. Pauli-X ($\sigma_x$) — "Quantum NOT gate"

$$\hat{n} = (1,0,0) \Rightarrow X = \sigma_x = \begin{bmatrix}0&1\\1&0\end{bmatrix}$$

**Outer product form:** $X = |0\rangle\langle1| + |1\rangle\langle0|$

**Action:**
$$X|0\rangle = \begin{bmatrix}0&1\\1&0\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix}0\\1\end{bmatrix} = |1\rangle, \quad X|1\rangle = |0\rangle$$

#### 2. Pauli-Y ($\sigma_y$)

$$\hat{n} = (0,1,0) \Rightarrow Y = \sigma_y = \begin{bmatrix}0&-i\\i&0\end{bmatrix} \quad (i^2=-1)$$

**Outer product form:** $Y = -i|0\rangle\langle1| + i|1\rangle\langle0|$

**Action:**
$$Y|0\rangle = \begin{bmatrix}0&-i\\i&0\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix}0\\i\end{bmatrix} = i|1\rangle, \quad Y|1\rangle = -i|0\rangle$$

#### 3. Pauli-Z ($\sigma_z$) — "Phase flip gate"

$$\hat{n} = (0,0,1) \Rightarrow Z = \sigma_z = \begin{bmatrix}1&0\\0&-1\end{bmatrix}$$

**Outer product form:** $Z = |0\rangle\langle0| - |1\rangle\langle1|$

**Action:**
$$Z|0\rangle = \begin{bmatrix}1&0\\0&-1\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix}1\\0\end{bmatrix} = |0\rangle, \quad Z|1\rangle = -|1\rangle$$

#### 4. Hadamard Gate (H)

Derived using $\hat{n} = \left(\frac{1}{\sqrt{2}}, 0, \frac{1}{\sqrt{2}}\right)$:
$$H = \frac{1}{\sqrt{2}}(\sigma_x + \sigma_z) = \frac{1}{\sqrt{2}}\left(\begin{bmatrix}0&1\\1&0\end{bmatrix}+\begin{bmatrix}1&0\\0&-1\end{bmatrix}\right) = \frac{1}{\sqrt{2}}\begin{bmatrix}1&1\\1&-1\end{bmatrix}$$

*Note: $H^2 = I$ — applying H twice returns to original state.*

**Action:**
$$H|0\rangle = \frac{1}{\sqrt{2}}\begin{bmatrix}1&1\\1&-1\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix} = \frac{1}{\sqrt{2}}\begin{bmatrix}1\\1\end{bmatrix} = \frac{|0\rangle+|1\rangle}{\sqrt{2}}$$
$$H|1\rangle = \frac{1}{\sqrt{2}}\begin{bmatrix}1&1\\1&-1\end{bmatrix}\begin{bmatrix}0\\1\end{bmatrix} = \frac{1}{\sqrt{2}}\begin{bmatrix}1\\-1\end{bmatrix} = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

#### 5. Phase Gate (S Gate)

$$S = \begin{bmatrix}1&0\\0&i\end{bmatrix}$$
**Action:** $S|0\rangle = |0\rangle$, $\quad S|1\rangle = i|1\rangle$

#### 6. T Gate ($\pi/8$ Gate)

$$T = \begin{bmatrix}1&0\\0&e^{i\pi/4}\end{bmatrix}$$

Note: $T^2 = S$ (applying T twice gives the S gate).

---

### Q11. Explain the construction and working of the CNOT Gate with truth table, matrix representation, and quantum circuit. **(6M)**

**Answer:**

The **Controlled-NOT (CNOT)** gate is a two-qubit gate:
- **Control qubit** $|A\rangle$: remains unchanged → $|A\rangle$
- **Target qubit** $|B\rangle$: flipped (XOR) if $|A\rangle = |1\rangle$ → $|B \oplus A\rangle$

$$|A\rangle|B\rangle \longrightarrow |A\rangle|B \oplus A\rangle$$

#### Truth Table

| Input $|AB\rangle$ | Output |
|:---:|:---:|
| $\|00\rangle$ | $\|00\rangle$ (control=0, no flip) |
| $\|01\rangle$ | $\|01\rangle$ (control=0, no flip) |
| $\|10\rangle$ | $\|11\rangle$ (control=1, target flips 0→1) |
| $\|11\rangle$ | $\|10\rangle$ (control=1, target flips 1→0) |

#### Matrix Representation

Basis vectors: $|00\rangle \to \begin{bmatrix}1\\0\\0\\0\end{bmatrix}$, $|01\rangle \to \begin{bmatrix}0\\1\\0\\0\end{bmatrix}$, $|10\rangle \to \begin{bmatrix}0\\0\\1\\0\end{bmatrix}$, $|11\rangle \to \begin{bmatrix}0\\0\\0\\1\end{bmatrix}$

Output ordering: $|00\rangle \to |00\rangle$, $|01\rangle \to |01\rangle$, $|10\rangle \to |11\rangle$, $|11\rangle \to |10\rangle$ (3rd and 4th rows/columns interchange):

$$\text{CNOT} = \begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{bmatrix}$$

*(Top-left 2×2 block = Identity: nothing changes when control = $|0\rangle$. Bottom-right 2×2 block = Pauli-X: flips target when control = $|1\rangle$.)*

#### Quantum Circuit

```
|A⟩ ────●──── |A⟩
         |
|B⟩ ────⊕──── |B ⊕ A⟩
```

**Worked example** — CNOT$(H \otimes X)$ applied to $|00\rangle$:

Circuit:
```
|0⟩ ──[H]──●──── ψ₁
|0⟩ ──[X]──⊕──── ψ₂
```
$$\text{CNOT}(H \otimes X) = \frac{1}{\sqrt{2}}\begin{bmatrix}1&1\\1&-1\end{bmatrix} \otimes \begin{bmatrix}0&1\\1&0\end{bmatrix}$$

After computing the tensor product (3rd and 4th rows interchange due to CNOT):

$$U = \frac{1}{\sqrt{2}}\begin{bmatrix}0&1&0&1\\1&0&1&0\\1&0&-1&0\\0&1&0&-1\end{bmatrix}$$

$$\psi_f = U|00\rangle = \frac{1}{\sqrt{2}}\begin{bmatrix}0\\1\\1\\0\end{bmatrix} = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle) \quad \text{(Bell state)}$$

---

### Q12. Explain the working of the SWAP Gate with circuit diagram, truth table, and matrix representation. **(6M)**

**Answer:**

The **SWAP gate** is a two-qubit gate that **swaps** the states of the two qubits involved:
$$|\phi\rangle|\psi\rangle \longrightarrow |\psi\rangle|\phi\rangle$$

It can be constructed using **3 alternating CNOT gates**.

#### Matrix Representation

$$\text{SWAP} = \begin{bmatrix}1&0&0&0\\0&0&1&0\\0&1&0&0\\0&0&0&1\end{bmatrix}$$

#### Truth Table

| Input | Output |
|:---:|:---:|
| $\|00\rangle$ | $\|00\rangle$ |
| $\|01\rangle$ | $\|10\rangle$ |
| $\|10\rangle$ | $\|01\rangle$ |
| $\|11\rangle$ | $\|11\rangle$ |

#### Quantum Circuit

```
|φ⟩ ────✕──── |ψ⟩
         |
|ψ⟩ ────✕──── |φ⟩
```

*(The ✕ cross-connection symbol denotes a SWAP gate in circuit diagrams.)*

**Equivalent 3-CNOT decomposition:**
```
|φ⟩ ──●──⊕──●── |ψ⟩
       |   |   |
|ψ⟩ ──⊕──●──⊕── |φ⟩
```

---

### Q13. Derive the operation of the Controlled-Z Gate and Toffoli Gate using suitable quantum circuits and matrix representations. **(6M)**

**Answer:**

#### 1. Controlled-Z (CZ) Gate

The CZ gate applies a Z gate to the **target qubit** only when the **control qubit** is $|1\rangle$.

Since $Z|0\rangle = |0\rangle$ and $Z|1\rangle = -|1\rangle$, only $|11\rangle$ gets a phase flip:

$$\text{CZ} = \begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&-1\end{bmatrix}$$

**Truth table:**

| Input | Output |
|:---:|:---:|
| $\|00\rangle$ | $\|00\rangle$ |
| $\|01\rangle$ | $\|01\rangle$ |
| $\|10\rangle$ | $\|10\rangle$ |
| $\|11\rangle$ | $-\|11\rangle$ |

**Working:**
- $|00\rangle$: control = 0 → output $|00\rangle$
- $|01\rangle$: control = 0 → output $|01\rangle$
- $|10\rangle$: control = 1, target = $|0\rangle$ → $Z|0\rangle = |0\rangle$ → output $|10\rangle$
- $|11\rangle$: control = 1, target = $|1\rangle$ → $Z|1\rangle = -|1\rangle$ → output $-|11\rangle$

**Quantum circuit:**
```
|A⟩ ────●──── |A⟩
         |
|B⟩ ────[Z]── |B'⟩
```
*(CZ is symmetric — both qubits can serve as control.)*

#### 2. Toffoli Gate (CCNOT — Controlled-Controlled NOT)

The Toffoli gate has **two control qubits** and **one target qubit**. The target flips only when **both controls** are $|1\rangle$.

$$|a\rangle|b\rangle|c\rangle \longrightarrow |a\rangle|b\rangle|c \oplus ab\rangle$$

$$\text{Toffoli} = \begin{bmatrix}1&0&0&0&0&0&0&0\\0&1&0&0&0&0&0&0\\0&0&1&0&0&0&0&0\\0&0&0&1&0&0&0&0\\0&0&0&0&1&0&0&0\\0&0&0&0&0&1&0&0\\0&0&0&0&0&0&0&1\\0&0&0&0&0&0&1&0\end{bmatrix}$$

*(8×8 matrix — first 6 basis states unchanged; last two $|110\rangle \leftrightarrow |111\rangle$ are swapped.)*

**Truth Table:**

| Input | Output | Note |
|:---:|:---:|:---|
| $\|000\rangle$ | $\|000\rangle$ | Controls not both 1 |
| $\|001\rangle$ | $\|001\rangle$ | Controls not both 1 |
| $\|010\rangle$ | $\|010\rangle$ | Controls not both 1 |
| $\|011\rangle$ | $\|011\rangle$ | Controls not both 1 |
| $\|100\rangle$ | $\|100\rangle$ | Controls not both 1 |
| $\|101\rangle$ | $\|101\rangle$ | Controls not both 1 |
| $\|110\rangle$ | $\|111\rangle$ | Both controls = 1, 3rd qubit flips 0→1 |
| $\|111\rangle$ | $\|110\rangle$ | Both controls = 1, 3rd qubit flips 1→0 |

**Quantum circuit:**
```
|a⟩ ────●──────── |a⟩
         |
|b⟩ ────●──────── |b⟩
         |
|c⟩ ────⊕──────── |c ⊕ ab⟩
```

**Example:** $|110\rangle = \begin{bmatrix}0\\1\end{bmatrix}\otimes\begin{bmatrix}0\\1\end{bmatrix}\otimes\begin{bmatrix}1\\0\end{bmatrix} = [0,0,0,0,0,0,1,0]^T$ → Toffoli maps this to $[0,0,0,0,0,0,0,1]^T = |111\rangle$.

---

### Q14. Analyze the generation of Bell States using Hadamard and CNOT gates. Justify the role of entanglement in Bell state preparation with suitable mathematical derivation and circuit diagram. **(6M)**

**Answer:**

**Bell states** are the four maximally entangled two-qubit states. They are generated using an **H gate** followed by a **CNOT gate**.

#### Quantum Circuit

```
|0⟩ ──[H]──●──── 
            |    
|0⟩ ────── ⊕────
```

#### Generation of Bell State $|\phi^+\rangle$

**Step 1:** Initialize to $|00\rangle$, i.e., $|\psi_0\rangle = |00\rangle$.

**Step 2:** Apply Hadamard to qubit 1:
$$H|0\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}}$$
$$|\psi_1\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}} \otimes |0\rangle = \frac{|00\rangle + |10\rangle}{\sqrt{2}}$$

**Step 3:** Apply CNOT (qubit 1 = control, qubit 2 = target):
- $|00\rangle \to |00\rangle$ (control = 0, no flip)
- $|10\rangle \to |11\rangle$ (control = 1, flip target)

$$|\phi^+\rangle = \frac{|00\rangle + |11\rangle}{\sqrt{2}}$$

#### All Four Bell States

Starting with different initial two-qubit states:

| Initial State | After H on Qubit 1 | After CNOT | Bell State |
|:---:|:---:|:---:|:---:|
| $\|00\rangle$ | $\frac{1}{\sqrt{2}}(\|00\rangle+\|10\rangle)$ | $\frac{1}{\sqrt{2}}(\|00\rangle+\|11\rangle)$ | $\|\phi^+\rangle$ |
| $\|01\rangle$ | $\frac{1}{\sqrt{2}}(\|01\rangle+\|11\rangle)$ | $\frac{1}{\sqrt{2}}(\|01\rangle+\|10\rangle)$ | $\|\psi^+\rangle$ |
| $\|10\rangle$ | $\frac{1}{\sqrt{2}}(\|00\rangle-\|10\rangle)$ | $\frac{1}{\sqrt{2}}(\|00\rangle-\|11\rangle)$ | $\|\phi^-\rangle$ |
| $\|11\rangle$ | $\frac{1}{\sqrt{2}}(\|01\rangle-\|11\rangle)$ | $\frac{1}{\sqrt{2}}(\|01\rangle-\|10\rangle)$ | $\|\psi^-\rangle$ |

#### Worked Matrix Example (from notes)

Circuit with CNOT$(H \otimes H)$ acting on $|00\rangle$:

$$U = \text{CNOT}(H \otimes H) = \frac{1}{2}\begin{bmatrix}1&1&1&1\\1&-1&1&-1\\1&-1&-1&1\\1&1&-1&-1\end{bmatrix}$$

$$\psi_f = U|00\rangle = \frac{1}{2}\begin{bmatrix}1\\1\\1\\1\end{bmatrix} = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$$

#### Role of Entanglement

In a Bell state like $|\phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$, the two qubits are **maximally entangled**: measuring qubit 1 as $|0\rangle$ instantly forces qubit 2 to $|0\rangle$, and vice versa — regardless of the distance separating them. This is the quantum resource exploited in teleportation and quantum cryptography.

---

# UNIT 2 — No-Cloning Theorem, Quantum Teleportation, Bell's Inequality

---

## SECTION-I (2-Mark Questions)

---

### Q15. Define the No-Cloning Theorem. **(2M)**

**Answer:**

The **No-Cloning Theorem** states that it is **impossible** to create a perfect independent copy of an **unknown arbitrary quantum state** without destroying the original.

Mathematically, there exists **no unitary operator** $U$ such that $U|\psi\rangle|S\rangle = |\psi\rangle|\psi\rangle$ holds for all arbitrary states $|\psi\rangle$.

This follows directly from the **linearity** of quantum mechanics: the only states that can be cloned are **orthogonal** states (e.g., $|0\rangle$ and $|1\rangle$ — the classical bit states).

---

### Q16. What is Quantum Teleportation? **(2M)**

**Answer:**

**Quantum Teleportation** is a protocol that transfers an **unknown quantum state** $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ from **Alice (sender)** to **Bob (receiver)** using:
1. A **shared entangled Bell pair** $|\beta_{00}\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$
2. **Classical communication** (2 classical bits) through a classical channel.

The original state at Alice is **destroyed** during measurement (consistent with the No-Cloning Theorem), and Bob reconstructs the exact state by applying correction gates based on Alice's measurement result.

---

### Q17. Explain why an unknown quantum state cannot be cloned. **(2M)**

**Answer:**

An unknown state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ **cannot be cloned** due to two fundamental reasons:

1. **Unitarity / Inner product preservation:** If we assume $U|\psi\rangle|S\rangle = |\psi\rangle|\psi\rangle$ and $U|\phi\rangle|S\rangle = |\phi\rangle|\phi\rangle$, equating inner products before and after cloning gives:
$$\langle\psi|\phi\rangle = (\langle\psi|\phi\rangle)^2$$
Setting $x = \langle\psi|\phi\rangle$: $x^2 = x \Rightarrow x = 0$ or $x = 1$. This allows only **identical** or **orthogonal** states to be cloned — not arbitrary superpositions.

2. **Linearity:** A cloning machine must distribute linearly across superpositions, producing an **entangled state** rather than two independent copies.

---

### Q18. Differentiate between classical copying and quantum cloning. **(2M)**

**Answer:**

| Property | Classical Copying | Quantum Cloning |
|---|---|---|
| Basis | Read a bit (0 or 1) → write to new slot | Requires unitary transformation $U$ |
| Works for | All bit states trivially | Only orthogonal states ($\|0\rangle$, $\|1\rangle$) |
| Unknown state | Can always copy | **Impossible** (No-Cloning Theorem) |
| Superposition | No superpositions exist | Linearity forces entanglement, not a copy |
| Information | Bit value is preserved exactly | Amplitudes $\alpha, \beta$ are **destroyed on measurement** |

Classical bits can be copied by simply reading and rewriting. In quantum mechanics, any attempt to clone $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ results in the Bell state $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$ — an entangled pair, not two independent copies.

---

### Q19. Explain the significance of Bell's Inequality. **(2M)**

**Answer:**

**Bell's Inequality** (specifically the CHSH form) sets a strict upper bound on correlations between distant particles under **classical physics / local hidden variable theories**:
$$|\langle A_0B_0\rangle + \langle A_0B_1\rangle + \langle A_1B_0\rangle - \langle A_1B_1\rangle| \leq 2$$

Its significance:
1. **Tests local realism** — if a system obeys this, it is classical (hidden variables exist).
2. **Quantum violation** — using entangled qubits, quantum mechanics achieves $2\sqrt{2} \approx 2.828 > 2$, proving no local hidden variable theory can explain quantum correlations.
3. **Foundation of Quantum Cryptography** — entanglement security is guaranteed by the violation of Bell's inequality.

---

### Q20. Illustrate how entanglement is utilized in Quantum Teleportation. **(2M)**

**Answer:**

In Quantum Teleportation, **shared entanglement** serves as the quantum channel:

1. Alice and Bob share the Bell pair $|\beta_{00}\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$ — qubit 2 with Alice, qubit 3 with Bob.
2. Alice holds qubit 1 in state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$.
3. Alice performs a **Bell basis measurement** on qubits 1 & 2 → her measurement outcome instantly correlates with Bob's qubit 3 (via entanglement).
4. Alice sends **2 classical bits** to Bob describing her outcome.
5. Bob applies the appropriate **Pauli correction** ($I$, $X$, $Z$, or $XZ$) to reconstruct $|\psi\rangle$.

The entanglement acts as a "quantum bridge" — without it, teleportation is impossible. Note that no information travels faster than light (2 classical bits must still be sent).

---

## SECTION-II (6-Mark Questions)

---

### Q21. Explain the No-Cloning Theorem and derive its mathematical proof using the inner product preservation property of unitary operators. **(6M)**

**Answer:**

#### Statement

The **No-Cloning Theorem** states that it is **impossible** to build a universal quantum machine that creates a perfect copy of an arbitrary unknown quantum state.

#### Step 1: Define the Machine

A quantum cloning machine is a **unitary operator** $U$. It takes two inputs:
1. The target state to copy: $|\psi\rangle$
2. A blank "quantum paper" in standard state: $|S\rangle$

If the machine works, applying $U$ must output two copies:
$$U|\psi\rangle|S\rangle = |\psi\rangle|\psi\rangle \quad \cdots (1)$$

#### Step 2: Test with Two Different States

If this is a **universal copier**, it must work for **any** state:
$$U|\psi\rangle|S\rangle = |\psi\rangle|\psi\rangle$$
$$U|\phi\rangle|S\rangle = |\phi\rangle|\phi\rangle$$

#### Step 3: Take the Inner Product

**After cloning** (right-hand side):
$$(\langle\psi|\langle\psi|)(|\phi\rangle|\phi\rangle) = \langle\psi|\phi\rangle \cdot \langle\psi|\phi\rangle = (\langle\psi|\phi\rangle)^2$$

**Before cloning** (left-hand side — unitarity preserves inner product):
$$(\langle\psi|\langle S|U^\dagger)(U|\phi\rangle|S\rangle) = \langle\psi|\langle S|I|\phi\rangle|S\rangle = \langle\psi|\phi\rangle\underbrace{\langle S|S\rangle}_{=1} = \langle\psi|\phi\rangle$$

#### Step 4: The Conflict

Because unitary operators **preserve inner products**, before = after:
$$(\langle\psi|\phi\rangle)^2 = \langle\psi|\phi\rangle$$

Let $x = \langle\psi|\phi\rangle$:
$$x^2 = x \Rightarrow x^2 - x = 0 \Rightarrow x(x-1) = 0$$

**Only two solutions:**
- $x = 1$: $\langle\psi|\phi\rangle = 1 \Rightarrow |\psi\rangle = |\phi\rangle$ (identical states)
- $x = 0$: $\langle\psi|\phi\rangle = 0 \Rightarrow |\psi\rangle \perp |\phi\rangle$ (orthogonal states)

#### Conclusion

A universal copier can only clone **identical** or **orthogonal** states. For any **arbitrary superposition** with $0 < |\langle\psi|\phi\rangle| < 1$, the math breaks down. **A universal quantum copier cannot exist.**

---

### Q22. Describe the cloning of basis states and superposition states. Explain why cloning fails for arbitrary quantum states with suitable mathematical analysis. **(6M)**

**Answer:**

#### Cloning Basis States — Succeeds

Suppose a machine (e.g., CNOT gate with $|S\rangle = |0\rangle$) copies the standard basis:
$$U|0\rangle|S\rangle = |0\rangle|0\rangle$$
$$U|1\rangle|S\rangle = |1\rangle|1\rangle$$

Testing with CNOT:
- Input $|0\rangle|0\rangle$: control = 0 → target not flipped → $|00\rangle$ ✓
- Input $|1\rangle|0\rangle$: control = 1 → target flips → $|11\rangle$ ✓ (perfect copy)

#### Cloning a Superposition — Fails

Try to clone $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$:

**Path 1: What a perfect clone should look like**
$$\text{Expected O/P} = |+\rangle|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle+|1\rangle) \otimes \frac{1}{\sqrt{2}}(|0\rangle+|1\rangle) = \frac{1}{2}(|00\rangle+|01\rangle+|10\rangle+|11\rangle)$$

**Path 2: What quantum mechanics actually outputs (Linearity)**

Because quantum mechanics is **strictly linear**, $U$ must distribute across the superposition:
$$U|+\rangle|S\rangle = U\left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right)|S\rangle = \frac{1}{\sqrt{2}}\left(U|0\rangle|S\rangle + U|1\rangle|S\rangle\right)$$

Substituting known behaviors:
$$\text{Actual O/P} = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) \quad \text{(Bell state!)}$$

#### Verdict — Compare the results:

| | State |
|---|---|
| **Expected** | $\frac{1}{2}(\|00\rangle+\|01\rangle+\|10\rangle+\|11\rangle)$ |
| **Actual** | $\frac{1}{\sqrt{2}}(\|00\rangle+\|11\rangle)$ |

Instead of **two independent copies** of $|+\rangle$, the machine created a **highly entangled Bell state**. The two qubits are fused together — not cloned.

**What you wanted:** Two completely independent, isolated qubits each in state $|\psi\rangle$.

**What you actually get:** A single entangled Bell state. If you modify or measure the first qubit, the second qubit instantly reacts.

**Root cause:** Linearity forced the machine to fail. Cloning is fundamentally incompatible with the linear structure of quantum mechanics.

---

### Q23. Explain the Quantum Teleportation protocol with the quantum circuit and describe the roles of Alice and Bob. **(6M)**

**Answer:**

#### Setup and Roles

- **Alice (Sender):** Holds qubit 1 in unknown state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$. She wants to send this exact state to Bob.
- **Bob (Receiver):** Space-separated from Alice, waiting to reconstruct $|\psi\rangle$.

Due to the **No-Cloning Theorem**, Alice cannot copy $|\psi\rangle$ without destroying it. If she measures, the state collapses and $\alpha, \beta$ are permanently lost.

#### Quantum Circuit

```
Alice's qubits:
  |ψ⟩ (q1) ──────────●──────[H]──[M₁]══════════════════► (Z correction on Bob)
  |0⟩ (q2) ──[H]──●──⊕────────────[M₂]══════════════════► (X correction on Bob)
                    |
Bob's qubit:
  |0⟩ (q3) ────────⊕────────────────────────[X]──[Z]── |ψ⟩
```

*(Double lines = classical channels)*

#### Step 1: Prepare the Entangled Pair

A Bell pair is shared:
$$|\beta_{00}\rangle_{23} = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$$
Qubit 2 goes to Alice; qubit 3 goes to Bob.

#### Step 2: Initial 3-Qubit State

$$|\psi_0\rangle = |\psi\rangle_1 \otimes |\beta_{00}\rangle_{23} = (\alpha|0\rangle + \beta|1\rangle) \otimes \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$$
$$= \frac{1}{\sqrt{2}}[\alpha|000\rangle + \alpha|011\rangle + \beta|100\rangle + \beta|111\rangle]$$

#### Step 3: Alice applies CNOT$_{12}$ (qubit 1 = control, qubit 2 = target)

$$|\psi_1\rangle = \frac{1}{\sqrt{2}}[\alpha|000\rangle + \alpha|011\rangle + \beta|110\rangle + \beta|101\rangle]$$

#### Step 4: Alice applies Hadamard to qubit 1

Using $H|0\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}$ and $H|1\rangle = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$:

$$|\psi_2\rangle = \frac{1}{2}[|00\rangle(\alpha|0\rangle+\beta|1\rangle) + |01\rangle(\alpha|1\rangle+\beta|0\rangle) + |10\rangle(\alpha|0\rangle-\beta|1\rangle) + |11\rangle(\alpha|1\rangle-\beta|0\rangle)]$$

#### Step 5: Alice Measures (Classical Communication)

Alice measures qubits 1 & 2 and sends 2 classical bits to Bob:

| Alice Measures | Bob Has | Bob Applies |
|:---:|:---:|:---:|
| $\|00\rangle$ | $\alpha\|0\rangle+\beta\|1\rangle$ | $I$ (nothing) |
| $\|01\rangle$ | $\alpha\|1\rangle+\beta\|0\rangle$ | $X$ (Pauli-X) |
| $\|10\rangle$ | $\alpha\|0\rangle-\beta\|1\rangle$ | $Z$ (Pauli-Z) |
| $\|11\rangle$ | $\alpha\|1\rangle-\beta\|0\rangle$ | $XZ$ (both) |

After applying the correction gate, Bob's qubit becomes exactly $\alpha|0\rangle + \beta|1\rangle = |\psi\rangle$.

**Note:** Alice's original qubit is destroyed in the process — consistent with No-Cloning Theorem.

---

### Q24. Derive the mathematical steps involved in the Quantum Teleportation algorithm and explain the state transformation after each quantum operation. **(6M)**

**Answer:**

#### Initial State $|\psi_0\rangle$

Alice holds $|\psi\rangle_1 = \alpha|0\rangle + \beta|1\rangle$. Shared Bell pair:
$$|\beta_{00}\rangle_{23} = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)_{23}$$

Complete 3-qubit state:
$$|\psi_0\rangle = (\alpha|0\rangle+\beta|1\rangle) \otimes \frac{1}{\sqrt{2}}(|00\rangle+|11\rangle)$$
$$= \frac{1}{\sqrt{2}}[\alpha|000\rangle + \alpha|011\rangle + \beta|100\rangle + \beta|111\rangle]$$

#### After CNOT$_{12}$ → $|\psi_1\rangle$

CNOT flips qubit 2 if qubit 1 = $|1\rangle$:
- $|000\rangle \to |000\rangle$
- $|011\rangle \to |011\rangle$
- $|100\rangle \to |110\rangle$
- $|111\rangle \to |101\rangle$

$$|\psi_1\rangle = \frac{1}{\sqrt{2}}[\alpha|000\rangle + \alpha|011\rangle + \beta|110\rangle + \beta|101\rangle]$$

#### After $H_1$ (Hadamard on qubit 1) → $|\psi_2\rangle$

Substitute $H|0\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}$ and $H|1\rangle = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$ into qubit 1 of $|\psi_1\rangle$:

$$|\psi_2\rangle = \frac{1}{2}\bigl[\alpha|000\rangle+\alpha|100\rangle+\alpha|011\rangle+\alpha|111\rangle+\beta|010\rangle-\beta|110\rangle+\beta|001\rangle-\beta|101\rangle\bigr]$$

**Regroup by Alice's qubit pair (qubits 1,2):**

$$|\psi_2\rangle = \frac{1}{2}\Bigl[|00\rangle(\alpha|0\rangle+\beta|1\rangle) + |01\rangle(\alpha|1\rangle+\beta|0\rangle) + |10\rangle(\alpha|0\rangle-\beta|1\rangle) + |11\rangle(\alpha|1\rangle-\beta|0\rangle)\Bigr]$$

#### After Alice's Measurement and Bob's Correction

| Alice measures | Bob's qubit | Correction | Final state |
|:---:|:---:|:---:|:---:|
| $\|00\rangle$ | $\alpha\|0\rangle+\beta\|1\rangle$ | $I$ | $\alpha\|0\rangle+\beta\|1\rangle = \|\psi\rangle$ ✓ |
| $\|01\rangle$ | $\alpha\|1\rangle+\beta\|0\rangle$ | $X$ | $X(\alpha\|1\rangle+\beta\|0\rangle) = \alpha\|0\rangle+\beta\|1\rangle$ ✓ |
| $\|10\rangle$ | $\alpha\|0\rangle-\beta\|1\rangle$ | $Z$ | $Z(\alpha\|0\rangle-\beta\|1\rangle) = \alpha\|0\rangle+\beta\|1\rangle$ ✓ |
| $\|11\rangle$ | $\alpha\|1\rangle-\beta\|0\rangle$ | $XZ$ | $XZ(\alpha\|1\rangle-\beta\|0\rangle) = \alpha\|0\rangle+\beta\|1\rangle$ ✓ |

In all four cases, Bob recovers $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ exactly. **Teleportation is complete.**

---

### Q25. Explain Bell's Inequality, derive the CHSH inequality, and discuss its significance in quantum mechanics. **(6M)**

**Answer:**

#### Background

**Bell's Inequality** is a mathematical framework that sets a strict upper limit on how strongly correlated the measurement outcomes of two distant particles can be under **classical physics (local realism)**.

Einstein, Podolsky and Rosen (EPR) argued that quantum mechanics was **incomplete** — particles must possess predetermined hidden properties called **Local Hidden Variables (LHVs)** that dictate measurement outcomes before they occur.

Bell proved theoretically that if LHVs existed, the correlation coefficient in a specific experimental setup must remain $\leq 2$.

#### Experimental Setup

An entanglement source generates pairs of photons — one to Alice, one to Bob.
- Alice measures along angles $A_0$ or $A_1$.
- Bob measures along angles $B_0$ or $B_1$.
- Outcomes: $+1$ (spin up) or $-1$ (spin down).

#### Derivation of CHSH Inequality

Assume **local realism**: $A_0, A_1, B_0, B_1$ all have predetermined values of $\pm 1$ simultaneously.

Consider:
$$C = A_0(B_0 + B_1) + A_1(B_0 - B_1)$$
$$= A_0B_0 + A_0B_1 + A_1B_0 - A_1B_1$$

Analyzing $(B_0+B_1)$ and $(B_0-B_1)$:
- If $B_0 = B_1$: $(B_0+B_1) = \pm2$ and $(B_0-B_1) = 0$
- If $B_0 \neq B_1$: $(B_0+B_1) = 0$ and $(B_0-B_1) = \pm2$

In either case, since $A_0, A_1 = \pm1$, the value of $C$ for any single particle pair is exactly $+2$ or $-2$.

Averaging over thousands of trials:
$$\boxed{|\langle A_0B_0\rangle + \langle A_0B_1\rangle + \langle A_1B_0\rangle - \langle A_1B_1\rangle| \leq 2}$$

This is the **CHSH Bell Inequality**. The bound of **2** is the absolute limit of correlation dictated by classical physics.

#### Significance

Bell's inequality is significant because:
1. It converts the EPR philosophical debate into a **testable experiment**.
2. It distinguishes quantum mechanics from any classical / hidden variable theory.
3. Its **quantum violation** ($2\sqrt{2}$) confirms non-locality and genuine entanglement.
4. It is the foundation of **quantum cryptography** (security proofs) and **quantum communication**.

---

### Q26. Derive the mathematical proof showing the violation of Bell's Inequality by quantum mechanics using an entangled Bell state. **(6M)**

**Answer:**

#### Quantum Prediction

If Alice and Bob share the maximally entangled Bell state:
$$|\psi^+\rangle = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$$

and they carefully choose their measurement angles, the quantum expectation values are:
$$\langle A_0B_0\rangle = \frac{1}{\sqrt{2}}, \quad \langle A_0B_1\rangle = \frac{1}{\sqrt{2}}, \quad \langle A_1B_0\rangle = \frac{1}{\sqrt{2}}, \quad \langle A_1B_1\rangle = -\frac{1}{\sqrt{2}}$$

#### Computing the CHSH Expression

$$|\langle A_0B_0\rangle + \langle A_0B_1\rangle + \langle A_1B_0\rangle - \langle A_1B_1\rangle|$$
$$= \left|\frac{1}{\sqrt{2}} + \frac{1}{\sqrt{2}} + \frac{1}{\sqrt{2}} - \left(-\frac{1}{\sqrt{2}}\right)\right|$$
$$= \left|\frac{4}{\sqrt{2}}\right| = \frac{4}{\sqrt{2}} = 2\sqrt{2} \approx 2.828$$

#### Result

$$2\sqrt{2} \approx 2.828 > 2$$

**Quantum mechanics explicitly violates Bell's inequality!**

#### Implications

Bell's inequality has several important implications:
1. **Rejection of local hidden variable theories** — no LHV model can reproduce quantum predictions.
2. **Confirmation of quantum entanglement** — correlations are stronger than any classical mechanism allows.
3. **Non-local nature of reality** — quantum states are inherently non-local.
4. **Impact on classical realism** — particle properties are not predetermined.
5. **Foundation for quantum computing** — entanglement is a genuine resource.
6. **Application in Quantum Cryptography** — security is based on entanglement statistics.
7. **Experimental Verification** — multiple experiments (Aspect et al.) have confirmed the violation.

---

### Q27. Explain the implications of the No-Cloning Theorem and discuss its role in Quantum Communication and Quantum Cryptography. **(6M)**

**Answer:**

#### Statement Recap

No unitary $U$ can satisfy $U|\psi\rangle|S\rangle = |\psi\rangle|\psi\rangle$ for all arbitrary $|\psi\rangle$. The algebraic proof shows $x^2 = x$ has only solutions $x = 0$ or $x = 1$, permitting cloning only of orthogonal states.

#### Key Implications

**1. Measurement collapses state:** Alice cannot measure $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ to find $\alpha, \beta$ (measurement collapses to $|0\rangle$ or $|1\rangle$), so she **cannot copy it classically** either.

**2. Entanglement, not cloning, is created:** A CNOT-based copier produces $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$ — a Bell state — instead of two independent copies.

**3. Teleportation is the only transfer mechanism:** The No-Cloning Theorem **forces** the use of quantum teleportation (which destroys the original) rather than independent copying.

#### Role in Quantum Communication

- **Quantum repeaters** cannot simply amplify (clone) signals like classical repeaters. Instead, they use **entanglement swapping**.
- **Quantum networks** rely on teleportation as the fundamental operation for state transfer.
- **No wire-tapping without detection:** Any eavesdropper trying to clone quantum signals on a communication line will inevitably disturb the state (due to no-cloning), revealing their presence.

#### Role in Quantum Cryptography (QKD)

In **BB84 Quantum Key Distribution**:
- Alice sends qubits in random bases ($+$ or $\times$).
- Eve (eavesdropper) **cannot clone** the qubits to retain a copy while forwarding the original — she must measure, which disturbs the state.
- Alice and Bob can detect Eve's presence through error rates in the key.

The No-Cloning Theorem thus **guarantees the security** of quantum cryptographic protocols — any interception is physically detectable.

---

### Q28. Analyze the relationship among the No-Cloning Theorem, Quantum Teleportation, and Bell's Inequality. Justify how these principles establish the foundations of secure quantum communication. **(6M)**

**Answer:**

#### The Three Pillars and Their Relationship

**1. No-Cloning Theorem** establishes a fundamental **limitation**: unknown quantum states cannot be perfectly copied. This forces any transfer of quantum information to be **destructive at the source** (original is lost).

**2. Quantum Teleportation** is the **solution** enabled by entanglement: since cloning is forbidden, teleportation is the only way to transfer an arbitrary quantum state. It:
- Destroys Alice's original (consistent with No-Cloning)
- Uses Bell state entanglement + 2 classical bits
- Reconstructs the **exact state** at Bob's end

**3. Bell's Inequality** provides the **verification** that entanglement is real and non-classical. The violation ($2\sqrt{2} > 2$) confirms that:
- The shared Bell states used in teleportation are **genuinely entangled**
- No classical (LHV) simulation can reproduce the correlations

#### How They Establish Secure Quantum Communication

| Principle | Contribution to Security |
|---|---|
| **No-Cloning** | Eavesdropper cannot intercept without disturbing the state |
| **Teleportation** | Transfers state without exposing it to interception |
| **Bell's Inequality Violation** | Certifies entanglement quality; eavesdropper cannot fake it |

**Together:**
- No-Cloning $\Rightarrow$ eavesdropping is **detectable**
- Teleportation $\Rightarrow$ state is **transmitted securely** (2 classical bits are useless without the Bell pair)
- Bell Inequality $\Rightarrow$ entanglement **quality is verifiable** (device-independent security)

This trinity forms the **physical foundation** of quantum cryptography (QKD), quantum networks, and ultimately quantum internet security.

---

# UNIT 3 — Deutsch Algorithm, Deutsch-Jozsa Algorithm

---

## SECTION-I (2-Mark Questions)

---

### Q29. Define the Deutsch Algorithm. **(2M)**

**Answer:**

The **Deutsch Algorithm**, proposed by David Deutsch in 1985, is the first quantum algorithm to demonstrate that a quantum computer can **solve a specific problem faster** than a classical computer.

**Problem:** Given a Boolean function $f : \{0,1\} \to \{0,1\}$, determine whether $f$ is **constant** (same output for both inputs) or **balanced** (different outputs) using the **minimum number of function evaluations**.

- **Classical:** Requires **2** evaluations ($f(0)$ and $f(1)$).
- **Quantum:** Requires only **1** evaluation via quantum parallelism and phase kickback.

---

### Q30. What is the objective of the Deutsch–Jozsa Algorithm? **(2M)**

**Answer:**

The **Deutsch-Jozsa Algorithm** (Deutsch & Jozsa, 1992) is an extension of the Deutsch algorithm to an $n$-bit input. Its objective is to determine, with **certainty**, whether a given $n$-bit Boolean function $f : \{0,1\}^n \to \{0,1\}$ is:

- **Constant:** Produces the **same output** (all 0's or all 1's) for every possible input.
- **Balanced:** Produces **0 for exactly half** of the inputs and **1 for the remaining half**.

**Classical advantage:** A classical computer needs up to $2^{n-1}+1$ evaluations in the worst case. The Deutsch-Jozsa algorithm solves it in **1 query** — an **exponential speedup**.

---

### Q31. Distinguish between Constant and Balanced Boolean Functions. **(2M)**

**Answer:**

| Property | Constant Function | Balanced Function |
|---|---|---|
| Definition | Same output for **all** inputs | Output 0 for **half** inputs, 1 for remaining half |
| For $n=1$: | $f(0)=f(1)=0$ or $f(0)=f(1)=1$ | $f(0)=0, f(1)=1$ or $f(0)=1, f(1)=0$ |
| Quantum outcome | Measurement gives $\|0\rangle^{\otimes n}$ | At least one qubit measured as $\|1\rangle$ |
| Phase | $(-1)^{f(0)} = (-1)^{f(1)}$ — phases same | $(-1)^{f(0)} \neq (-1)^{f(1)}$ — phases opposite |

In Deutsch's algorithm: **measure 0 → constant; measure 1 → balanced**.

---

### Q32. Explain the role of Phase Kickback in the Deutsch Algorithm. **(2M)**

**Answer:**

**Phase Kickback** is the mechanism by which the oracle $U_f$ encodes the function value $f(x)$ as a **phase** on the input qubit rather than on the output.

When the ancilla (output) qubit is in state $\frac{|0\rangle - |1\rangle}{\sqrt{2}}$, the oracle action becomes:
$$U_f|x\rangle\frac{|0\rangle-|1\rangle}{\sqrt{2}} = (-1)^{f(x)}|x\rangle\frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

The identity $|0\oplus f(x)\rangle - |1\oplus f(x)\rangle = (-1)^{f(x)}(|0\rangle-|1\rangle)$ causes the function value to "kick back" as a global phase $(-1)^{f(x)}$ onto the **input qubit** $|x\rangle$.

This allows the final Hadamard to convert the phase difference into a **measurable bit difference**: constant functions → $|0\rangle$, balanced functions → $|1\rangle$.

---

## SECTION-II (6-Mark Questions)

---

### Q33. Explain the Deutsch Algorithm with a neat quantum circuit and discuss the initialization of qubits, oracle operation, and final measurement. **(6M)**

**Answer:**

#### Overview

The Deutsch Algorithm determines whether $f : \{0,1\} \to \{0,1\}$ is **constant** or **balanced** using **one oracle call**, whereas a classical computer needs **two**.

#### Quantum Circuit

```
|0⟩ ──[H]──[     ]──[H]──[M]── (measure)
           [ U_f ]
|1⟩ ──[H]──[     ]────────────  (ancilla, ignored)
```

#### Step 1: Initialization

Two qubits are used:
- Qubit 1 (input register): $|0\rangle$
- Qubit 2 (output/ancilla): $|1\rangle$

$$|\psi_0\rangle = |0\rangle|1\rangle = |01\rangle = \begin{bmatrix}0\\1\\0\\0\end{bmatrix}$$

#### Step 2: Apply Hadamard ($H^{\otimes 2}$)

$$H|0\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}, \quad H|1\rangle = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

$$|\psi_1\rangle = \left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right)\otimes\left(\frac{|0\rangle-|1\rangle}{\sqrt{2}}\right) = \frac{1}{2}(|00\rangle-|01\rangle+|10\rangle-|11\rangle)$$

#### Step 3: Oracle Operation $U_f$

The oracle: $U_f|x,y\rangle = |x, y\oplus f(x)\rangle$

Using the phase kickback identity $|0\oplus f(x)\rangle - |1\oplus f(x)\rangle = (-1)^{f(x)}(|0\rangle-|1\rangle)$:

$$|\psi_2\rangle = \frac{1}{\sqrt{2}}\left[(-1)^{f(0)}|0\rangle + (-1)^{f(1)}|1\rangle\right] \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

#### Step 4: Apply Hadamard to First Qubit

#### Case Analysis:

**Constant function 1** ($f(0)=0, f(1)=0$):
$$|\psi_2\rangle \text{ (input part)} = \frac{|0\rangle+|1\rangle}{\sqrt{2}}$$
$$H\left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right) = |0\rangle \quad \Rightarrow \text{Measurement: } \mathbf{0} \quad \text{(Constant)}$$

**Constant function 2** ($f(0)=1, f(1)=1$):
$$|\psi_2\rangle \text{ (input part)} = -\frac{|0\rangle+|1\rangle}{\sqrt{2}} \quad \text{(global phase }{-1}\text{, no effect)}$$
$$H\left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right) = |0\rangle \quad \Rightarrow \text{Measurement: } \mathbf{0} \quad \text{(Constant)}$$

**Balanced function 1** ($f(0)=0, f(1)=1$): $(-1)^0=1,\; (-1)^1=-1$
$$|\psi_2\rangle \text{ (input part)} = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$
$$H\left(\frac{|0\rangle-|1\rangle}{\sqrt{2}}\right) = |1\rangle \quad \Rightarrow \text{Measurement: } \mathbf{1} \quad \text{(Balanced)}$$

**Balanced function 2** ($f(0)=1, f(1)=0$): $(-1)^1=-1,\; (-1)^0=1$
$$|\psi_2\rangle \text{ (input part)} = -\frac{|0\rangle-|1\rangle}{\sqrt{2}} \quad \text{(global phase }{-1}\text{)}$$
Ignoring global phase: $\frac{|0\rangle-|1\rangle}{\sqrt{2}} \xrightarrow{H} |1\rangle \quad \Rightarrow \text{Measurement: } \mathbf{1} \quad \text{(Balanced)}$

#### Summary

| $f$ type | Measurement | Decision |
|:---:|:---:|:---:|
| Constant | $0$ | $f$ is constant |
| Balanced | $1$ | $f$ is balanced |

One single oracle query determines the answer — **quantum speedup achieved**.

---

### Q34. Demonstrate the execution of the Deutsch–Jozsa Algorithm for a three-qubit input register by explaining the state transformations at every stage. **(6M)**

**Answer:**

#### Setup: $n = 3$ Input Qubits + 1 Ancilla

**Initial state $|\psi_0\rangle$:**
- Three input qubits initialized to $|0\rangle$; ancilla initialized to $|1\rangle$:

$$|\psi_0\rangle = |000\rangle|1\rangle$$

#### Step 1: Apply Hadamard to All Qubits ($|\psi_1\rangle$)

For input qubits: $H|0\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}$. For ancilla: $H|1\rangle = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$.

**Input register:**
$$H^{\otimes 3}|000\rangle = \frac{1}{\sqrt{8}}\sum_{x=0}^{7}|x\rangle = \frac{1}{\sqrt{8}}\bigl(|000\rangle+|001\rangle+|010\rangle+|011\rangle+|100\rangle+|101\rangle+|110\rangle+|111\rangle\bigr)$$

*(All 8 possible 3-bit inputs simultaneously — superposition)*

**Complete state entering oracle:**
$$|\psi_1\rangle = \frac{1}{\sqrt{8}}\sum_{x=0}^{7}|x\rangle \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

#### Step 2: Oracle Operation $U_f$ ($|\psi_2\rangle$)

Oracle: $U_f|x,y\rangle = |x, y\oplus f(x)\rangle$

Since ancilla is $\frac{|0\rangle-|1\rangle}{\sqrt{2}}$, the XOR operation changes only the **phase** (phase kickback):
$$|\psi_2\rangle = \frac{1}{\sqrt{8}}\sum_{x=0}^{7}(-1)^{f(x)}|x\rangle \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

Each basis state $|x\rangle$ acquires phase $(-1)^{f(x)}$.

#### Step 3: Apply Hadamard Again to Input Register ($|\psi_3\rangle$)

The Hadamard transform is:
$$H^{\otimes 3}|x\rangle = \frac{1}{\sqrt{8}}\sum_{z=0}^{7}(-1)^{x\cdot z}|z\rangle$$
where $x\cdot z$ is the bitwise inner product modulo 2.

Final state:
$$|\psi_3\rangle = \frac{1}{8}\sum_{z=0}^{7}\left[\sum_{x=0}^{7}(-1)^{f(x)+x\cdot z}\right]|z\rangle$$

**Quantum interference:**
- Positive amplitude interference → **constructive** (amplitudes add)
- Negative amplitude interference → **destructive** (amplitudes cancel)

#### Step 4: Measurement

**If $f$ is constant** ($f(x)$ = same for all $x$):
$$\sum_{x=0}^{7}(-1)^{f(x)+x\cdot z} = (-1)^{f(x)}\sum_{x=0}^{7}(-1)^{x\cdot z}$$
For $|z\rangle = |000\rangle$ (z=0): all phases $(-1)^{x\cdot 0} = 1$ → sum = 8 → amplitude = 1 at $|000\rangle$.
For $z \neq 0$: the sum = 0 (destructive interference).

**→ Measurement gives $|000\rangle$ with certainty → Function is CONSTANT.**

**If $f$ is balanced:**
For $|z\rangle = |000\rangle$: $\sum_x(-1)^{f(x)} = 0$ (half +1, half −1 cancel).

**→ Amplitude at $|000\rangle$ = 0 → At least one qubit measured as 1 → Function is BALANCED.**

---

### Q35. Explain the Deutsch–Jozsa Algorithm with a suitable quantum circuit and discuss each computational step in detail. **(6M)**

**Answer:**

#### Introduction

The **Deutsch-Jozsa Algorithm** (David Deutsch & Richard Jozsa, 1992) is one of the earliest and most important quantum algorithms. It demonstrates that a quantum computer can solve a specific computational problem **exponentially faster** than a classical computer.

**Problem:** Given a Boolean function $f : \{0,1\}^n \to \{0,1\}$ (promised to be either constant or balanced), determine which type it is.

- Classical: worst case $2^{n-1}+1$ evaluations.
- Quantum: **1 oracle call**.

#### Quantum Circuit ($n=3$)

```
Input register (n=3):
|0⟩ ──[H]──┐                  ┌──[H]──[M]── q₁
|0⟩ ──[H]──┤    Oracle U_f    ├──[H]──[M]── q₂
|0⟩ ──[H]──┘  U_f|x,y⟩=      └──[H]──[M]── q₃
            |x, y⊕f(x)⟩
Ancilla:
|1⟩ ──[H]──────────────────────────────────  (ignored) q₄
```

Stage descriptions:
1. **First H layer:** Create superposition
2. **Middle block $U_f$:** Oracle operation
3. **Third H layer:** Create quantum interference
4. **Measurement:** Read output

Parameters: $n$ = number of input qubits = 3; $x$ = $n$-bit input; $y$ = ancilla; $\oplus$ = XOR.

#### Step 1: Initialize Qubits

$$|\psi_0\rangle = |000\rangle|1\rangle \quad \text{(I/P register = }|000\rangle\text{, Ancilla = }|1\rangle\text{)}$$

#### Step 2: Apply Hadamard — Create Superposition

Apply H to every qubit:
$$H|0\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}, \quad H|1\rangle = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

**Input register** (each of 3 qubits becomes $\frac{|0\rangle+|1\rangle}{\sqrt{2}}$):
$$H^{\otimes 3}|000\rangle = \frac{1}{\sqrt{8}}\sum_{x=0}^{7}|x\rangle$$

Expanded: $\frac{1}{\sqrt{8}}(|000\rangle+|001\rangle+|010\rangle+|011\rangle+|100\rangle+|101\rangle+|110\rangle+|111\rangle)$

*(All 8 input combinations evaluated simultaneously — this is the quantum parallelism advantage)*

**Ancilla:** $\frac{|0\rangle-|1\rangle}{\sqrt{2}}$

**Complete state entering oracle:**
$$|\psi_1\rangle = \frac{1}{\sqrt{8}}\sum_{x=0}^{7}|x\rangle \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

#### Step 3: Oracle Operation — Phase Kickback

$$U_f|x,y\rangle = |x, y\oplus f(x)\rangle$$

Since ancilla is $\frac{|0\rangle-|1\rangle}{\sqrt{2}}$, the XOR changes only the phase:
$$|\psi_2\rangle = \frac{1}{\sqrt{8}}\sum_{x=0}^{7}(-1)^{f(x)}|x\rangle \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

#### Step 4: Apply Hadamard Again — Create Interference

$$H^{\otimes 3}|x\rangle = \frac{1}{\sqrt{8}}\sum_{z=0}^{7}(-1)^{x\cdot z}|z\rangle \quad (x\cdot z = \text{bitwise inner product mod } 2)$$

$$|\psi_3\rangle = \frac{1}{8}\sum_{z=0}^{7}\left[\sum_{x=0}^{7}(-1)^{f(x)+x\cdot z}\right]|z\rangle$$

**Interference:** Constructive (positive) and destructive (negative) interference occurs.

#### Step 5: Measurement and Decision

- **Constant function** → all interference is constructive for $|z=0\rangle = |000\rangle$ → **measure $|000\rangle$**
- **Balanced function** → amplitude at $|000\rangle$ = 0 (destructive) → **measure $\neq |000\rangle$**

| Measurement | Conclusion |
|:---:|:---:|
| All qubits = 0 ($\|000\rangle$) | $f$ is **Constant** |
| Any qubit = 1 | $f$ is **Balanced** |

---

### Q36. Derive the mathematical representation of the Deutsch Algorithm from the initial state through Hadamard transformation, oracle operation, and final measurement. **(6M)**

**Answer:**

#### Complete Mathematical Derivation of Deutsch's Algorithm

**Setup:** $f : \{0,1\} \to \{0,1\}$. Two qubits used: input $|0\rangle$ and ancilla $|1\rangle$.

$$|\psi_0\rangle = |0\rangle|1\rangle$$

In computational basis: $|01\rangle = \begin{bmatrix}0\\1\\0\\0\end{bmatrix}$

---

#### Stage 1: Apply $H^{\otimes 2}$ (Hadamard on both qubits)

$$H|0\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}, \quad H|1\rangle = \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

$$|\psi_1\rangle = H|0\rangle \otimes H|1\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}} \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

$$= \frac{1}{2}(|0\rangle+|1\rangle)(|0\rangle-|1\rangle) = \frac{1}{2}(|00\rangle - |01\rangle + |10\rangle - |11\rangle)$$

---

#### Stage 2: Apply Oracle $U_f$

$$U_f|x,y\rangle = |x, y\oplus f(x)\rangle$$

Substituting $|\psi_1\rangle$ into the oracle:
$$|\psi_2\rangle = \frac{1}{2}\sum_{x=0}^{1}|x\rangle\cdot(|0\oplus f(x)\rangle - |1\oplus f(x)\rangle)$$

**Key identity (Phase Kickback):**
$$|0\oplus f(x)\rangle - |1\oplus f(x)\rangle = (-1)^{f(x)}(|0\rangle - |1\rangle)$$

Therefore:
$$|\psi_2\rangle = \frac{1}{\sqrt{2}}\left[(-1)^{f(0)}|0\rangle + (-1)^{f(1)}|1\rangle\right] \otimes \frac{|0\rangle-|1\rangle}{\sqrt{2}}$$

---

#### Stage 3: Apply Hadamard to First Qubit

Since $H\left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right) = |0\rangle$ and $H\left(\frac{|0\rangle-|1\rangle}{\sqrt{2}}\right) = |1\rangle$:

**If $f$ is constant ($f(0)=f(1)$):**

Both phases equal → input part = $\pm\frac{|0\rangle+|1\rangle}{\sqrt{2}}$

$$H\left(\frac{|0\rangle+|1\rangle}{\sqrt{2}}\right) = |0\rangle$$

**→ First qubit = $|0\rangle$ → Measurement yields $\mathbf{0}$ → CONSTANT**

**If $f$ is balanced ($f(0) \neq f(1)$):**

Phases are opposite → input part = $\pm\frac{|0\rangle-|1\rangle}{\sqrt{2}}$

$$H\left(\frac{|0\rangle-|1\rangle}{\sqrt{2}}\right) = |1\rangle$$

**→ First qubit = $|1\rangle$ → Measurement yields $\mathbf{1}$ → BALANCED**

---

#### Summary Table: All 4 Functions

| $f(0)$ | $f(1)$ | Type | After Phase Kickback | After $H$ | Measurement |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | Constant | $+\frac{\|0\rangle+\|1\rangle}{\sqrt{2}}$ | $\|0\rangle$ | $\mathbf{0}$ |
| 1 | 1 | Constant | $-\frac{\|0\rangle+\|1\rangle}{\sqrt{2}}$ | $\|0\rangle$ (global phase) | $\mathbf{0}$ |
| 0 | 1 | Balanced | $\frac{\|0\rangle-\|1\rangle}{\sqrt{2}}$ | $\|1\rangle$ | $\mathbf{1}$ |
| 1 | 0 | Balanced | $-\frac{\|0\rangle-\|1\rangle}{\sqrt{2}}$ | $\|1\rangle$ (global phase) | $\mathbf{1}$ |

**Conclusion:** The Deutsch algorithm determines constant vs. balanced with a **single oracle evaluation**, achieving a quantum speedup over the classical 2-evaluation requirement.

---

# END OF ANSWER NOTES

---

> **Flagged Items — Not Covered / Ambiguous in Notes:**
>
> - **Q6 (Unit 1, Section-I, 2M):** The question text is **missing/blank** in the scanned Question Bank PDF. The corresponding content cannot be identified. Please refer to the original printed QB.
>
> - **Q28 (Unit 2, Section-II, 6M) — "Relationship" essay:** The notes do not contain an explicit combined discussion of all three topics (No-Cloning + Teleportation + Bell's Inequality) in a single dedicated section. The answer provided above is constructed by integrating the three separate treatments found across Unit 2 pages 1–18, strictly using the notes' own terminology and results.

---

*Document prepared from handwritten class notes: Unit 1 (20 pages), Unit 2 (18 pages), Unit 3 (9 pages). All notation, derivations, and examples are sourced exclusively from those notes.*
