

**Adapted from:** Magnotti et al., _EMBO Mol Med_ 2019;11:e10547 **Cohort:** 6 donors — Patient 1 (M694V/M694V), Patient 2 (MEFV duplication, VUS), 2 family members (heterozygous carriers), 2 healthy controls (HD) **Two plates run in parallel from one isolation:**

- **Plate 1** — black 96-well plate → PI kinetic (Varioskan LUX, top read)
- **Plate 2** — regular clear 96-well plate → IL-1β ELISA (incubator, supernatant harvest)

---

## 0. Design rationale (read once)

|Readout|Plate|Priming|Cell number|Purpose|
|---|---|---|---|---|
|PI kinetic (cell death)|Black, Varioskan|**No LPS** for UCN-01 wells|2 × 10⁴/well|Gasdermin-D pores / pyroptosis|
|IL-1β ELISA|Clear, incubator|**LPS 10 ng/mL, 3 h** for ALL wells|5 × 10³/well|Caspase-1 / pro-IL-1β processing|

The two assays are run in **separate wells** — PI is cytotoxic and contaminates supernatant; ELISA wells cannot be kinetically read. They share the same plating, priming, and stimulus timepoints so you can directly align the two readouts per donor.

**Key controls:**

- **M694V/M694V patient** = positive control for both assays. Must fire in both. If it doesn't, fix the assay before interpreting anything else.
- **Duplication patient** = the research question. Compare to the reference ladder on both readouts.
- **LPS + nigericin** = genotype-independent inflammasome activation (NLRP3). Should produce robust death and robust IL-1β in **all** donors. This is the "are the cells alive and inflammasome-competent" internal control.
- **No colchicine arm** — not available. The HD-vs-FMF contrast and the nigericin column together provide sufficient specificity evidence for a first replication.
- Oral colchicine therapy in the FMF patient does **not** blank the assay — it washes out during PBMC isolation.

---

## 1. Reagents and stocks

|Reagent|Stock|Notes|
|---|---|---|
|Isolated CD14⁺ monocytes|—|Counted with viability marker before use|
|RPMI 1640 + **L-glutamine (2 mM)** + 10% FCS|—|Add glutamine fresh from 200 mM (100×) stock; pre-warm to 37 °C|
|UCN-01|10 mM in DMSO|**Fresh single-use aliquot from −80 °C, light-protected.** Do not reuse 4 °C tube|
|Propidium iodide (PI)|1 mg/mL|PI plate only|
|Nigericin|10 mM in EtOH or DMSO||
|LPS|1 mg/mL → prepare 1 µg/mL working|For priming; keep at 4 °C|
|Triton X-100|Prepare 10% in medium (100 µL neat Triton + 900 µL medium)|PI plate only|
|DMSO|Neat|Vehicle control|
|Human IL-1β ELISA kit|—|Range ideally 15–2000 pg/mL; dilute FMF patient supernatants if needed|

**L-glutamine note:** Free L-glutamine is fully stable over the 4–5 h of this assay. Use a recently prepared complete medium (within 1–2 weeks) or add glutamine fresh from a frozen 200 mM aliquot on the day.

**No CO₂ reader note:** Prime both plates for 3 h in your CO₂ incubator. The Varioskan runs without CO₂ for only ~105 min — too short for meaningful pH drift. Temperature and evaporation matter far more.

---

## 2. Working ("10×") solutions — used for BOTH plates

Add **20 µL** of 10× stimulus to **180 µL** cells = **200 µL** final well volume throughout.

|Stimulus|Final concentration|10× working solution|Recipe per 1 mL|
|---|---|---|---|
|UCN-01|12.5 µM|125 µM (1.25% DMSO)|12.5 µL of 10 mM UCN-01 + 987.5 µL medium|
|Vehicle (DMSO)|0.125% DMSO|1.25% DMSO|12.5 µL DMSO + 987.5 µL medium|
|Nigericin|5 µM|50 µM|5 µL of 10 mM nigericin + 995 µL medium|
|Triton X-100 _(PI plate only)_|0.1%|1%|100 µL of 10% Triton + 900 µL medium|

