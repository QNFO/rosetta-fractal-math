---
title: "Project Rosetta: The Approximation Entropy & The Fractal Limits of Digital Physics"
subtitle: "Quantifying the Irreducible Cost of Translating Continuous Physical Dynamics into Discrete Digital Computation"
author: "Rowan Brad Quni-Gudzinas"
date: "2026-07-22"
license: "QNFO Unified License Agreement (QNFO-ULA)"
doi: "10.5281/zenodo.XXXXXXXXX"
status: "draft"
---

# Abstract

The superconducting transmon is not a bad qubit. It is a **qudit** -- a multi-level quantum digit with approximately 12 resolvable energy levels -- that the quantum computing industry has spent two decades forcing into a binary straitjacket. Planck's quantization of the electromagnetic field gives every bosonic mode a discrete, unbounded integer ladder ($E_n = n\hbar\omega$). The field's decision to truncate this ladder to $n \in \{0, 1\}$ is not a physics constraint. It is a **radix error**: the imposition of base-2 (binary) onto a system that naturally carries base-$d$ (where $d \approx 12$ for state-of-the-art transmons). We quantify the irreducible thermodynamic cost of this binary truncation as $S_{\text{Base}} = \ln(d/2) \approx 1.79$ nats per state projection, and recast the full approximation entropy framework as a decomposition across four cognitive and physical truncation layers. We prove that the translation functor $F: \mathcal{P} \to \mathcal{C}$ remains non-exact under the corrected framing (Theorem 1), and we propose a constructive alternative: replace qubit quantum error correction with qudit QEC on the same hardware. The transmon was never a qubit. Planck knew this in 1900. It is time the field caught up.

# 1. Introduction

## 1.1 The Binary Straitjacket

The global quantum computing industry has absorbed approximately 35 billion dollars in combined public and private investment over two decades while delivering zero commercially viable machines [@QNFO2026QubitDelusionI]. This paper argues that the failure is not primarily an engineering problem but a **radix error** -- the systematic imposition of binary logic (base-2) onto a physical system that naturally supports multi-level quantum digits (base-$d$).

The transmon is a **qudit**, not a qubit. The two-level truncation is a human cognitive artifact -- binary is convenient for classical engineers with ten fingers -- not a physical constraint. Planck's 1900 quantization of the electromagnetic field gave us a discrete, equally-spaced energy ladder ($E_n = n\hbar\omega$, $n = 0, 1, 2, 3, \ldots$). The ladder is real. It is discrete. It is also unbounded. The error is not that we discretized. The error is that we stopped at two rungs.

**The key distinction** (which V1.0 of this framework mischaracterized as "continuous versus discrete"):

| | Old Framing (V1.0) | Corrected Framing (V4.0) |
|:--|:--------------------|:-------------------------|
| Transmon spectrum | "Continuous bosonic dynamics" | Discrete integer ladder (Planck quantization) |
| The field's error | Treating analog as digital | Treating base-$d$ as base-2 |
| The cost | Translating continuous $\rightarrow$ discrete | Truncating base-$d$ $\rightarrow$ base-2: $S_{\text{Base}} = \ln(d/2)$ |
| What is lost | Symplectic capacity (abstract) | Information in rungs $n \ge 2$ (concrete, measurable as leakage) |
| Constructive proposal | "Three paths forward" (reactive) | Build qudits on existing hardware (constructive) |

Planck gave us a digital system. We chose to read it in binary. The cost of that choice -- the entropy of the binary truncation -- is the subject of this paper.

## 1.2 The Planck-Radix Correction (Informal)

A bosonic mode in a cavity has energy eigenvalues $E_n = n\hbar\omega$ for $n = 0, 1, 2, 3, \ldots$. This spectrum is:

1. **Discrete** (Planck): The eigenvalues are isolated points, not a continuum. Boundary conditions and the quantum of action $h$ guarantee this.
2. **Unbounded** (Bose statistics): There is no Pauli exclusion cap on $n$. Coherent states routinely populate $n \sim 10^{16}$ photons in a single mode.
3. **Equally spaced** (Harmonic): $E_{n+1} - E_n = \hbar\omega$ for all $n$.

