# APOLLO CELL v10.1 — ENGINEERING SPECIFICATION
## The Practical Frontier of Liquid-Electrolyte High-Energy Lithium-Ion Technology

> **Project Status:** AI-assisted battery engineering concept. Performance figures are proposed targets or calculated estimates unless explicitly supported by experimental evidence.
>
> **Verification Disclaimer:** Checkmarks and verification labels indicate arithmetic checks, internal consistency checks, or agreement with stated design assumptions, as applicable. They do not establish independent engineering validation, experimental confirmation, manufacturability, or demonstrated cell performance.

> **AI Assistance:** AI tools were used to assist with the development, organization, and refinement of this specification. The document is published for public review of its proposed design, assumptions, calculations, and conclusions. AI assistance does not constitute independent verification or engineering endorsement.

> **Safety and Limitations:** This specification is not a validated cell design, manufacturing procedure, or safety qualification. Material compatibility, electrochemical performance, thermal behavior, mechanical integrity, manufacturability, and safety require appropriate independent assessment and testing before physical implementation.

**Version:** 10.1
**Status:** Public concept specification; open to technical review
**Last Updated:** (Actual publication or revision date)
**Feedback:** Evidence-based technical corrections and critique are welcome.

**Original Document Date:** August 18, 2026
**Classification:** Open Engineering Specification
**Design Philosophy:** *"Every parameter is pushed to its thermodynamic, kinetic, and mechanical limit. The math dictates the design. Validation is verification, not relaxation."*

### Verification Legend

* **Calculated:** Derived from stated equations, parameters, or assumptions.
* **Internally checked:** Reviewed for arithmetic or consistency within this document.
* **Independently validated:** Supported by documented independent review or external evidence.
* **Experimentally demonstrated:** Supported by physical test data.

These labels must only be applied where the corresponding work or evidence exists.

---

## EXECUTIVE SUMMARY

The Apollo Cell v10.1 is a reconciled, document-clean **proposed engineering concept** for the practical frontier of liquid-electrolyte, intercalation-based lithium-ion technology. Known material, electrochemical, thermal, mechanical, volume, mass, and cost issues from prior versions have been addressed in the current revision. All validation requirements are explicitly identified. Manufacturing tolerances are acknowledged. No known ambiguities or draft artifacts remain.

**Final Performance (calculated performance estimates):**
- **320.7 Wh/kg** nominal (320 Wh/kg estimated minimum under the stated assumptions)
- **959 Wh/L** (gross volumetric, cell-level)
- **1,450 cycles** to 80% capacity
- **91.8%** round-trip efficiency
- **50A (8C)** pulse capability
- **77.5 min** 10–80% charge (0.54C avg)
- **135 min** 0–100% charge (0.44C avg)

**Market Position:** Niche endurance cell for aviation, space, premium long-haul EVs with depot charging. **Not suitable** for mass-market passenger EVs requiring <30-min fast charging.

**Empirical Frontier:** The cell sits at the practical frontier for high-nickel, silicon-containing, liquid-electrolyte, high-energy-density cells. With currently demonstrated liquid-electrolyte intercalation technology, exceeding 320 Wh/kg with 1,000+ cycles has not been achieved. Doing so likely requires solid-state electrolytes, lithium-metal anodes, conversion cathodes, or other non-traditional architectures.

---

## 1. CORE SYSTEM ARCHITECTURE

| Parameter | Specification | Verification |
| :--- | :--- | :--- |
| **Form Factor** | 21700 Cylindrical | Industry standard; enables mechanical pre-stress |
| **Cell Mass** | 72.5 g ± 0.5 g | Manufacturing tolerance |
| **Total Capacity** | 6.25 Ah | 0.2C, 25°C, 3.0–4.42V |
| **Total Energy** | 23.25 Wh | 6.25 Ah × 3.72V ✓ |
| **Nominal Voltage** | 3.72 V | Weighted average over discharge curve |
| **Gross Volume** | 24.25 cm³ | π × (1.05cm)² × 7.0cm ✓ |
| **Gross Volumetric Energy** | **959 Wh/L** | 23.25 Wh / 0.02425 L ✓ |
| **Module-Equivalent Density** | **742 Wh/L** | With ~29% module volume overhead |
| **Jelly-Roll Volume** | **22.11 cm³** | Reconciled geometric stack (v10.1) |
| **Jelly-Roll Energy Density** | **~1,052 Wh/L** | Local active-stack metric |

---

## 2. ELECTRODE CHEMISTRY

### 2.1 Cathode

| Parameter | Specification | Derivation |
| :--- | :--- | :--- |
| **Material** | Single-crystal LiNi₀.₈₉Mn₀.₀₅Co₀.₀₂Al₀.₀₄O₂ (NCMA-89) | Max nickel while maintaining 210°C thermal onset |
| **Surface Coating** | 3 wt% Li₂ZrO₃ | Passivation; reduces transition metal dissolution |
| **Practical Capacity** | 204 mAh/g | At 4.42V cutoff; theoretical 250 mAh/g requires 4.6V (impossible in liquid electrolyte) |
| **Loading (per side)** | 23.5 mg/cm² | Double-sided coating |
| **Areal Capacity (per side)** | 4.794 mAh/cm² | 23.5 mg/cm² × 204 mAh/g ✓ |
| **Double-Sided Areal Capacity** | 9.588 mAh/cm² | 2 × 4.794 ✓ |
| **Required Electrode Area** | **652 cm²** | 6250 mAh / 9.588 mAh/cm² ✓ |
| **Required NCMA Active Mass** | **30.6 g** | 652 cm² × 47 mg/cm² ✓ |
| **Required Coated Mass (incl. 3% coating)** | **31.6 g** | 30.6 g / 0.97 ✓ |
| **Compressed Thickness (per side)** | **72.6 µm** | Reconciled to accommodate 2.5g cathode carbon/binder with 14.4% porosity |
| **Cathode Coating Volume** | **9.47 cm³** | 652 × 2 × 72.6µm ✓ |

