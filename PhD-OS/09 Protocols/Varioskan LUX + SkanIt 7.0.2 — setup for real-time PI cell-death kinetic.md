

**Instrument:** Thermo Varioskan LUX  **Software:** SkanIt 7.0.2 RE for Microplate Readers **Assay:** Real-time propidium iodide (PI) influx, black 96-well plate, top read, 37 °C, every 5 min for 105 min **Save the finished session as a template** (e.g. `PI_kinetics.skax`) and reload it for every donor / repeat so the configuration is identical run to run.

---

## Critical pre-checks (the things that cost time before)

1. **The instrument MUST be connected to the computer before anything works.** If SkanIt is not connected to the Varioskan, the incubator will not heat and the run cannot start. Confirm the instrument panel at the bottom-left of SkanIt shows **Varioskan LUX 3020-83516** with a green/active status dot, not greyed out. _(This was the cause of the earlier "won't heat / won't run" problem.)_
2. **The Varioskan LUX has no physical temperature control** — temperature is set only through SkanIt, and only once the instrument is connected.
3. Black 96-well plate, top read. No lid during the run.

---

## Step 1 — Connect instrument and start heating (do this FIRST, ~20 min before loading)

1. Confirm SkanIt shows the connected Varioskan at bottom-left.
2. The instrument status line shows the incubator. Set/enable the incubator to **37 °C**. When heating, the line reads e.g. **"Incubator: On — 23.8 °C → 37.0 °C"** (current → target, with a climbing arrow).
3. **Wait for it to reach and hold 37.0 °C** before loading cells or starting the run. This takes ~15–20 min from room temperature. A stable run shows the current temperature at ~36.9–37.0 °C with no climbing arrow.

> Do not start the run while the chamber is still climbing — pyroptosis is temperature-sensitive and the informative early kinetics (25–45 min) will be blunted if the plate starts cold.

---

## Step 2 — Build the protocol tree (Add Steps tab)

The protocol must have this exact structure and order:

```
Protocol
├── Shake 1                 ← runs once, before the loop
└── Kinetic Loop 1          ← the repeating timer
    └── Fluorescence         ← the measurement, INSIDE the loop
```

To build it:

1. **Add Steps → Shake** (under Control). Place it first.
2. **Add Steps → Kinetic Loop** (under Control). Place it after Shake.
3. **Select Kinetic Loop 1**, then **Add Steps → Fluorescence** (Fluorometry, single-wavelength — NOT Fluorescence Spectrum). This nests the measurement inside the loop.

> If the steps end up in the wrong order or the Fluorescence is not nested inside the Kinetic Loop, drag them in the session tree to fix it, or delete and re-add in the order above. _(We had to correct this once.)_

---

## Step 3 — Fluorescence step settings

Select the Fluorescence step and set:

|Parameter|Value|
|---|---|
|Multiple wavelengths|**OFF** (single pair only)|
|Excitation|**535 nm**|
|Emission|**635 nm**|
|Measurement time|**100 ms**|
|Optics|**Top**|
|Excitation bandwidth|**12 nm**|
|**Dynamic range** (Advanced parameters)|**FIXED — "Medium High"** (NOT Automatic)|

**Dynamic range is the single most important setting.** Leaving it on _Automatic_ lets the instrument rescale between reads, which flattens or distorts a rising kinetic and makes timepoints non-comparable. Set it to a fixed range (start at **Medium High**) and lock it for the whole run.

> If you earlier added a second wavelength pair (e.g. 530/617), **Remove** it — one pair only, to keep the cycle short.

---

## Step 4 — Kinetic Loop settings

Select Kinetic Loop 1 and set:

|Parameter|Value|
|---|---|
|Interval|**5 min**|
|Number of readings / duration|**21 readings** (≈105 min)|
|Use settle delay|**ON** (auto = 100 ms for 96-well; reduces movement noise)|
|Check temperature at start [°C]|**37** (ticked)|
|Check gas control at start|OFF|
|Measurement order|default raster (option 3) is fine|

> **"Check temperature at start" is a safety gate, not a heater** — it only verifies the chamber has already reached 37 °C and warns/blocks if not. It does **not** itself heat the instrument; that's Step 1. Keeping it ticked is good practice so a cold plate can't start by accident.

---

## Step 5 — Shake step settings

Select Shake 1:

- Type: **orbital**
- Duration: **5–10 s**
- This runs once at the start to mix the stimulus into the cells before the first read. No shaking happens during the loop (cells stay settled for consistent top-read signal).

---

## Step 6 — Plate Layout