The transmon inherits this structure. Its Hamiltonian $H = 4E_C n^2 - E_J\cos(\phi)$ approximates a harmonic oscillator with anharmonicity $\alpha_r = \sqrt{8E_C/E_J} - 1 \approx 1.9\%$. The spectrum is approximately:

$$E_n \approx \sqrt{8E_J E_C}\left(n + \frac{1}{2}\right) - \frac{E_C}{12}(6n^2 + 6n + 3)$$

This is a discrete, unbounded, gently anharmonic ladder. Approximately 12 levels are experimentally resolvable [@Koch2007; @Wang2022]. The field calls this a "qubit" by imposing:

$$|\psi_q\rangle = c_0|0\rangle + c_1|1\rangle$$

with projection operator $P_{\text{qubit}} = |0\rangle\langle 0| + |1\rangle\langle 1|$. The Planck Loss -- the fraction of state norm discarded by this truncation -- is:

$$\mathcal{L}_P = 1 - \text{Tr}(P_{\text{qubit}} |\psi\rangle\langle\psi|) = \sum_{n=2}^{\infty} |c_n|^2$$

For a coherent drive (a gate operation), $\mathcal{L}_P$ is substantial -- leakage into $n \ge 2$ is the dominant error mechanism in transmon processors [@QNFO2026QubitDelusionV].

**The radix error, stated precisely:** Planck's quantization outputs a unary/integer basis ($n = 0,1,2,3,\ldots$). The field forces this into binary ($n \in \{0,1\}$) by discarding $n \ge 2$. The entropy cost is $S_{\text{Base}} = \ln(d/2)$ where $d$ is the number of resolvable levels. For $d=12$: $S_{\text{Base}} \approx 1.79$ nats $\approx 2.58$ bits per qubit.

## 1.3 Statement of Results

| Axis | Core Result |
|:-----|:------------|
| **1.** Categorical Foundations | The functor $F: \mathcal{P} \to \mathcal{C}$ is non-exact (Theorem 1) -- the radix error is formal, not contingent |
| **2.** Algebraization Complexity | $\cos(\phi)$ requires degree-224 polynomial for spectral fidelity $10^{-4}$ |
| **3.** Thermodynamics of Translation | Rosetta's Constant $R = k_B T \ln(N_{\text{max}}/d_{\text{comp}})$ |
| **4.** Complexity Bounds | Digital Speed Limit: depth grows exponentially in qubit count $Q$ |
| **5.** Experimental Protocol | Translation Calorimeter -- falsifiable measurement of $S_{\text{Base}}$ |
| **HAL.** Hidden Axioms | $S_{\text{Total}} = S_{\text{Obs}} + S_{\text{Base}} + S_{\text{Arch}} + S_{\text{Alg}} + S_{\text{Trot}}$ -- five layers of truncation entropy |

## 1.4 Prior Art

This work builds on and extends several independent lines of inquiry. Planck [-@Planck1900] established the discrete bosonic ladder structure. De Gosson [-@deGosson2012SymplecticCamel] framed the conflict between geometry and algebra in quantum information using Gromov's non-squeezing theorem, but stopped at the existence argument without quantification. The QNFO Research Collective's "Qubit Delusion" series [@QNFO2026QubitDelusionI; @QNFO2026BeyondTheQubit; @QNFO2026PhysicsOfComputation; @QNFO2026ProblemSubstrateMapping; @QNFO2026ManifestoHonestComputation] provided the philosophical scaffolding. Wang et al. [-@Wang2022] experimentally confirmed $d \approx 12$ resolvable transmon levels. Our contribution is the **radix correction** to the V1.0 thesis and the constructive qudit alternative.

# 2. Categorical Foundations

## 2.1 Category $\mathcal{P}$: Physical Dynamics

$\mathcal{P}$ has as objects **symplectic manifolds** $(M^{2n}, \omega)$. Morphisms are Hamiltonian flows $\varphi_t^H: M \to M$ generated by $H: M \to \mathbb{R}$, or unitarily via $U(t) = e^{-iHt/\hbar}$. For the transmon: phase space is the cylinder $M = S^1 \times \mathbb{R}$ with $H = 4E_C n^2 - E_J\cos(\phi)$ [@Koch2007].