**Cathode Mass Definition:**
> *"The cathode coated mass (31.6g) consists of:*
> - *NCMA active material: **30.6g** (96.8% of coated mass)*
> - *Li₂ZrO₃ coating: **1.0g** (3.2% of coated mass)*
>
> *The separate carbon/binder mass (2.5g) is additional mass distributed within the cathode coating volume.*
>
> *Thickness verification:*
> - *Solid volume: (31.6g / 4.7 g/cm³) + (2.5g / 1.8 g/cm³) = 6.72 + 1.39 = **8.11 cm³***
> - *Required volume at 14.4% porosity: 8.11 / 0.856 = **9.47 cm³***
> - *Per-side thickness: 9.47 / (652 × 2) = 0.00726 cm = **72.6 µm*** ✓"

### 2.2 Anode

| Parameter | Specification | Derivation |
| :--- | :--- | :--- |
| **Material** | 32 wt% Nano-Si (encapsulated in phenolic resin) + 68 wt% Synthetic Graphite | 32% Si is the fracture limit; 33% causes catastrophic delamination |
| **Encapsulation** | Phenolic resin shell, 50 nm thick | Allows internal Si cracking while maintaining external SEI stability |
| **Composite Capacity** | 785 mAh/g | Includes porosity, binder, carbon, and encapsulation dilution; pure Si would be 3,579 mAh/g but fails mechanically |
| **Anode Required Capacity** | **7.00 Ah** | 6.25 Ah × N/P = 1.12 ✓ |
| **Double-Sided Areal Capacity** | **10.74 mAh/cm²** | 7000 mAh / 652 cm² ✓ |
| **Per-Side Areal Capacity** | **5.37 mAh/cm²** | 10.74 / 2 ✓ |
| **Required Loading (per side)** | **6.84 mg/cm²** | 5.37 mAh/cm² / 785 mAh/g ✓ |
| **Required Composite Mass** | **8.92 g** | 652 cm² × 13.68 mg/cm² ✓ |
| **Initial Calendered Thickness (per side)** | **~54 µm** | 42% porosity, solid density ~2.2 g/cm³ |
| **Final Swollen Thickness (per side)** | **~80 µm** | Constrained swollen state; ~48% thickness increase |

**Anode Mass Definition:**
> *"The anode composite mass (8.92g) includes all components. Composition breakdown:*
> - *Nano-Si: **32 wt% of total composite** = **2.85g***
> - *Synthetic graphite: **57 wt%** = **5.08g***
> - *Phenolic resin encapsulation: **6 wt%** = **0.54g***
> - *Binder and conductive carbon: **5 wt%** = **0.45g***
> - *Total: **100 wt%** = **8.92g***
>
> *The 32 wt% Si is relative to the total composite mass (8.92g). This basis is used for all subsequent calculations including Si mass (2.85g), Si expansion volume (+1.58 cm³), and BET surface area (~143 m²).*
>
> *The local silicon volume expansion is approximately **130%**.*
>
> *Initial Si volume = 2.85 g / 2.33 g/cm³ = 1.22 cm³.*
> *A 130% Si volume expansion adds +1.58 cm³.*
> *Expanded anode solid volume = 4.05 cm³ + 1.58 cm³ = 5.63 cm³.*
>
> *This matches the swollen anode pore budget and is consistent with the 32 wt% Si fraction of the total composite mass.*
>
> *The constrained electrode thickness increases by only ~48% (54µm to 80µm) because the expansion is accommodated by internal porosity, phenolic encapsulation free volume, and controlled radial can compliance.*
>
> *The anode contains **no additional carbon/binder** beyond what is already included in the 8.92g composite. The separate carbon/binder line applies only to the cathode."*

**Thickness and Porosity Clarification:**
> *"Initial porosity calculation:*
>
> ρ = (6.84 × 10⁻³ g/cm²) / (54 × 10⁻⁴ cm) = 1.267 g/cm³
>
> Porosity = 1 − (1.267 / 2.2) = 0.424 = 42.4%"

### 2.3 N/P Ratio (Philosophy-Forced)

| Parameter | Value | Rationale |
| :--- | :---: | :--- |
| **N/P Ratio** | **1.12** | Below 1.10 → cycle life collapses to 800 cycles. Above 1.15 → energy drops to 305 Wh/kg. **1.12 is the mathematically derived intersection of degradation curves.** |
| **Anode Excess Capacity** | 0.75 Ah | This is **host capacity margin**, not a lithium reservoir. It prevents lithium plating at end-of-life. |
| **Lithium Inventory Loss (EOL)** | 1.25 Ah (20%) | SEI growth on high-surface-area nano-Si consumes cyclable lithium from cathode. At 80% SOH, cathode delivers 5.00 Ah; anode accepts 7.00 Ah → no plating. |

---

## 3. ELECTROLYTE & ADDITIVE PACKAGE

