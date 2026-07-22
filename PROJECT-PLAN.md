# PROJECT ROSETTA — Project Plan & WBS

**Slug:** `rosetta-fractal-math`
**Full Title:** Project Rosetta: The Approximation Entropy & The Fractal Limits of Digital Physics
**Author:** Rowan Brad Quni-Gudzinas
**Date:** 2026-07-22
**Branch:** `feature/phase0-init`

---

## §0 — Project Charter

### Mission

To formalize and experimentally quantify the irreducible informational and thermodynamic cost of translating physical dynamics from their native continuous mathematical frameworks (differential geometry, functional analysis) into discrete digital computational logic (Boolean algebra, quantum circuits). We define this cost as **Approximation Entropy (S_A)** and propose that it is a fundamental physical invariant — not an engineering nuisance — that invalidates the assumption of universal digital computability for bosonic quantum systems.

### Vision

Establish a **new taxonomy of physical computation** that replaces the obsolete "digital vs. analog" dichotomy with a rigorous **mathematical-domain taxonomy**: Class I (Discrete-Fermionic), Class II (Continuous-Bosonic), Class III (Topological-Anyonic). Every quantum computer must publish its Approximation Entropy alongside its qubit count and gate fidelity.

### Scope

The program spans five independent research axes (see §5) and one unified publication synthesizing them. The superconducting transmon serves as the primary experimental case study, but the framework extends to any domain where continuous dynamics are forced into discrete representations (climate modeling, fluid dynamics, AI on digital hardware).

---

## §1 — Core Claim Lock

### §1.1 — Original Formulation (from genesis note, 2026-07-22)

> Digital computation is not a universal ontological framework; it is a specialized algebraic language suitable for discrete, countably finite systems. Natural quantum dynamics operates in continuous differential geometry and infinite-dimensional functional analysis. The translation between these incommensurable mathematical domains — the "digital translation" — carries an irreducible thermodynamic and informational cost, defined as Approximation Entropy (S_A). For bosonic systems, S_A ∝ ln(1/α_r), making digital fault-tolerant quantum computing exponentially more expensive than analog simulation.

### §1.2 — Logically Valid, Falsifiable Reformulation

**Core Thesis (F1):** There exists no exact, information-preserving functor F: P → C from the category of continuous dynamical systems (symplectic manifolds with Hamiltonian flows) to the category of finite discrete logic (Boolean algebras with quantum gates).

**Core Thesis (F2):** For any bosonic system with anharmonicity α_r, the digital circuit depth required to simulate its natural evolution for time T scales as exp(ω_p·T/α_r). This "digital speed limit" is independent of decoherence.

**Core Thesis (F3):** The thermodynamic cost of translating a continuous quantum state to a discrete register and back is Q_min = k_B·T·S_A, where S_A ≈ −ln(α_r) for weakly anharmonic systems.

**Falsification Conditions:**
- (F1) is falsified if a formal proof demonstrates that the symplectic area invariant (Gromov non-squeezing) is preserved under any finite-dimensional Boolean projection.
- (F2) is falsified if a digital gate decomposition is found that simulates the transmon Hamiltonian with circuit depth polynomial in T and α_r without Trotter error.
- (F3) is falsified if a calorimetric measurement (Axis 5) shows zero differential heat between analog evolution and digital gate translation for the same unitary operation.

---

## §2 — WBS (Work Breakdown Structure)

### Phase 0: Project Initialization [THIS PHASE]
| Task | Description | Status |
|------|-------------|--------|
| 0.1 | Repository & scaffold | ✅ |
| 0.2 | PROJECT-PLAN.md with charter, WBS, risks | ✅ |
| 0.3 | Core claim reformulated and locked | ✅ |
| 0.4 | KG/D1 cross-reference discovery | 🔄 |
| 0.5 | Source note copied to docs/ | Pending |
| 0.6 | GitHub repo created and pushed | Pending |
| 0.7 | Phase 0 closeout (commit, tag v0.1-phase0) | Pending |

### Phase 1: Due Diligence & Literature Search
| Task | Description |
|------|-------------|
| 1.1 | Query KG for related QNFO papers |
| 1.2 | Query D1/Vectorize for QNFO internal overlap |
| 1.3 | External search: arXiv, Semantic Scholar, web (5 parallel sources) |
| 1.4 | Deduplication and classification matrix |
| 1.5 | Gap analysis — confirm novelty |
| 1.6 | Phase 1 closeout, tag v0.2-phase1-dd |