Prepare fresh on the day. Pre-warm to 37 °C before adding to cells.

---

## 3. Monocyte isolation and counting

Use your SepMate / density gradient + CD14 MicroBead (Miltenyi) workflow.

1. Handle gently — every dead cell at isolation raises baseline PI signal and dilutes your cytokine signal. Cold PBS washes, low-speed spins.
2. **Count with a viability marker** and record % viable. Aim ≥90%. Note viability per donor — low viability raises baseline for both assays.
3. Resuspend in warm complete RPMI (with L-glutamine + 10% FCS) after counting.

---

## 4. Cell plating mixes

### 4A. PI plate — black 96-well plate

**Target per well:** 2 × 10⁴ cells, 5 µg/mL PI, 200 µL final (no LPS for UCN-01/DMSO/Triton wells). → Plating mix: cells at **1.11 × 10⁵/mL** + PI at **5.6 µg/mL** (= 5.6 µL of 1 mg/mL PI per 1 mL mix).

Per donor — make the following master mix, then split:

|Donor type|Master mix volume|Cells needed|PI (1 mg/mL) to add|
|---|---|---|---|
|Control / family member|2.6 mL|~2.9 × 10⁵|14.6 µL|
|Patient|2.6 mL|~2.9 × 10⁵|14.6 µL|

Split the 2.6 mL per donor into:

- **0.8 mL → primed (nigericin) portion:** add **8.8 µL of 1 µg/mL LPS** → 11 ng/mL in mix → 10 ng/mL final.
- **1.8 mL → unprimed portion:** for DMSO (3 wells), UCN-01 (3 wells), Triton (3 wells).

### 4B. IL-1β plate — clear 96-well plate

**Target per well:** 5 × 10³ cells, **no PI**, 200 µL final. All wells are LPS-primed. → Plating mix: cells at **2.78 × 10⁴/mL** + LPS at **11 ng/mL** (= 11 µL of 1 µg/mL LPS per 1 mL mix). No PI added.

Per donor — make one unified primed mix (all wells primed):

|Donor type|Mix volume|Cells needed|LPS (1 µg/mL) to add|
|---|---|---|---|
|All donors|1.2 mL|~3.3 × 10⁴|13.2 µL|

Conditions per donor on IL-1β plate: Unstimulated (baseline), DMSO (vehicle), UCN-01, LPS+Nigericin = 4 × 3 replicates = 12 wells × 180 µL = 2.16 mL → make 1.2 mL covers 6 wells + dead volume.

**Recalculate per donor for IL-1β plate:**  
12 wells × 180 µL = 2.16 mL → make **2.4 mL** per donor. Cells: 2.4 mL × 2.78 × 10⁴/mL = **6.7 × 10⁴ cells**. LPS: 2.4 mL × 11 ng/mL = **26.4 µL of 1 µg/mL LPS**.

---

## 5. Total cell requirement per donor

|Donor|PI plate|IL-1β plate|Total per donor|
|---|---|---|---|
|All donors|~2.9 × 10⁵|~6.7 × 10⁴|**~3.6 × 10⁵**|
|All 6 donors combined|—|—|**~2.1 × 10⁶**|

This is readily achievable from a single blood draw (20–30 mL heparinised blood typically yields 5–20 × 10⁶ monocytes after CD14 enrichment).

---

## 6. Plate maps

### Plate 1 — PI kinetic (black 96-well, Varioskan)

Rows = donors, column blocks = condition (triplicate). **Priming only in cols 7–9.**