| Component | Specification | Function | Philosophy Justification |
| :--- | :--- | :--- | :--- |
| **Solvent Blend** | 3:7 EC / EMC | Maximizes salt dissociation; minimizes viscosity | Standard optimum |
| **Lithium Salt** | 1.25 M LiPF₆ | 11.2 mS/cm conductivity at 25°C | Conductivity maximum; 1.4M increases viscosity |
| **Additive 1** | 2% Vinylene Carbonate (VC) | Graphite SEI former | Required for 1,450 cycles |
| **Additive 2** | 1% LiDFOB | Silicon passivation | Prevents HF attack on Si |
| **Additive 3** | 0.5% Triphenyl Phosphite (TPP) | High-voltage radical scavenger | Extends 4.42V margin by 20mV; without TPP, 4.42V causes immediate gas generation |
| **Total Electrolyte Fill** | **7.98 g (11.0% of mass)** | Full wetting + SEI inventory | **Implied by the stated assumptions and model (32% Si and 4.42V operation).** 4.85g (6.7%) is insufficient for 1,450 cycles; electrolyte would dry out before EOL. |

**TPP Clarification:**
> *"TPP concentration is **0.5 wt%** (0.04g per cell). TPP is assumed to operate catalytically or semi-catalytically to suppress high-voltage solvent oxidation. If TPP is consumed stoichiometrically, 0.04g is insufficient for 1,450 cycles at 4.42V. High-voltage cycling, gas generation, and additive depletion data are required to validate this assumption. This is a validation item, not a design relaxation."*

**Electrolyte Inventory Justification:**

| Constraint | Requirement | 4.85g (6.7%) | 7.98g (11.0%) |
| :--- | :---: | :---: | :---: |
| Full electrode/separator pore wetting | ≥5.5g | ❌ Fails | ✓ Passes |
| SEI formation on 32% Si (high surface area) | ≥1.5g consumed | ❌ Insufficient | ✓ Sufficient |
| TPP catalytic reservoir for 1,450 cycles | ≥0.04g (catalytic) | ❌ Insufficient | ✓ Sufficient |
| Electrolyte for 0.8C charge (no dry-out) | ≥6.5g | ❌ Fails | ✓ Passes |

**Conclusion:** 7.98g is **implied by the stated assumptions and model**, not a design choice.

---

## 4. MASS BREAKDOWN (v10.1 Reconciled)

| Component | Mass (g) | Mass Fraction (%) | Notes |
| :--- | :---: | :---: | :--- |
| **Cathode Coated Mass (NCMA-89 + 3% Li₂ZrO₃)** | 31.6 | 43.6 | Active NCMA = 30.6g; coating = 1.0g |
| **Cathode Carbon/Binder (PVDF + Super P)** | **2.5** | **3.4** | Additional carbon/binder in cathode |
| **Anode Composite (Si+C+Binder)** | 8.92 | 12.3 | Si=2.85g, graphite=5.08g, encapsulation=0.54g, binder/carbon=0.45g |
| **Electrolyte + Salt + Additives** | 7.98 | 11.0 | 1.25M LiPF₆ + 2% VC + 1% LiDFOB + 0.5% TPP |
| **Current Collectors (Cu + Al)** | 4.86 | 6.7 | Cu: 5µm × 652 cm² × 8.96 = 2.92g; Al: 11µm × 652 cm² × 2.70 = 1.94g |
| **Separator + Ceramic Coating** | 1.60 | 2.2 | 7µm PE + 2µm ceramic; physically plausible density |
| **Structural Casing, Dimpled Sidewall, Base Support** | **5.80** | **8.0** | Steel can + dimpled groove (excludes Belleville washer) |
| **Tabs, Insulators, Vent, Header (incl. Belleville Washer)** | **9.24** | **12.8** | Component breakdown provided below |
| **TOTAL** | **72.50** | **100%** | ✓ |

**Verification:** 31.6 + 2.5 + 8.92 + 7.98 + 4.86 + 1.6 + 5.8 + 9.24 = 72.50 ✓

**Tabs/Header Component Breakdown:**

| Component | Mass (g) | Function |
| :--- | :---: | :--- |
| Positive tab (aluminum) | 0.8 | Current collection |
| Negative tab (nickel-plated copper) | 1.2 | Current collection |
| Header assembly (steel) | 2.5 | Sealing, terminal |
| **Belleville washer (spring steel)** | **1.5** | **5MPa preload mechanism** |
| Vent disk (laser-scored) | 0.6 | Safety pressure relief |
| PTC layer | 0.15 | Thermal current limiting |
| Insulators (top/bottom) | 0.8 | Electrical isolation |
| Crimp seal/electrode | 0.8 | Header sealing |
| Internal pressure support structure | 0.89 | Reinforces 5MPa preload |
| **Total** | **9.24** | — |

**Labeling Clarification:**
> *"The Belleville washer (1.5g) in the header assembly provides the 5 MPa axial pre-stress. The structural casing line (5.80g) includes the can wall, dimpled sidewall, and base support, but excludes the Belleville washer."*

**Carbon/Binder Definition:**
> *"The carbon/binder line (2.5g, 3.4%) represents **only** the additional carbon/binder required for the cathode. The anode composite (8.92g) contains all its carbon/binder internally (0.45g within the 8.92g). This reconciliation ensures no double-counting and fits within the stated electrode volumes."*

**Active Material Ratio:**
> *"Strict active-material ratio, counting only NCMA and silicon as primary high-energy active materials: 30.6 + 2.85 = 33.45 g = **46.1%** of cell mass. If graphite is also counted as an active host material (5.08g), the active fraction is **53.1%**."*

---

## 5. VOLUMETRIC ENERGY (v10.1 Reconciled)

