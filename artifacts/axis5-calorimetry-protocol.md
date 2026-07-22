# Axis 5: The Translation Calorimeter — Experimental Protocol
## Project Rosetta — rosetta-fractal-math

**Date:** 2026-07-22
**Status:** Phase 4 Deep Research — Draft
**Related:** Axis 1 (Theory), Axis 3 (S_A Thermodynamics), Axis 4 (Complexity Bounds)

---

## 1. Motivation

Axes 1–4 provide theoretical arguments that \(S_A > 0\) — that translating continuous bosonic dynamics into discrete digital gates carries an irreducible thermodynamic cost. **Theory is necessary; experiment is dispositive.**

Axis 5 proposes a direct, falsifiable experiment: measure the differential heat between "analog native evolution" and "digital gate translation" for the same unitary operation on a single transmon.

---

## 2. The Translation Calorimeter Concept

### 2.1 Core Idea

Two experiments on the **same** transmon, at the **same** dilution fridge temperature (15 mK), executing the **same** unitary rotation \(U\):

| Experiment | Method | Expected Heat |
|:---|:---|:---|
| **A (Analog/Native)** | Let transmon evolve under its natural Hamiltonian \(H_0\) for time \(\tau\), no gates, no drives | \(Q_A \approx 0\) (unitary evolution) |
| **B (Digital/Translated)** | Execute gate sequence \(\{G_1, G_2, ..., G_K\}\) that approximates \(e^{-iH_0\tau}\) with DRAG pulses, Trotter decomposition, and readout | \(Q_B \approx k_B T \cdot S_A\) |

**Prediction:** \(Q_B - Q_A \approx k_B T \cdot \ln(1/\alpha_r) \approx 4 k_B T \approx 8.3 \times 10^{-24}\) J per logical translation.

### 2.2 Falsification Criterion

\[
\boxed{\text{If } Q_B - Q_A = 0 \text{ (within experimental noise floor), the Rosetta framework is falsified.}}
\]

If the digital translation is **exact** — carrying zero additional thermodynamic cost beyond bit erasure — then \(S_A = 0\) and the functor \(F: \mathcal{P} \to \mathcal{C}\) is exact. The entire Rosetta thesis collapses to the standard model of quantum computation.

---

## 3. Experimental Design

### 3.1 Hardware Requirements

| Component | Specification | Rationale |
|:---|:---|:---|
| Transmon qubit | \(E_J/E_C = 50\), \(\alpha_r = 1.9\%\), \(T_1 > 100\ \mu\text{s}\), \(T_2^* > 50\ \mu\text{s}\) | Industry-standard coherence; \(\alpha_r\) low enough for S_A to be measurable |
| Dilution fridge | Base temperature \(T_b \leq 15\) mK, cooling power \(\geq 10\ \mu\text{W}\) at 100 mK | Must resolve differential heat at \(10^{-23}\) J scale |
| Calorimeter | Sensitivity \(\delta Q \leq 10^{-24}\) J, bandwidth \(\geq 1\) GHz | Nanosecond gate times require fast calorimetry |
| Control electronics | DRAG-calibrated pulses, arbitrary waveform generators | Standard transmon control stack |

### 3.2 Calorimeter Architecture

**Option 1: Normal-Insulator-Superconductor (NIS) Junction Calorimeter**

A NIS junction acts as a primary thermometer with sensitivity \(\delta T \sim 1\ \mu\text{K}\). The heat deposited in the electron bath raises the electronic temperature, which is read out via the NIS junction's current-voltage characteristic. This is the state-of-the-art for quantum thermodynamics experiments (Pekola group, Aalto).

**Option 2: Resonator-Based Calorimetry**

A superconducting LC resonator capacitively coupled to the transmon. The resonator's quality factor \(Q\) is sensitive to quasiparticle generation in the transmon, which proxies for heat dissipation. Changes in \(Q\) (or resonance frequency shift) are measured via reflectometry.

**Option 3: Quantum Non-Demolition (QND) Energy Measurement**

Repeated QND measurements of the transmon's energy before and after the gate sequence. The energy difference \(\Delta E\) between the pre- and post-gate state, averaged over \(10^6\) cycles, gives \(Q_B\). This is measurement-based calorimetry — no direct heat sensor needed.

**Recommended: Hybrid NIS + QND Approach**

- NIS junction for absolute temperature calibration
- QND energy measurement for shot-by-shot statistics
- Cross-validation between the two methods

### 3.3 Signal Estimation