```
         Col 1–3          Col 4–6          Col 7–9           Col 10–12
         DMSO             UCN-01           LPS + Nigericin   Triton (100%)
         (vehicle,        (12.5 µM,        (LPS 3h prime,    (0.1%, 15 min
         unprimed)        unprimed)        Nig 5 µM)         lysis ref)
Row A    P1 M694V/M694V   P1 M694V/M694V   P1 M694V/M694V    P1 M694V/M694V
Row B    P2 Duplication   P2 Duplication   P2 Duplication    P2 Duplication
Row C    Family 1 (Het)   Family 1 (Het)   Family 1 (Het)    Family 1 (Het)
Row D    Family 2 (Het)   Family 2 (Het)   Family 2 (Het)    Family 2 (Het)
Row E    Control 1 (HD)   Control 1 (HD)   Control 1 (HD)    Control 1 (HD)
Row F    Control 2 (HD)   Control 2 (HD)   Control 2 (HD)    Control 2 (HD)
Row G    uns1              uns2              uns3               PBS
Row H    PBS              PBS              PBS               PBS
```

- Rows G and H: fill with 200 µL PBS as evaporation moat.
- Cols 7–9 (nigericin) use the **LPS-spiked** plating mix. All other sample wells use the **unprimed** mix.
- 200 µL per well throughout.

### Plate 2 — IL-1β ELISA (clear 96-well, incubator)

**All wells LPS-primed.** Rows = donors, column blocks = condition (triplicate).

```
         Col 1–3          Col 4–6          Col 7–9           Col 10–12
         Unstimulated     DMSO             UCN-01            LPS + Nigericin
         (baseline)       (vehicle)        (12.5 µM)         (Nig 5 µM)
Row A    P1 M694V/M694V   P1 M694V/M694V   P1 M694V/M694V    P1 M694V/M694V
Row B    P2 Duplication   P2 Duplication   P2 Duplication    P2 Duplication
Row C    Family 1 (Het)   Family 1 (Het)   Family 1 (Het)    Family 1 (Het)
Row D    Family 2 (Het)   Family 2 (Het)   Family 2 (Het)    Family 2 (Het)
Row E    Control 1 (HD)   Control 1 (HD)   Control 1 (HD)    Control 1 (HD)
Row F    Control 2 (HD)   Control 2 (HD)   Control 2 (HD)    Control 2 (HD)
Row G    empty            empty            empty             empty
Row H    empty            empty            empty             empty
```

- No Triton on this plate (no normalisation needed; absolute pg/mL by ELISA standard curve).
- Unstimulated (cols 1–3) = LPS-primed but no second signal. Subtracts baseline cytokine from LPS priming alone.
- 200 µL per well.

---

## 7. Step-by-step timeline

Both plates follow the **same clock.** Prepare and plate them together.

---

**T = −3 h 15 min — Prepare plating mixes and plate both plates**

1. Prepare each donor's **PI plate master mix** (§4A): cells + PI at 1.11 × 10⁵/mL, 5.6 µg/mL PI.
    
    - Split: pull 0.8 mL → add LPS (primed portion, cols 7–9).
    - Remaining 1.8 mL = unprimed (cols 1–6 and 10–12).
2. Prepare each donor's **IL-1β plate mix** (§4B): cells at 2.78 × 10⁴/mL, no PI, LPS 11 ng/mL throughout.
    
3. Plate both plates: **180 µL/well** per the maps above.
    
4. Fill rows G–H of the PI (black) plate with 200 µL PBS (evaporation moat).
    

---

**T = −3 h — Start priming; incubate both plates in CO₂ incubator at 37 °C**

- PI plate: only cols 7–9 contain LPS; cols 1–6 and 10–12 rest in plain medium+PI (this is the "no priming" condition for UCN-01).
- IL-1β plate: all wells contain LPS; all wells prime for 3 h.

_During this window: set up and pre-warm the Varioskan LUX to 37 °C (§8)._

---

**T = 0 — Add stimuli to both plates simultaneously. Work quickly.**

Remove both plates from incubator. Keep warm.

**To PI plate (black):** Add 20 µL of 10× stimulus per well:

|Wells|Add|
|---|---|
|Cols 1–3 (DMSO)|20 µL 10× vehicle (1.25% DMSO)|
|Cols 4–6 (UCN-01)|20 µL 10× UCN-01 (125 µM)|
|Cols 7–9 (Nigericin)|20 µL 10× nigericin (50 µM)|
|Cols 10–12 (Triton)|20 µL 10× Triton (1%)|