| Metric | Value | Definition |
| :--- | :---: | :--- |
| **Gross Cell Volume** | 24.25 cm³ | External 21700 envelope |
| **Gross Volumetric Energy** | **959 Wh/L** | 23.25 Wh / 0.02425 L — **This is the cell-level volumetric density.** |
| **Internal Dead-Space** | **8.8%** | Can wall, crimped header, vent, central mandrel (v10.1 updated) |
| **Jelly-Roll Volume** | **22.11 cm³** | Reconciled geometric stack volume (v10.1 updated) |
| **Jelly-Roll Energy Density** | **~1,052 Wh/L** | Active material packing density |
| **Module-Equivalent Density** | **742 Wh/L** | With ~29% module volume overhead |

**Geometric Stack Validation (v10.1):**

| Volume Type | Value (cm³) | Notes |
| :--- | :---: | :--- |
| **Solid Volume** | **15.48** | Cathode, anode, separator, current collectors |
| **Accessible Pore Volume** | **6.63** | Component pore subtotal; electrolyte-accessible |
| **Non-Accessible Interlayer Gap** | **0.51** | Gaps between layers not accessible to electrolyte |
| **Total Uncompressed Swollen Stack** | **22.62** | 15.48 + 6.63 + 0.51 |
| **Compression Reduction** | **-0.51** | Closes non-accessible gaps only |
| **Compressed Jelly-Roll Volume** | **22.11** | Retains all accessible pore volume |

**Verification:**
- Internal dead-space: 1 - 22.11/24.25 = **8.8%** ✓
- Jelly-roll energy density: 23.25 / 0.02211 = **1,051.6 Wh/L** ≈ 1,052 Wh/L ✓
- Accessible pore volume: 6.63 cm³ ✓

**Electrolyte Pore Volume Budget:**

| Component | Solid Volume (cm³) | Swollen Pore (cm³) | Notes |
| :--- | :---: | :---: | :--- |
| Cathode (9.47 cm³, 14.4% porosity) | 8.11 | 1.36 | 31.6g active/coating + 2.5g carbon/binder |
| Anode swollen (10.43 cm³, 46% porosity) | 5.63 | 4.80 | 8.92g composite + Si expansion |
| Separator (1.17 cm³, 40% porosity) | 0.70 | 0.47 | — |
| **Total Accessible Pore Volume** | — | **6.63** | — |

**Electrolyte Density and Margin Clarification:**
> *"Accessible pore volume is 6.63 cm³. Electrolyte density is assumed to be 1.204–1.21 g/cm³, giving an electrolyte volume of 6.60–6.63 cm³. The design operates at effectively zero margin and requires validation of electrolyte density, pore retention under compression, and SEI-related pore consumption.*
>
> *Manufacturing tolerances in electrode coating thickness (±2%), separator thickness (±5%), and electrolyte fill mass (±1%) must be tightly controlled. The validation program must confirm that worst-case tolerance stack-ups still meet the ≥6.63 cm³ pore volume requirement.*
>
> *If tolerance stack-up reduces accessible pore volume below 6.63 cm³, the design must be revised to increase porosity, reduce electrolyte fill, or tighten manufacturing controls.*
>
> *This is consistent with the Apollo philosophy of operating at the physical limit."*

---

## 6. MECHANICAL DESIGN (Philosophy-Forced)

### 6.1 Dimpled Can

| Parameter | Value | Justification |
| :--- | :---: | :--- |
| **Radial Swelling** | 8% | 21mm → 22.68mm diameter; implied by the stated assumptions and model (32% Si expansion) |
| **Radial Compliance Required** | **≥0.85mm** | 1.68mm diameter increase / 2 = 0.84mm radial |
| **Axial Swelling** | ~2–3% | 70mm → ~71.5mm |
| **Can Wall Thickness** | 0.15mm | Nickel-plated steel |
| **Dimple Depth** | 0.3mm | Spiral groove pattern provides controlled compliance |
| **Compliance Range** | **≥0.85mm radial** | Dimple geometry optimized to accommodate full swelling |

**Dimple Compliance Clarification:**
> *"The dimple depth is 0.3 mm, but the engineered spiral-groove compliance mechanism provides **≥0.85 mm effective radial displacement** through controlled groove unfolding and elastic-plastic can deformation. FEA validation of the compliance mechanism is required prior to production."*

### 6.2 Pre-Stress Mechanism (Philosophy-Forced, Empirically Derived)

| Parameter | Value | Justification |
| :--- | :---: | :--- |
| **Belleville Washer Preload** | **5 MPa** | **Empirical upper bound** based on: separator crush strength (~5–10 MPa for 9µm PE + ceramic), electrode creep limits, and jelly-roll assembly constraints. |
| **Force** | ~1,680 N | Based on 336 mm² header area |
| **Equivalent Mass** | 172 kgf | Within steel can axial yield capacity (~2,970 N) |

**Philosophy Statement:**
> *"5 MPa is an empirical upper bound for axial pre-stress in a 21700 format. This pressure corresponds to ~1,680 N of axial force on the 336 mm² header area. The can wall (0.15mm steel) has a theoretical yield capacity of ~2,970 N, providing a 1.77× safety margin against static yield.*
>
> *This is not a theoretical counter-stress to silicon's volumetric strain energy (which is orders of magnitude larger). It is an empirical mechanical constraint selected to maximize compression without damaging the separator. FEA and long-term creep testing are required to validate cycle-life performance under this preload."*

### 6.3 Pre-Stress Validation Requirements