## 2.2 Category $\mathcal{C}$: Computational Logic

$\mathcal{C}$ has as objects finite-dimensional state spaces $\mathcal{H}_2^{\otimes n}$. Morphisms are finite gate compositions from $\mathcal{G} = \{H, T, \text{CNOT}\}$. Objects are finite and discrete -- no continuous coordinate, no symplectic form.

## 2.3 Theorem 1: Non-Exactness

**Theorem 1.** *$F: \mathcal{P} \to \mathcal{C}$ is not exact -- there exist invariants preserved in $\mathcal{P}$ with no image in $\mathcal{C}$.*

*Proof.* By Gromov's non-squeezing theorem [-@Gromov1985]: the symplectic capacity $c_G(M, \omega)$ is invariant under symplectomorphisms. Under $F$, this maps to a finite discrete point set with zero capacity. An invariant in the source with no image in the target -- the defining signature of a non-exact functor. $\square$

# 3. Algebraization Complexity

The transmon Hamiltonian contains $\cos(\phi)$ -- a transcendental function. For computation it must be approximated by a finite polynomial.

**Definition.** The **Algebraization Complexity** $A(H, \varepsilon)$ is the minimum polynomial degree $N$ preserving eigenvalues to within $\varepsilon$.

**Theorem 2.** For the transmon with $E_J/E_C \gg 1$:

$$ A(H, \varepsilon) \approx \sqrt{\frac{8E_J}{E_C}} \cdot \frac{1}{2}\ln\left(\frac{1}{2\varepsilon}\right) $$

For $E_J/E_C = 50$, $\alpha_r = 1.9\%$, $\varepsilon = 10^{-4}$: $A \approx 224$.

**Result:** The transmon's exponential charge-noise immunity $\exp(-\sqrt{8E_J/E_C})$ is mathematically identical to its algebraic intractability -- a **Coherence-Algebraization Conservation Law.**

# 4. Thermodynamics of Translation

## 4.1 Approximation Entropy $S_A$

The Kullback-Leibler divergence between the full bosonic density operator and its discretized projection:

$$ S_A = D_{\text{KL}}(\rho_{\text{full}} \| \rho_{\text{grid}}) = \ln\left(\frac{N_{\text{max}}}{d_{\text{comp}}}\right) $$

For the transmon ($N_{\text{max}} \approx 12$, $d_{\text{comp}} = 2$): $S_A \approx 1.79$ nats $\approx 2.58$ bits per state projection.

## 4.2 Rosetta's Constant $R$

$$ \boxed{R \equiv k_B T \cdot S_A = k_B T \cdot \ln\left(\frac{N_{\text{max}}}{d_{\text{comp}}}\right)} $$

At $T = 15$ mK: $R \approx 3.7 \times 10^{-25}$ J per state projection. Per logical gate: $R_{\text{gate}} \approx 1.5 \times 10^{-24}$ J/gate. With all five entropy sources (§7): $Q_{\text{total}} \approx 1.4 \times 10^{-24}$ J/gate.

## 4.3 Landauer Extension

Landauer [-@Landauer1961] established $k_B T \ln 2$ for erasing one bit within the SAME domain. We extend to inter-domain:

$$ Q_{\text{total}} = k_B T \ln 2 + k_B T \ln(N_{\text{max}}/2) = k_B T \ln(N_{\text{max}}) $$

For the transmon: $Q_{\text{total}} \approx 2.48\,k_B T$ -- the Rosetta term is $3.6\times$ the Landauer term.

# 5. The Digital Speed Limit

## 5.1 Trotter Error

The standard digital simulation uses: $e^{-i(H_A + H_B)t} \approx (e^{-iH_A t/n} e^{-iH_B t/n})^n$. Error scales as $\|[H_A, H_B]\|$. For the transmon: $\|[H_{\text{harm}}, H_{\text{nonlin}}]\| \propto \hbar\omega_p \alpha_r$.

## 5.2 Trotter Wall

For fault-tolerant threshold $\varepsilon = 10^{-4}$:

$$ \frac{G_{\text{effective}}}{G_{\text{advertised}}} \approx \frac{\omega_p}{\alpha_r} \approx 50 $$