Brief orbital mix (5–10 s). Load into Varioskan immediately. Start kinetic read.

**To IL-1β plate (clear):** Add 20 µL of 10× stimulus per well:

|Wells|Add|
|---|---|
|Cols 1–3 (Unstim)|20 µL medium only|
|Cols 4–6 (DMSO)|20 µL 10× vehicle (1.25% DMSO)|
|Cols 7–9 (UCN-01)|20 µL 10× UCN-01 (125 µM)|
|Cols 10–12 (Nigericin)|20 µL 10× nigericin (50 µM)|

Brief orbital mix. Return to CO₂ incubator at 37 °C for **90 min**.

---

**T = 0 → +105 min — PI kinetic read running on Varioskan (§8)**

Leave undisturbed.

---

**T = +90 min — Harvest IL-1β plate supernatants**

1. Remove IL-1β plate from incubator.
2. Centrifuge at **300 × g, 5 min, 4 °C** to pellet cells and debris.
3. Carefully collect **150 µL supernatant** per well into a labelled 96-well or Eppendorf tubes.
4. Freeze at **−20 °C** immediately, or proceed directly to ELISA.
    - Do not freeze-thaw more than once before ELISA.
    - Dilute FMF patient supernatants 1:5 to 1:10 before ELISA if signal exceeds standard curve.

---

**T = +105 min — PI kinetic read ends**

Export raw RFU data from SkanIt for analysis (§9).

---

## 8. Varioskan LUX / SkanIt setup (PI plate)

Set up and pre-warm during the 3 h priming window.

- **Measurement mode:** Fluorescence Intensity, **top read**, black plate.
- **Excitation:** 535 nm. **Emission:** 635 nm. (Try 617 nm if Triton window is too narrow.)
- **Dynamic range: FIXED — not Automatic.** The single most critical setting. Automatic rescaling between reads flattens a rising kinetic. Calibrate on a Triton well (brightest signal): set fixed range so Triton sits near the top but not over-range, baseline well above the floor. Lock for the entire run.
- **Measurement time:** increase integration time above default to improve signal/noise.
- **Z (focal) height:** optimise on a bright Triton well before starting.
- **Temperature:** 37 °C, chamber pre-warmed.
- **Kinetic protocol:** interval **5 min**, ~19 reads, total ~105 min. Either set a 15 min initial delay (so first read = 15 min post-stimulus) or start immediately and designate the 15-min read as baseline in analysis.
- **Shaking:** brief orbital 5–10 s before first read only.
- **No lid.**

---

## 9. Analysis — PI kinetic plate

### Normalisation (paper method)

Per well:

1. **Baseline subtraction:** subtract each well's first timepoint value (≈15 min) from all subsequent reads. This removes constant PI background and sets t = 15 min to 0%.
2. **Triton normalisation:** divide by the mean Triton signal (also baseline-subtracted) × 100.

> **% cell death(t) = [RFU(t) − RFU(15 min)] / [mean Triton(t) − mean Triton(15 min)] × 100**

### Derived metrics

- **Kinetic curve:** mean ± SEM per condition per timepoint.
- **AUC:** trapezoid rule. Retain to **60 min** for UCN-01; to **105 min** for nigericin.
- **Time to 20% cell death (t₂₀):** fit a 6th-order polynomial to each donor's normalised kinetic; interpolate t₂₀. Mark donors where average never reaches 20% as ND (not determined).

### Plots

- **Panel A:** mean ± SEM kinetics, grouped by genotype (one line per group).
- **Panel B:** AUC dot plot, one dot per donor, grouped by genotype.
- **Panel C (nigericin):** same kinetic/AUC layout confirming genotype-independent response.

---

## 10. Analysis — IL-1β plate

- Report absolute **pg/mL** from ELISA standard curve.
- Subtract unstimulated (cols 1–3) baseline from UCN-01 and nigericin values per donor.
- Plot as dot plot: one dot per donor, grouped by genotype. Show median ± IQR (non-parametric; data typically non-Gaussian across donors).
- Statistical comparison: Wilcoxon rank-sum test (FMF vs HD) once you have enough donors for meaningful testing; with n = 2 per group this run is exploratory — report individual values.