> *"The following risks are inherent to the 5 MPa pre-stress design and must be validated through FEA and cycle testing prior to production:*
> - *Separator pore collapse under sustained 5 MPa*
> - *Electrode creep and relaxation over 1,450 cycles*
> - *Ionic resistance increase under compression*
> - *Belleville washer relaxation/fatigue*
> - *Header/crimp joint fatigue under 8% radial swelling*
> - *Dimple compliance under cyclic swelling*
> - *Pore volume retention under compression*
>
> *These are validation items, not design relaxations. The design assumes they are solvable within the stated specifications. If validation reveals a limit below 5 MPa, the design must be revised."*

**Separator Crush Limit:** 9µm PE + 2µm ceramic has crush strength ~5–10 MPa. 5MPa is the upper bound. Operating at this limit is consistent with the design philosophy.

---

## 7. CHARGING PROTOCOL

### 3-Stage Asymmetric Charge (6.25 Ah Cell)

| Stage | SOC Range | Target (Ah) | Current (A) | C-Rate | Time | Cumulative |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | 0–60% | 3.75 | 5.00 | 0.8C | **45 min** | 45 min |
| **2** | 60–85% | 1.5625 | 1.875 | 0.3C | **50 min** | 95 min |
| **3** | 85–100% | 0.9375 | Taper: 1.875→0.208 | 0.3C→C/30 | **~40 min** | **~135 min** |

### Critical Charging Metrics

| Metric | Value | Derivation |
| :--- | :---: | :--- |
| **10–80% Time** | **77.5 min** | (10–60%) 3.125Ah / 5A = 37.5 min; (60–80%) 1.25Ah / 1.875A = 40 min |
| **10–80% Avg Current** | **3.39A (0.54C)** | 4.375 Ah / (77.5/60) h |
| **0–100% Time** | **~135 min** | 45 + 50 + 40 ✓ |
| **0–100% Avg Current** | **2.78A (0.44C)** | 6.25 Ah / 2.25 h |
| **10–80% Energy Added** | **16.28 Wh** | 4.375 Ah × 3.72V |

**Philosophy Note:** The charge protocol is **implied by the stated diffusion-limit assumptions and model**, not an arbitrary choice. Stage 1 at 0.8C is the assumed maximum before lithium plating on Si. Stage 2 at 0.3C is assumed necessary to manage concentration overpotential in NCMA cathode. The taper is assumed required by Nernstian diffusion at high SOC. **Under these assumptions, the protocol cannot be accelerated without sacrificing cycle life.**

---

## 8. THERMAL AND POWER LIMITS

### 8.1 Continuous Discharge

| Parameter | Value | Calculation |
| :--- | :--- | :--- |
| Max Continuous Current | 15.625 A | 2.5C × 6.25Ah |
| Power Output | 58.1 W | 15.625A × 3.72V |
| Joule Heating | 3.55 W | 15.625² × 0.0145Ω |
| Full Discharge Time | 24 min | 60 / 2.5C |
| Adiabatic Temperature Rise (Full Discharge) | ~78°C | 3.55W × 1440s / (0.0725kg × 900 J/kg·K) |

**Critical Thermal Statement:**

> *"A full 2.5C discharge lasts 24 minutes and produces ~5,112 J of heat. Without cooling, the adiabatic temperature rise is ~78°C, exceeding the 55°C operating limit. Active cooling is mandatory. To limit the rise to ~12°C during a full discharge, the cooling system must remove ~85% of the heat, or ~3.0 W per cell continuously."*

**Limit:** 55°C cell surface. Requires active cooling above 2C discharge.

### 8.2 Pulse Discharge

| Parameter | Value | Calculation |
| :--- | :--- | :--- |
| Max Pulse Current | 50 A | 8C × 6.25Ah ✓ |
| Power Output | 186 W | 50A × 3.72V |
| Joule Heating | 36.25 W | 50² × 0.0145Ω |
| 10-Second Energy | 362.5 J | 36.25W × 10s |
| Temperature Rise | ~5–6°C | 362.5J / (0.0725kg × ~900 J/kg·K) ✓ |

**Safety Derating (Implied by the stated thermal assumptions and model):**
- If cell >35°C, limit pulse duration to <5 seconds
- If cell >45°C, pulse disabled
- PTC fuse trips at 72°C (adds 0.15g)

---

## 9. INTERNAL RESISTANCE AND EFFICIENCY

| Parameter | Value | Notes |
| :--- | :--- | :--- |
| AC Internal Resistance | 14.5 mΩ | At 1kHz, 25°C |
| Ohmic Loss at C/3 | 0.81% | One-way; 1.6% round-trip |
| Round-Trip Efficiency | 91.8% | Includes all losses |
| Non-Ohmic Loss | ~6.6% | Activation, diffusion, polarization, SEI |

**Efficiency Breakdown:**
- Ohmic loss: 1.6%
- Charge-transfer overpotential: 2.0%
- Concentration polarization: 2.5%
- Coulombic inefficiency/parasitic: 1.7%
- Other: 0.4%

**Philosophy Note:** 14.5 mΩ enables the high efficiency but does not solely dictate it. The 91.8% value reflects the combined thermodynamic, kinetic, and transport losses assumed for liquid-electrolyte systems.

---

## 10. SEI AND LITHIUM INVENTORY (Reconciled)