For a single gate at 15 mK:

\[
Q_{\text{single}} \approx k_B T \cdot \ln(1/0.019) \approx 1.38 \times 10^{-23} \cdot 0.015 \cdot 3.97 \approx 8.2 \times 10^{-25} \text{ J}
\]

For \(N = 10^6\) gate repetitions (a typical averaging experiment lasting ~1 ms):

\[
Q_{\text{total}} \approx N \cdot 8.2 \times 10^{-25} \approx 8.2 \times 10^{-19} \text{ J}
\]

At 15 mK, this corresponds to a temperature rise:

\[
\Delta T \approx \frac{Q_{\text{total}}}{C_e} \quad \text{where } C_e \approx 10^{-15} \text{ J/K (electron heat capacity at 15 mK)}
\]

\[
\Delta T \approx 8.2 \times 10^{-4} \text{ K} = 0.82 \text{ mK}
\]

This is **measurable** with NIS junction thermometry (sensitivity ~1 μK) but requires careful subtraction of systematic heating (RF drive lines, amplifier noise).

### 3.4 Noise and Systematics

| Source | Magnitude | Mitigation |
|:---|:---|:---|
| RF drive heating | Comparable to signal | Use minimum-power DRAG pulses; measure drive power at cold stage |
| Amplifier back-action | ~10^-24 J per photon | Use Josephson Parametric Amplifier (JPA) with near-quantum-limited noise |
| Quasiparticle poisoning | ~10^-22 J per QP tunneling event | Shield from infrared; use quasiparticle traps |
| Fridge temperature drift | ~0.1 mK/hour | Active temperature stabilization; differential measurement (A vs B interleaved) |
| Gate leakage to higher levels | Additional S_A contribution | Include in model; actually part of the signal |

### 3.5 Statistical Power

To achieve \(5\sigma\) significance against the null hypothesis (\(S_A = 0\)):

\[
N_{\text{cycles}} \geq \left(\frac{5 \cdot \sigma_{\text{noise}}}{Q_{\text{single}}}\right)^2
\]

Assuming noise floor \(\sigma_{\text{noise}} \approx 10^{-24}\) J (limited by amplifier back-action):

\[
N_{\text{cycles}} \geq \left(\frac{5 \cdot 10^{-24}}{8.2 \times 10^{-25}}\right)^2 \approx 37
\]

This is remarkably small — **only 37 gate cycles needed at \(5\sigma\)** if the noise floor holds. In practice, systematic errors dominate. A conservative estimate: \(10^6\) cycles interleaved between Experiments A and B, with the entire sequence repeated 100 times for statistical robustness.

**Total experiment time:** ~100 seconds (dominated by fridge thermalization between cycles, not gate times).

---

## 4. Protocol Sequence

### Step 1: Calibration

1. Calibrate NIS thermometer against a known heat pulse (resistive heater on the mixing chamber)
2. Characterize RF drive line attenuation — measure actual power delivered to the transmon vs. power at room-temperature source
3. Measure qubit \(T_1\), \(T_2^*\), and higher-level populations via standard readout

### Step 2: Experiment A (Analog/Native Evolution)

1. Prepare the transmon in \(\left|0\right\rangle\) (or \(\left|1\right\rangle\))
2. Let it evolve under \(H_0 = 4E_C n^2 - E_J\cos(\phi)\) for time \(\tau\), with NO microwaves applied
3. Measure final state (tomography) and residual heat via calorimeter
4. Record \(Q_A\) (expected: near zero, dominated by \(T_1\) relaxation)
5. Repeat \(10^5\) times, varying \(\tau\)

### Step 3: Experiment B (Digital Gate Translation)

1. Prepare the transmon in the same initial state as Experiment A
2. Execute the Trotterized gate sequence \(\{G_1, ..., G_K\}\) approximating \(e^{-iH_0\tau}\)
   - Gates: each requires DRAG-calibrated microwave pulse
   - Trotter steps: \(n = 50\) per logical evolution (from Axis 4)
   - Readout: standard dispersive readout
3. Measure final state (must match A within statistical error) and residual heat
4. Record \(Q_B\)
5. Repeat \(10^5\) times

### Step 4: Differential Analysis

\[
\Delta Q = Q_B - Q_A
\]

If \(\Delta Q > 0\) and \(\Delta Q \propto \ln(1/\alpha_r)\) across multiple transmons with different \(E_J/E_C\):

→ **Rosetta Framework Confirmed**