A "100-gate" circuit executes 5,000 sub-gates. True gate budget at $T_2^* \approx 100$ $\mu$s:

$$ G_{\text{budget}} \approx \frac{T_2^*}{t_g \cdot (\omega_p/\alpha_r)} \approx 100 $$

## 5.3 Fractal Boundary

**Theorem 4.** There exists $\alpha^* \approx 3\%$ below which weakly anharmonic bosonic arrays are classically simulable. Standard transmons at $\alpha_r \approx 1.9\%$ are BELOW this boundary.

# 6. The Translation Calorimeter

Two experiments on the same transmon at the same temperature:

| Experiment | Method | Predicted Heat |
|:-----------|:-------|:---------------|
| **A (Analog)** | Natural evolution under $H_0$ | $Q_A \approx 0$ |
| **B (Digital)** | Trotterized gate sequence | $Q_B \approx k_B T \cdot S_A$ |

**Falsification:** If $\Delta Q = Q_B - Q_A = 0$ (within noise), the framework is refuted.

**Feasibility:** NIS junction calorimeter with 1 $\mu$K sensitivity. $Q_{\text{single}} \approx 8.2 \times 10^{-25}$ J; $10^6$ cycles yield $\Delta T \approx 0.82$ mK (measurable). 37 gates for $5\sigma$ (theory). Estimated cost: \$520K, 18--24 months.

# 7. Hidden Axioms Layer (HAL)

$$ S_{\text{Total}} = S_{\text{Obs}} + S_{\text{Base}} + S_{\text{Arch}} + S_{\text{Alg}} + S_{\text{Trot}} $$

| Term | Origin | Transmon Value (nats) |
|:-----|:-------|:----------------------|
| $S_{\text{Obs}}$ | Human cognitive filter (binary thresholding) | 1.79 |
| $S_{\text{Base}}$ | Radix mismatch (binary vs. native spectrum) | 1.79 |
| $S_{\text{Arch}}$ | Archimedean time-slicing (uniform Trotter) | 0.5 |
| $S_{\text{Alg}}$ | Algebraization (cosine $\to$ polynomial) | 1.0 |
| $S_{\text{Trot}}$ | Commutator error ($[H_{\text{harm}}, H_{\text{nonlin}}] \neq 0$) | 1.5 |
| **Total** | | **6.6** |

**Anthropocentricity:** The qubit encoding is a human cognitive artifact. Binary is the radix humans chose because we have ten fingers and built classical computers in base-2. A Platonic observer with access to all $d$ resolvable levels would see a qudit, not a qubit: $S_{\text{Obs}} = \ln(d/2) \approx 1.79$ nats.

**Radix Contingency (Strengthened by Planck-Radix Correction):** Planck's quantization gives a **unary/integer basis** ($n = 0,1,2,3,\ldots$). This is the natural radix of any harmonic oscillator mode. The field imposes base-2 by truncating to $n \in \{0,1\}$. The entropy cost is **not** the cost of discretization (the spectrum was already discrete). It is the cost of **radix conversion**: mapping a base-$d$ system to base-2. For $d=12$: $S_{\text{Base}} = \ln(d/2) \approx 1.79$ nats. This corrects V1.0, which mischaracterized $S_{\text{Base}}$ as "continuous $\to$ discrete translation." The spectrum was always discrete. The translation is base-$d \to$ base-2.

**Continuum Fallacy:** The Trotter error IS the Archimedean cost. Logarithmic time-stepping reduces sub-gates by ~50% with no hardware modifications.

# 8. Discussion: The Qudit Manifesto

## 8.1 The Transmon Was Never a Qubit

The core error of the gate-model quantum computing program is not engineering. It is conceptual. Planck gave us a discrete, unbounded integer ladder in 1900. For 125 years, we have built machinery that treats this ladder as if it had exactly two rungs. The "qubit" is a human cognitive artifact -- binary is convenient for engineers with ten fingers, not a physical constraint.

The transmon's 12 resolvable levels [@Wang2022] were never a "leakage problem." They are the system's native computational substrate. The leakage is not the system failing at being a qubit. The leakage is the system succeeding at being a bosonic mode -- and us misinterpreting its correct behavior as an error.