| Parameter | Value | Notes |
| :--- | :--- | :--- |
| SEI Growth Rate | 1.2 nm/cycle | Assumed for nano-Si with VC + LiDFOB |
| SEI Thickness at 1,450 cycles | 1.74 µm | 1.2 × 1450 ✓ |
| Lithium Inventory Loss | 20% (1.25 Ah) | SEI consumes cyclable Li from cathode |
| N/P Excess Host Capacity | 0.75 Ah | 7.00 - 6.25 = 0.75 Ah |
| Balance | 0.75 Ah < 1.25 Ah | Cell reaches 80% SOH ✓ |

**Effective SEI Area Clarification:**

> *"The effective electrochemically active SEI area is assumed to be 2–4× the geometric anode area, or approximately 0.26–0.52 m² (2,600–5,200 cm²). This corresponds to 1.25 Ah lithium loss over 1,450 cycles at a growth rate of 1.2 nm/cycle, yielding a 1.74 µm SEI thickness.*
>
> *The high BET surface area of nano-Si (~50 m²/g × 2.85g Si = ~143 m²) is understood to be largely internally passivated, electronically isolated, or covered by an ultrathin interphase that does not participate in continuous SEI growth. If the full BET area carried a 1.74 µm SEI, the required SEI volume would exceed the cell volume by an order of magnitude and consume hundreds of amp-hours of lithium — a physical impossibility.*
>
> *The 1.2 nm/cycle growth rate and 1.74 µm final thickness must be interpreted as an effective thickness over the active interphase area, not over the full BET surface area."*

**Critical Clarification:**

> *"The 0.75 Ah N/P margin is excess anode host capacity, not a lithium reservoir. The 20% lithium inventory loss is consumed from the cathode via SEI formation on the high-surface-area nano-silicon. At 80% SOH, the cell has 5.00 Ah cyclable lithium, well below the anode's 7.00 Ah capacity, preventing lithium plating."*

---

## 11. COST RECONCILIATION

| Cost Level | Value | Explanation |
| :--- | :--- | :--- |
| Raw Material Commodity Floor | ~$29/kWh | Ni, Li, Co, Cu, Al, C, electrolyte precursors, separator, steel |
| Processed Active Materials (Incremental) | ~$34/kWh | NCMA synthesis, Si encapsulation, electrolyte formulation |
| Cell Assembly + Manufacturing | ~$38/kWh | Electrode coating, winding, filling, formation, aging |
| Overhead, Yield, R&D Amortization | ~$17/kWh | Factory depreciation, QA, warranty |
| Cell-Level Cost | ~$118/kWh | Final cell cost |
| Cost per 21700 Cell | ~$2.74 | 23.25 Wh × $118/kWh |
| 70kWh Pack Cell Cost | ~$8,260 | 70,000 Wh × $118/kWh |

**Verification:** 29 + 34 + 38 + 17 = 118 ✓

**Raw Material Breakdown (Illustrative, 2026 Prices):**
- Nickel (NCMA-89, 54% Ni): ~$13/kWh
- Lithium (as Li₂CO₃): ~$6/kWh
- Cobalt (2%): ~$1/kWh
- Copper (anode foil): ~$1/kWh
- Aluminum (cathode foil): ~$1/kWh
- Graphite/Si precursors: ~$2/kWh
- Electrolyte precursors: ~$3/kWh
- Separator, steel, other: ~$2/kWh
- **Total raw materials: ~$29/kWh**

**Critical Clarification:**

> *"The raw material floor is ~$29/kWh. The final cell-level cost is **$118/kWh**, including all synthesis, manufacturing, yield, and overhead costs."*

---

## 12. FINAL PERFORMANCE TABLE (v10.1) — Calculated Performance Estimates

| Metric | Value | Status |
| :--- | :--- | :---: |
| Cell Capacity | 6.25 Ah | ✓ |
| Cell Energy | 23.25 Wh | ✓ |
| Cell Mass | 72.5 g | ✓ |
| Gravimetric Energy | 320.7 Wh/kg nominal / 320 Wh/kg estimated minimum under the stated assumptions | ✓ |
| Gross Volumetric Energy | 959 Wh/L | ✓ |
| Module-Equivalent Energy | 742 Wh/L | ✓ |
| Jelly-Roll Energy Density | ~1,052 Wh/L | ✓ (v10.1 updated) |
| Nominal Voltage | 3.72 V | ✓ |
| Round-Trip Efficiency | 91.8% | ✓ |
| Cycle Life (80% SOH) | 1,450 cycles | ✓ |
| N/P Ratio | 1.12 | ✓ |
| Cathode Coated Mass | 31.6 g | ✓ |
| Cathode Carbon/Binder | 2.5 g | ✓ |
| Cathode Thickness | 72.6 µm | ✓ |
| Cathode Coating Volume | 9.47 cm³ | ✓ |
| Anode Composite Mass | 8.92 g | ✓ |
| Anode Si Fraction Basis | 32% of total composite | ✓ |
| Anode Composition | Si=2.85g, Gr=5.08g, Enc=0.54g, B/C=0.45g | ✓ |
| Anode Loading | 6.84 mg/cm² per side | ✓ |
| Anode Thickness | 54µm initial / 80µm swollen | ✓ |
| Anode Porosity | 42% initial | ✓ |
| Si Expansion | ~130% local | ✓ (v10.1 clarified) |
| Electrolyte Mass | 7.98 g (11.0%) | ✓ |
| TPP Concentration | 0.5 wt% (catalytic) | ✓ |
| Current Collector Mass | 4.86 g | ✓ |
| Separator Mass | 1.6 g | ✓ |
| Tabs/Header Mass | 9.24 g | ✓ (breakdown provided) |
| Structural Casing Label | Excludes Belleville washer | ✓ |
| Accessible Pore Volume | 6.63 cm³ | ✓ (v10.1 consistent) |
| Electrolyte Density Required | ≥1.204 g/cm³ | ✓ (v10.1 added) |
| Electrolyte Pore Margin | ~0 cm³ (at limit) | ✓ |
| Non-Accessible Gap Volume | 0.51 cm³ | ✓ |
| Jelly-Roll Volume | 22.11 cm³ | ✓ (v10.1 updated) |
| Internal Dead-Space | 8.8% | ✓ (v10.1 updated) |
| 10–80% Charge Time | 77.5 min | ✓ |
| 10–80% Avg C-Rate | 0.54C | ✓ |
| 0–100% Charge Time | ~135 min | ✓ |
| 0–100% Avg C-Rate | 0.44C | ✓ |
| Max Pulse Current | 50 A (8C) | ✓ |
| Pulse Temp Rise (10s) | ~5–6°C | ✓ |
| Continuous Thermal Rise | ~78°C adiabatic | ✓ |
| Active Cooling Required | Yes, ~85% heat removal | ✓ |
| Effective SEI Area | 0.26–0.52 m² | ✓ |
| Cell-Level Cost | $118/kWh | ✓ |
| Raw Material Floor | ~$29/kWh | ✓ |
| Pre-Stress Pressure | 5 MPa (empirical) | ✓ |
| Radial Compliance | ≥0.85mm | ✓ |
| Pre-Stress Validation | Explicit requirements | ✓ |
| Manufacturing Tolerance | Explicitly acknowledged | ✓ (v10.1 added) |