If \(\Delta Q = 0\) (within noise):

→ **Rosetta Framework Falsified** — digital translation is exact for bosonic systems

### Step 5: Scaling Verification

Repeat Steps 1–4 for transmons with different anharmonicities:
- Low anharmonicity: \(\alpha_r \approx 1\%\) (charge-sensitive transmon, \(E_J/E_C \approx 200\))
- Standard: \(\alpha_r \approx 1.9\%\) (\(E_J/E_C \approx 50\))
- High anharmonicity: \(\alpha_r \approx 5\%\) (fluxonium-like, \(E_J/E_C \approx 5\))

Verify: \(\Delta Q \propto -\ln(\alpha_r)\) — the Rosetta scaling law.

---

## 5. Expected Results Under Rosetta Hypothesis

| \(\alpha_r\) | \(E_J/E_C\) | Predicted \(S_A\) (bits/gate) | Predicted \(\Delta Q\) (10^-25 J) |
|:---|:---|:---|:---|
| 1.0% | 200 | 6.6 | 13.7 |
| 1.9% | 50 | 4.0 | 8.2 |
| 5.0% | 5 | 1.8 | 3.7 |
| 15% | 0.6 | 0.4 | 0.8 |

The scaling should be approximately: \(\Delta Q \propto -\ln(\alpha_r)\).

---

## 6. Observer Variation Extension (HAL-Axiom 1)

As specified in the HAL v2.0 framework, the experiment should be extended to include **two observer perspectives:**

### Observer A (Human-Digital)
- Reads binary bit values (0/1 thresholded from homodyne voltage)
- Uses standard digital post-processing
- Measures \(Q_A\)

### Observer B (Platonic-Continuous)
- Uses quantum non-demolition measurement of the full Wigner function
- No thresholding — retains continuous phase information
- Measures \(Q_B\) (expected: lower than \(Q_A\) by \(S_{\text{Obs}}\))

**The difference \(Q_A - Q_B = k_B T \cdot S_{\text{Obs}}\) is the Anthropic Heat** — the thermodynamic cost of forcing the transmon's continuous dynamics into human-readable binary output.

---

## 7. Falsifiability Summary

| Claim | Falsification Condition |
|:---|:---|
| \(S_A > 0\) | \(\Delta Q = 0\) within noise (\(5\sigma\)) |
| \(S_A \propto -\ln(\alpha_r)\) | \(\Delta Q\) independent of \(\alpha_r\) |
| \(S_{\text{Obs}} > 0\) | \(Q_A - Q_B = 0\) for Observer A vs B protocols |
| Rosetta's Constant \(R\) | \(\Delta Q\) does not match \(k_B T \ln(1/\alpha_r)\) |

**If ANY of these falsification conditions are met, the corresponding Rosetta claim is refuted.** This is the hallmark of good science: the theory tells you exactly what would prove it wrong.

---

## 8. Resource Estimate

| Item | Cost (USD) | Lead Time |
|:---|:---|:---|
| NIS junction calorimeter | $50,000 | 6 months (fabrication) |
| Transmon chip (3 variants) | $30,000 | 3 months (foundry) |
| Dilution fridge upgrade (additional wiring/thermometry) | $100,000 | 6 months |
| Control electronics (AWGs, digitizers) | $80,000 | 2 months |
| Cryogenic amplifiers (JPAs) | $60,000 | 4 months |
| Personnel (1 postdoc, 2 years) | $200,000 | — |
| **Total** | **~$520,000** | **18–24 months** |

---

## References

1. **Pekola, J.P. et al.** (2013) "Single-electron current sources: towards a refined definition of the ampere" — Rev. Mod. Phys. 85, 1421
2. **Ronzani, A. et al.** (2018) "Tunable photonic heat transport in a quantum heat valve" — Nature Physics 14, 991
3. **Koch, J. et al.** (2007) "Charge-insensitive qubit design" — Phys. Rev. A 76, 042319
4. **Blais, A. et al.** (2019) "Quantum bits with Josephson junctions" — arXiv:1908.09558
5. **Landauer, R.** (1961) "Irreversibility and Heat Generation in the Computing Process"
6. **QNFO Research Collective** (2026) "The Physics of Computation" — Qubit Delusion Phase III

---

*This protocol is an LLM-assisted experimental design. All numbers (noise floors, heat capacities, signal estimates) are order-of-magnitude calculations using published parameters. A full experimental proposal requires detailed device modeling and consultation with cryogenic experimentalists.*