### Phase 2: Categorical Foundations (Axis 1)
| Task | Description |
|------|-------------|
| 2.1 | Define Category P (Physical Dynamics): symplectic manifolds, Hamiltonian flows |
| 2.2 | Define Category C (Computational Logic): finite Hilbert spaces, quantum gates |
| 2.3 | Formalize Translation Functor F: P → C |
| 2.4 | Prove non-exactness via Gromov's non-squeezing theorem analog |
| 2.5 | Draft "The Non-Exactness of the Quantum-to-Digital Functor" whitepaper |

### Phase 3: Algebraization Complexity (Axis 2)
| Task | Description |
|------|-------------|
| 3.1 | Prove transcendental non-algebraizability of cos(φ) potential |
| 3.2 | Derive A(H) ∝ exp(√(8E_J/E_C)) — algebraic complexity metric |
| 3.3 | Show coherence vs. algebraizability conservation law |
| 3.4 | Produce complexity table for common physical potentials |

### Phase 4: Thermodynamics of Translation (Axis 3)
| Task | Description |
|------|-------------|
| 4.1 | Formal definition of S_A via Fisher information geometry |
| 4.2 | Derive Rosetta's Constant: R = k_B·T·ln(1/α_r) |
| 4.3 | Extend Landauer's principle to continuous→discrete translations |
| 4.4 | Compute S_A for transmon (α_r = 1.9%): ~4 bits/gate entropy |

### Phase 5: Complexity Bounds (Axis 4)
| Task | Description |
|------|-------------|
| 5.1 | Prove digital speed limit: depth ∝ exp(ω_p·T/α_r) |
| 5.2 | Identify Fractal Boundary α* where BQP vs. classical separation fails |
| 5.3 | Prove weakly anharmonic arrays (α < 3%) are classically simulable |

### Phase 6: Hidden Axioms Layer (HAL) — v2.0 Extension
| Task | Description |
|------|-------------|
| 6.1 | HAL-Axiom 1: Anthropocentric Observer-Selectivity — define Observer Topos |
| 6.2 | HAL-Axiom 2: Radix/Base Contingency — prove binary is worst base for bosons |
| 6.3 | HAL-Axiom 3: Archimedean/Cartesian Continuum Fallacy — non-Archimedean time |
| 6.4 | Unified total S_Total = S_Obs + S_Base + S_Arch + S_Alg + S_Trot |
| 6.5 | Draft "The Observer Topos" category-theoretic proof of human cognitive bias |

### Phase 7: Experimental Protocol (Axis 5)
| Task | Description |
|------|-------------|
| 7.1 | Design Translation Calorimeter experiment |
| 7.2 | Specify analog vs. digital heat differential measurement |
| 7.3 | Define falsification criterion: ΔQ = 0 → Framework falsified |
| 7.4 | Draft experimental protocol paper |

### Phase 8: Synthesis & Publication
| Task | Description |
|------|-------------|
| 8.1 | Synthesize all axes into 6-chapter paper |
| 8.2 | Publication Language Gate scan |
| 8.3 | Pandoc+XeLaTeX PDF build |
| 8.4 | PROVENANCE-BUNDLE.zip creation |
| 8.5 | Zenodo upload with DOI |
| 8.6 | D1 living-paper insert + R2 archive |
| 8.7 | Buffer social media dissemination |
| 8.8 | Core Distribution Stack verification |

---

## §3 — Milestones & Gate Criteria

| Milestone | Gate | Evidence |
|-----------|------|----------|
| **M0: Project Init** | Phase 0 closeout | Git tag v0.1-phase0, GitHub repo pushed |
| **M1: Novelty Confirmed** | Phase 1 closeout | 0 QNFO duplicates; ≥10 external papers classified |
| **M2: Categorical Proof** | Axis 1 draft complete | Non-exactness whitepaper |
| **M3: Algebraization Table** | Axis 2 draft complete | Complexity vs. coherence plot |
| **M4: S_A Quantified** | Axis 3 draft complete | Rosetta's Constant derived |
| **M5: Digital Speed Limit** | Axis 4 draft complete | Theorem proof |
| **M6: HAL Formalized** | HAL v2.0 complete | Observer Topos + Unified S_Total |
| **M7: Publication** | Phase 8 closeout | DOI resolves, papers.qnfo.org HTTP 200 |

---