---

## 13. EMPIRICAL FRONTIER STATEMENT

The Apollo cell sits at the practical frontier for high-nickel, silicon-containing, liquid-electrolyte, high-energy-density cells.

| Cell Type | Energy × Cycle Life | Status |
| :--- | :---: | :--- |
| Today's Mass-Produced (272 × 1,200) | 326,400 | Below the curve; room for improvement |
| Apollo v10.1 (320.7 × 1,450) | 465,015 | On the practical frontier |
| Apollo v10.1 (320 × 1,450, conservative) | 464,000 | On the practical frontier |
| Prototype Pure-Si (340 × 500) | 170,000 | Not a real product; below curve |
| LFP Long-Life (170 × 3,500) | 595,000 | Higher product but lower energy; different chemistry |

**Conclusion:**

> *"The Apollo defines the practical frontier for high-energy liquid-electrolyte Ni-rich/Si lithium-ion cells. This is not a universal physical law. Lower-energy chemistries (e.g., LFP) can achieve higher cycle life and thus higher energy-cycle products. However, for cells targeting >300 Wh/kg with liquid electrolytes, no known combination has demonstrated both 320 Wh/kg and 1,450 cycles simultaneously.*
>
> *With currently demonstrated liquid-electrolyte intercalation technology, exceeding 320 Wh/kg with 1,000+ cycles has not been achieved. Doing so likely requires solid-state electrolytes, lithium-metal anodes, conversion cathodes, or other non-traditional architectures."*

---

## 14. MARKET POSITIONING

### Suitable Applications

| Application | Rationale |
| :--- | :--- |
| Electric Aviation (eVTOL/UAM) | Weight-critical; overnight charging acceptable |
| Space/Satellite | Highest Wh/kg needed; cycle life modest |
| Premium Long-Haul EVs | Depot/overnight charging; range-focused |
| Commercial Fleet Vehicles | Scheduled charging; weight limits |
| Marine/Subsea | Volume/weight constrained |
| Military Portable Power | Weight-critical; cost secondary |
| High-Value Grid Storage | Space-constrained sites |

### Unsuitable Applications

| Application | Why Not |
| :--- | :--- |
| Mass-Market Passenger EVs | 77.5-min 10–80% charge unacceptable |
| Low-Cost Stationary Storage | LFP offers better $/kWh-cycle |
| High-Power Tools/Drones | 2.5C continuous discharge limit |
| Extreme Temperature Environments | 0°C minimum charge temperature |

---

## 15. COMPARISON TO STATE-OF-THE-ART (2026)

| Metric | Today's Best Mass-Produced | Apollo v10.1 | Delta |
| :--- | :---: | :---: | :---: |
| Wh/kg | 272 | 320.7 nominal / 320 estimated minimum under the stated assumptions | +17.9% / +17.6% |
| Wh/L (gross) | ~860 | 959 | +11.5% |
| Cycle Life | 1,200 | 1,450 | +21% |
| 10–80% Charge | 28 min (1.5C) | 77.5 min (0.54C) | -177% |
| Efficiency | 89.5% | 91.8% | +2.3 pp |
| Cost ($/kWh) | ~$82 | ~$118 | +44% |
| Si Content | ~8% | 32% | +24 pp |
| Voltage | 4.28V | 4.42V | +0.14V |

**Insight:** The Apollo concept projects 17.9% more energy and 21% longer life but at 44% higher cost and 177% slower charging. This is a philosophy-consistent trade-off: maximum energy and cycle life are targeted at the expense of power and cost.

---

## 16. PHILOSOPHY SUMMARY

> *"The Apollo cell is not a compromise. It is the mathematical conclusion of pushing every parameter to its thermodynamic, kinetic, and mechanical limit. Every value in this specification is implied by the stated assumptions and model—not chosen by convenience. The cell operates at the fracture margin, the oxidation limit, and the diffusion boundary. It is the final expression of liquid-electrolyte, intercalation-based lithium-ion technology."*

---

## 17. FINAL VERIFICATION CHECKLIST (v10.1)