1. Go to **Plate Layout**. Template: ANSI/SBS Standard, 96-well.
2. Assign sample wells: select the wells with cells (rows **A–F**, all 12 columns in this design) → Sample type **Unknown**.
3. Assign the PBS moat / empty wells (rows **G–H**) as **Blank** (or leave unassigned — they don't need reading).
4. Generic "Group 1 / Un0001…" labels are fine — you can map wells to donors/conditions yourself in analysis. (Optional: use **Sample groups** to pre-annotate by donor/condition if you prefer annotated exports.)

**Record the well map separately** (which row = which donor, which column block = which condition) so the export can be decoded. Reference layout for this assay:

|Rows|Columns 1–3|Columns 4–6|Columns 7–9|Columns 10–12|
|---|---|---|---|---|
|A–F = 6 donors|DMSO|UCN-01|LPS+Nigericin|Triton (100%)|

---

## Step 7 — Optimise Z-height (once, before the real run)

For a top read, the focal height matters. On a bright **Triton** well:

- Run the Z-height / focus optimisation (in the Fluorescence step or via the instrument optimisation option). SkanIt scans focal heights and picks the one giving maximum signal.
- Lock that Z value for the run.

While you're at it, do a quick test read of a Triton well and a baseline well to confirm **Medium High** dynamic range gives Triton near the top of range without saturating. If Triton saturates, drop to **Medium Low**; if the window is too small, try **High**.

---

## Step 8 — Final checks, then run

Before pressing **Start**:

- [ ] Instrument connected (green status)
- [ ] Incubator stable at **37.0 °C** (no climbing arrow)
- [ ] Protocol tree = Shake → Kinetic Loop → (Fluorescence nested inside)
- [ ] Fluorescence: 535/635, Top, 12 nm, 100 ms, **Dynamic range fixed (Medium High)**
- [ ] Kinetic Loop: 5 min × 21, settle delay ON, check-temp 37 ticked
- [ ] Plate layout assigned, well map recorded
- [ ] Z-height optimised
- [ ] Session saved

Add stimuli to the plate on the bench, brief gentle swirl, load immediately, press **Start**.

---

## During the run

- The Results view shows a **mini kinetic plot per well, building in real time** as each of the 21 reads comes in. This is normal — the numbers are still being recorded underneath (switch to the **List** tab any time to see them as a table). Plots instead of single numbers is simply because this is a time-course, unlike single endpoint reads.
- **Do not** open the drawer, switch views excessively, or disturb the instrument until 21/21.
- **Ignore Windows pop-ups** (e.g. "Update Microsoft Security Essentials"). Do not allow any update or restart during the run.
- A "Warnings during execution" dialog is usually non-fatal (most often "temperature not reached at start" from a too-early start). Click OK, read the run log, and check whether the early timepoints were collected cold. If so, re-run once stably at 37 °C.

---

## After the run (21/21 complete)

1. Click the **List** tab in Results to view the full numerical time-course (all wells × 21 timepoints). Sanity-check: values not all zero, not all saturated; Triton wells clearly higher than baseline.
2. Click **Export to Excel** (top-right of Results) to export the full matrix.
3. **Save the session** so data is stored with the protocol.
4. Note: the SpectraViewer panel may display a reference fluorophore label such as "Alexa Fluor 488" — this is a **cosmetic reference overlay only** and does not affect the measurement, which is acquired at your set 535/635.

---

## Analysis (recap — applied to the exported Excel)

- Per well: subtract the first timepoint (≈15 min) → set to 0% (removes constant PI background).
- Normalise to mean Triton (baseline-subtracted) = 100%.
    - % death(t) = [RFU(t) − RFU(15 min)] / [mean Triton − baseline] × 100
- AUC by trapezoid: retain to **60 min** for UCN-01, **105 min** for nigericin.
- Time-to-20% by 6th-order polynomial fit.
- Plot mean ± SEM kinetics (Panel A) and per-donor AUC (Panel B), grouped by genotype.

---

## Lessons captured from setup (so they aren't repeated)

- **Connect the instrument first** — nothing heats or runs otherwise.
- **Temperature is software-only** on this model; set it in SkanIt and wait for 37 °C.
- **"Check temperature at start" ≠ heater** — it's a gate; Step 1 does the heating.
- **Dynamic range must be fixed**, not Automatic, for a comparable kinetic.
- **Run automatically as a Kinetic Loop**, never as repeated manual reads — manual pull-and-return cycles cool the cells (pausing pyroptosis), give ragged intervals, disturb settled cells, and re-autoscale signal, all of which flatten and distort the data.
- **Don't start cold; don't disturb mid-run; ignore OS pop-ups.**