## §4 — Deliverable Registry

| ID | Deliverable | Phase | Path | Archival Target |
|----|-------------|-------|------|-----------------|
| D-01 | PROJECT-PLAN.md | 0 | root | GitHub + Zenodo |
| D-02 | README.md | 0 | root | GitHub |
| D-03 | Source note | 0 | docs/26203070732-source.md | GitHub + R2 |
| D-04 | Non-Exactness Whitepaper | 2 | artifacts/non-exactness-functor.md | GitHub + Zenodo |
| D-05 | Algebraization Complexity Table | 3 | artifacts/algebraization-table.md | GitHub + Zenodo |
| D-06 | Rosetta's Constant Derivation | 4 | artifacts/rosetta-constant.md | GitHub + Zenodo |
| D-07 | Digital Speed Limit Theorem | 5 | artifacts/digital-speed-limit.md | GitHub + Zenodo |
| D-08 | Observer Topos Proof | 6 | artifacts/observer-topos.md | GitHub + Zenodo |
| D-09 | Calorimetry Protocol | 7 | artifacts/calorimetry-protocol.md | GitHub + Zenodo |
| D-10 | Final Paper (LaTeX) | 8 | releases/rosetta-manifesto.pdf | Zenodo + R2 + D1 |
| D-11 | PROVENANCE-BUNDLE.zip | 8 | releases/ | Zenodo + R2 |

---

## §5 — Risk Register

| ID | Risk | Probability | Impact | Mitigation |
|----|------|-------------|--------|------------|
| R-01 | Functor F proven exact (core thesis falsified) | Low (contradicts Gromov's theorem) | Critical | Pivot to publishing the exactness proof itself — still revolutionary |
| R-02 | Calorimeter sensitivity insufficient to measure S_A | Moderate | High | Use multiple platforms (transmons, optomechanical) with statistical averaging over millions of cycles |
| R-03 | Community resistance ("this is just semantics") | High | Medium | Focus relentlessly on the quantifiable (S_A in Joules). If it has units of energy, it is not semantics — it is physics |
| R-04 | Source note contains internal language / generation artifacts | High (confirmed) | Medium | Dedicated Phase 2 (Axis 1-5) restructuring into publishable prose removes all internal directives |
| R-05 | Overlap with existing QNFO paper "Simplicity of Reality" | Moderate | Medium | Gap analysis in Phase 1 will delineate this project's unique contribution (formal functor framework, quantitative S_A metric, transmon case study) |
| R-06 | Mathematical formalism exceeds LLM capabilities for rigorous proofs | Moderate | High | Decompose proofs into verifiable sub-claims; use subagents for adversarial review; flag [LLM-ASSISTED-CONJECTURE] where formal proof is incomplete |
| R-07 | p-adic / non-Archimedean mathematics unfamiliar to target audience | High | Low | Dedicate a pedagogical appendix; cite standard references |
| R-08 | Project too ambitious for single publication | High | Medium | Consider splitting into 2 papers: (1) Categorical + Thermodynamic core, (2) HAL + Experimental implications |

---

## §6 — Success Criteria

1. **Theoretical:** Formal proof that F: P → C is non-exact published (arXiv or equivalent).
2. **Quantitative:** Rosetta's Constant R derived with explicit numeric values for transmon hardware.
3. **Taxonomic:** New physical computation classification (Class I/II/III) formally defined and defended.
4. **Falsifiable:** Calorimetry protocol with clear falsification criterion specified.
5. **Published:** DOI assigned, papers.qnfo.org returns HTTP 200, Buffer posts confirmed.
6. **Archived:** Full Core Distribution Stack verified (GitHub + Zenodo + R2 + D1/KG).

---

## §7 — Cross-Skill Integration

| Skill | Phase | Purpose |
|-------|-------|---------|
| `research` | All | Master pipeline (this skill) |
| `knowledge` | 0, 1, closeout | KG/D1 discovery, memory seeding |
| `git-github` | 0, every closeout | Branch discipline, conventional commits |
| `cloudflare` | 8 | R2 archive, D1 insert, Worker verification |
| `documents` / `pdf` | 8 | PDF building, formatting |
| `doc-coauthoring` | 2-8 | Separating internal meta-planning from publishable prose |

---

## §8 — Version History

| Version | Date | Description |
|---------|------|-------------|
| v0.1-phase0 | 2026-07-22 | Project initialization — scaffold, charter, WBS, core claim lock |