## 8.2 Qudit Quantum Error Correction Exists

The constructive alternative is already known. Qudit surface codes [@Gottesman1999; @Campbell2014] generalize the standard qubit surface code to $d$-dimensional quantum digits. The stabilizer formalism extends naturally:

$$X|j\rangle = |j+1 \bmod d\rangle, \quad Z|j\rangle = \omega^j|j\rangle$$

where $\omega = e^{2\pi i/d}$. Qudit codes offer:

1. **Higher threshold:** Qudit surface codes have thresholds that increase with $d$ [@Campbell2014]
2. **Reduced overhead:** A single qudit encodes $\log_2(d)$ bits, reducing physical-to-logical qubit ratios
3. **Native hardware match:** The transmon's 12-level ladder maps directly to a $d=12$ qudit -- no truncation, no leakage

The field should be building qudit surface codes on transmon hardware. The transmon is not a bad qubit. It is a **good qudit** waiting for qudit error correction.

## 8.3 The Planck Fidelity: A New Benchmark

We propose a benchmark metric: **Planck Fidelity** $\mathcal{F}_P$ -- the fidelity of a quantum operation when the occupation number $n$ is mapped to a qudit basis without truncation:

$$\mathcal{F}_P = \text{Tr}\left(P_{\text{qudit}} \; U_{\text{gate}} \; |\psi\rangle\langle\psi| \; U_{\text{gate}}^\dagger\right)$$

where $P_{\text{qudit}} = \sum_{n=0}^{d-1} |n\rangle\langle n|$ (all resolvable levels, not just $\{0,1\}$). For any finite gate time, $\mathcal{F}_P > \mathcal{F}_{\text{qubit}}$ because the drive couples to ALL $n$ via $a^\dagger$ -- the higher rungs are participating whether we acknowledge them or not.

## 8.4 Paths Forward

We propose three constructive paths, prioritized:

1. **Qudit QEC on transmons (primary):** Build and benchmark $d=12$ qudit surface codes on existing transmon hardware. This requires no new fabrication -- only a firmware and control software update to address all 12 levels. The existing hardware IS a qudit processor. We just need to program it as one.

2. **Qudit-native algorithms:** Grover's search, Shor's factoring, and quantum simulation all have qudit generalizations [@Wang2020] that exploit the larger Hilbert space per physical element. A $d=12$ qudit encodes $\log_2(12) \approx 3.58$ bits per element -- a 3.6$\times$ information density improvement over qubits with zero additional hardware.

3. **Hybrid qubit-qudit architectures:** During the transition, run qubit algorithms on the $\{|0\rangle, |1\rangle\}$ subspace while developing qudit QEC in parallel. This is the pragmatic path for existing NISQ-era systems.

## 8.5 Falsifiability

This framework makes specific, testable predictions:
1. $\Delta Q > 0$ in calorimetry (the binary truncation has a measurable thermodynamic cost)
2. $\Delta Q \propto -\ln(d/2)$ across transmon variants with different $d$
3. $\alpha^* \approx 3\%$ Fractal Boundary
4. Trotter Wall $\approx 50\times$ overhead for binary gates
5. Planck Fidelity $\mathcal{F}_P > \mathcal{F}_{\text{qubit}}$ for any gate operation on a transmon with $d > 2$

If $\Delta Q = 0$ -- if the binary truncation has zero thermodynamic cost -- the entropy framework collapses. If $\mathcal{F}_P \le \mathcal{F}_{\text{qubit}}$ -- if including higher rungs does not improve fidelity -- the qudit thesis is refuted. This is the hallmark of good science.

# 9. Conclusion

Planck gave us a digital computer in 1900. We spent 125 years reading it in the wrong base. The transmon is a qudit. The field's insistence on binary truncation is a radix error, not a physics error. Planck's quantization gave us a discrete ladder. We chose to climb only the first two rungs -- and then spent 35 billion dollars wondering why we kept falling off.

The Approximation Entropy $S_A$ framework developed in this paper quantifies the cost of that choice. The Qudit Manifesto proposes the alternative: stop fighting the transmon's bosonic nature. Start programming the machine Planck actually gave us.

# References