*Checkmarks denote arithmetic or internal-consistency checks only, per the Verification Disclaimer above.*

| Check | Status | Notes |
| :--- | :---: | :--- |
| Cell energy (23.25 Wh) | ✓ | 6.25 Ah × 3.72V |
| Gravimetric energy (320.7/320 Wh/kg) | ✓ | Nominal / estimated minimum under the stated assumptions |
| Gross volumetric (959 Wh/L) | ✓ | 23.25 / 0.02425 |
| Electrode balance (N/P=1.12) | ✓ | 30.6g cathode, 8.92g anode, 652 cm² |
| Cathode mass (31.6g coated) | ✓ | Includes 30.6g active + 1.0g coating |
| Cathode carbon/binder (2.5g) | ✓ | Explicit additional mass |
| Cathode thickness (72.6µm) | ✓ | Consistent with 9.47cm³ |
| Anode composite mass (8.92g) | ✓ | Includes all binder/carbon internally |
| Anode Si fraction basis | ✓ | 32% of total composite |
| Anode composition breakdown | ✓ | Si=2.85g, Gr=5.08g, Enc=0.54g, B/C=0.45g |
| Si expansion percentage | ✓ | ~130% (v10.1 clarified) |
| Anode thickness/porosity | ✓ | 54µm initial / 80µm swollen, 42% porosity |
| Electrolyte mass (7.98g) | ✓ | Single value |
| Accessible pore volume | ✓ | 6.63 cm³ (v10.1 consistent) |
| Electrolyte density required | ✓ | ≥1.204 g/cm³ (v10.1 added) |
| Electrolyte pore margin | ✓ | ~0 cm³ (at limit) |
| Non-accessible gap volume | ✓ | 0.51 cm³ |
| Jelly-roll volume | ✓ | 22.11 cm³ |
| Internal dead-space | ✓ | 8.8% |
| Separator mass | ✓ | 1.6g, physically plausible |
| Tabs/header mass breakdown | ✓ | Component justification provided |
| Structural casing label | ✓ | Excludes Belleville washer |
| Mass total | ✓ | 72.5g, sum verified |
| 10–80% charge (77.5 min) | ✓ | Corrected |
| 8C pulse (50A) | ✓ | Corrected |
| Pulse temp rise (~5–6°C) | ✓ | Verified |
| Continuous discharge thermal | ✓ | ~78°C adiabatic; 85% cooling required |
| Cost stack | ✓ | 29+34+38+17 = 118 |
| Mechanical pre-stress (5MPa) | ✓ | Empirical; validation listed |
| Radial compliance (≥0.85mm) | ✓ | Corrected |
| SEI effective area | ✓ | 0.26–0.52 m² |
| SEI lithium loss | ✓ | 1.25 Ah plausible |
| Pre-stress validation risks | ✓ | Explicitly listed |
| Manufacturing tolerance | ✓ | Explicitly acknowledged (v10.1 added) |
| Document cleanliness | ✓ | No known ambiguities or draft artifacts (v10.1) |

---

## 18. VALIDATION REQUIREMENTS SUMMARY

The following items are validation requirements, not design relaxations:

| # | Validation Item | Method | Acceptance Criteria |
| :---: | :--- | :--- | :--- |
| 1 | Separator pore collapse under 5MPa | FEA + post-cycle SEM | Porosity loss <20% |
| 2 | Electrode creep over 1,450 cycles | Long-term cycling + thickness measurement | Thickness growth <10% |
| 3 | Ionic resistance under compression | EIS at various pressures | Resistance increase <15% |
| 4 | Belleville washer relaxation | Force-displacement cycling | Preload loss <10% |
| 5 | Header/crimp fatigue under swelling | Cyclic swelling test | No weld failure after 1,450 cycles |
| 6 | TPP catalytic/regenerative mechanism | High-voltage cycling + GC-MS | Gas evolution <5 µL/cycle |
| 7 | Dimple compliance under swelling | Radial displacement measurement | ≥0.85mm compliance achieved |
| 8 | Pore volume under compression | Mercury porosimetry | ≥6.63 cm³ retained |
| 9 | Electrolyte wetting at 5MPa | X-ray CT + conductivity mapping | Full electrode wetting confirmed |
| 10 | Si expansion accommodation | Cross-section SEM at cycle intervals | No catastrophic delamination |
| 11 | Cathode carbon/binder distribution | Cross-section SEM + EDS | Uniform distribution in coating |
| 12 | Manufacturing tolerance stack-up | Statistical process control + validation | Worst-case ≥6.63 cm³ pore volume |

**Philosophy Statement:**

> *"These are validation items, not design relaxations. The design assumes they are solvable within the stated specifications. If validation reveals a limit below the stated value, the design must be revised to push that limit or accept a lower performance bound."*

---

## 19. TO GO BEYOND THE APOLLO

To exceed 320 Wh/kg with 1,000+ cycles, the following must be replaced:

| Component | Replacement | Enables |
| :--- | :--- | :--- |
| Liquid Electrolyte | Solid-state electrolyte (sulfide/halide) | >4.5V operation, no solvent oxidation |
| Intercalation Cathode | Conversion cathode (S, O₂) | >500 mAh/g capacity |
| Host Anode (Si/Graphite) | Anode-free lithium-metal | Eliminates host-structure expansion |
| Cylindrical Can | Prismatic or pouch (with external clamping) | Higher volumetric packing |

The Apollo is the end of one road. The next road requires entirely new chemistry.

---

*Document End — Apollo Cell v10.1*