---

## 11. Expected results

### PI kinetic (unprimed UCN-01)

|Donor|Expected kinetic|Interpretation|
|---|---|---|
|**M694V/M694V**|Fast sigmoidal; t₂₀ ≈ 30–50 min; high AUC|Positive control — must fire|
|**Duplication (VUS)**|Unknown → M694V-like = pathogenic evidence; HD-like = non-pathogenic or below detection|Research question|
|Family members (Het)|HD-like or weakly intermediate|Expected low/null response|
|HD controls|Flat to 60 min; delayed late PI rise (apoptosis only)|Expected negative|

### PI kinetic (LPS + nigericin)

All six donors should show **similar robust pyroptosis** regardless of MEFV genotype. If a donor is flat here, the problem is the cells, not the biology.

### IL-1β ELISA (LPS-primed UCN-01)

|Donor|Expected IL-1β|Notes|
|---|---|---|
|**M694V/M694V**|High (hundreds–>1000 pg/mL)|Paper median ~422 pg/mL for FMF|
|**Duplication (VUS)**|Unknown → elevated = pathogenic evidence|Complementary to PI result|
|Family members|Low–moderate (variable)|Heterozygotes can be intermediate|
|HD controls|Low (<50 pg/mL typically)|Paper median ~25 pg/mL for HD|
|All donors, Nigericin|High and similar across genotypes|NLRP3; genotype-independent|

The two readouts should be concordant per donor: a VUS patient showing both fast pyroptosis AND elevated UCN-01-driven IL-1β is much stronger evidence of pathogenicity than either alone.

---

## 12. Quick troubleshooting

|Symptom|Likely cause|Fix|
|---|---|---|
|M694V flat on PI plate|Dynamic range on Automatic; degraded UCN-01 stock; reader not at 37 °C; low cell viability|Fix reader settings first; confirm fresh drug|
|M694V low IL-1β|Insufficient LPS priming; degraded UCN-01; LPS lot inactive|Check LPS with nigericin control — if nigericin also fails, LPS is the problem|
|Everything flat including nigericin|Cell health / isolation; reader settings; PI quality|Re-isolate cells, check reader|
|Narrow Triton window on PI plate|Fixed dynamic range not set; low integration time; Z-height not optimised|Set fixed DR, increase integration, re-optimise Z|
|Edge wells drift on PI plate|Evaporation|Keep 200 µL, PBS moat, no lid|
|IL-1β over range|FMF patient supernatant saturates kit|Dilute 1:5 to 1:10 and re-run|
|IL-1β low for everyone|Priming failed (LPS); UCN-01 degraded; wrong cell number on ELISA plate|Confirm with nigericin wells|

---

## 13. Reagent checklist for the day

- [ ] Fresh UCN-01 aliquot thawed from −80 °C, light-protected
- [ ] Complete RPMI: RPMI 1640 + L-glutamine (2 mM, added fresh) + 10% FCS, pre-warmed 37 °C
- [ ] PI stock 1 mg/mL
- [ ] LPS 1 µg/mL working (from 1 mg/mL, dilute 1:1000 in PBS or medium)
- [ ] Nigericin 10× (50 µM) working
- [ ] DMSO vehicle 10× (1.25%) working
- [ ] Triton X-100 10× (1%) working
- [ ] IL-1β ELISA kit at RT; standards prepared
- [ ] Black 96-well plate (Varioskan / PI)
- [ ] Clear 96-well plate (ELISA / IL-1β)
- [ ] Varioskan pre-warmed to 37 °C, dynamic range set and locked on a test Triton well
- [ ] CO₂ incubator at 37 °C

---

_Dry run recommendation: before using patient material, run THP-1 cells on the black plate only (UCN-01, DMSO, Triton) using the finalised Varioskan settings to confirm dynamic range, Z-height, and drug activity produce a clean sigmoidal curve. THP-1 is your validated responder from earlier experiments._