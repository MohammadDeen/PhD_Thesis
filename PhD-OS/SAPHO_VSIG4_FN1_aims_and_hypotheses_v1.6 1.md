# Functional Modelling of *VSIG4* and *FN1* Variants in SAPHO Syndrome

### Aims, hypotheses, predictions and falsification criteria

**Version 1.6 — 31 July 2026**

---

## 0. Summary

### 0.1 Disease frame

SAPHO/CNO is not Mendelian. It sits on a spectrum of autoinflammatory bone disease characterised by sterile osteitis, variable cutaneous inflammation, and lesions that are simultaneously osteolytic and hyperostotic (Furer et al., 2024; Zhao et al., 2021; Sergi et al., 2022). The recurring mechanistic theme is dysregulated monocyte/macrophage cytokine output, with reduced regulatory cytokines and increased inflammasome-associated signalling (Hedrich et al., 2020; Roberts et al., 2024), linked to osteoclastogenesis and excessive remodelling (Hetrick & Oliver, 2023).

Functional work on rare variants is therefore framed as testing **threshold/modifier** contributions, not causation — the framing the field applies to *FBLIM1* and *P2RX7*.

### 0.2 Central hypothesis

> SAPHO arises from a self-sustaining myeloid–matrix inflammatory loop in bone. *VSIG4* and *FN1* variants lower the activation threshold of that loop from opposite compartments: **VSIG4 by removing a myeloid brake** on complement-mediated clearance and on cell-intrinsic inflammatory restraint, and **FN1 by altering an osteoblast-derived matrix** that is simultaneously a structural scaffold and a potential DAMP reservoir. Neither variant is predicted to alter baseline output. Both are predicted to shift the stimulus–response curve leftward and to delay resolution.

**The design consequence:** every core experiment is a **dose–response or kinetic time-course**, not a single-dose endpoint. A single-concentration, single-timepoint assay will very likely return "no phenotype" and produce a false negative.

### 0.3 What is assumed versus what is tested

A hypothesis stated in language that implies its mechanism is already established cannot be tested. Nor can one softened until any result would confirm it. Each element below is therefore labelled by its actual evidential status.

**Assumed (literature-established; not tested here):**
- SAPHO/CNO is multifactorial and threshold-driven, converging substantially on innate myeloid cytokine dysregulation (Furer et al., 2024; Hedrich et al., 2020).
- VSIG4/CRIg is a macrophage complement receptor participating in uptake of C3b/iC3b-opsonised material (Dustin, 2016; Hajishengallis et al., 2017; Reis et al., 2019).
- VSIG4 expression is differentiation- and cytokine-dependent and is reduced on activation (Gorgani et al., 2011; Ma et al., 2015; Munawara et al., 2017; Reissing et al., 2021).
- Fibronectin is required for matrix organisation, mineralisation and integrin-mediated signalling (Karamanos et al., 2021; Efthymiou et al., 2020).

**Tested (candidate mechanisms — directional, named, falsifiable):**
- That VSIG4's restraint on human myeloid cells operates through NLRP3 priming and IL-1β maturation at the challenge doses used. The strongest prior is Huang et al. (*Sci Adv* 2019), showing increased *Nlrp3* and *Il-1β* transcription in *Vsig4*⁻/⁻ macrophages via VSIG4–MS4A6D–JAK2–STAT3–A20–NF-κB, extended by Chen et al. (2023), which characterises MS4A6D as the VSIG4 adapter controlling NLRP3 activation. Note that these are the same group, so this is an extension rather than independent replication. Complementary work implicates PI3K–Akt–STAT3, PDK2 and mitochondrial ROS (Li et al., 2017). All are predominantly mouse/primary-macrophage. **This is the primary candidate mechanism under test, not an assumption.**
- That either FN1 allele produces detectable protein.
- That matrix from FN1-perturbed osteoblasts primes naïve monocytes.

**Explicitly not assumed:**
- That IL-1β is the sole route. TNF, IL-6 and CXCL8 are carried as parallel endpoints throughout, since TNF, IL-6 and IL-17/23 signalling are all implicated in SAPHO/CNO and TNF blockade is established therapy (Hedrich et al., 2020; Furer et al., 2024; Wang et al., 2025).
- That impaired *C. acnes* clearance is an established SAPHO mechanism. Microbial involvement is best treated as a possible trigger or modifier rather than a sufficient explanation (Hedrich et al., 2020; Wang et al., 2025).

### 0.4 Hypothesis hierarchy

| Tier | Hypothesis | Prior strength |
|---|---|---|
| **Primary (H-A)** | Hemizygous loss or dysfunction of VSIG4 lowers the macrophage activation threshold by impairing complement-dependent clearance and weakening cell-intrinsic inflammatory restraint | High — clean model correspondence, replicated mechanism |
| **Secondary (H-B)** | Heterozygous FN1 truncating variants alter FN1 dosage, secretion or fibrillar assembly, producing an osteoblast matrix that modifies myeloid priming and bone-cell coupling | Moderate — plausible, but no established FN1 haploinsufficiency phenotype |
| **Exploratory (H-C)** | Where mutant FN1 transcripts escape NMD, truncated non-fibrillar products have dominant-negative or matrix-DAMP activity | Low prior, high payoff — must not be the starting assumption |

### 0.5 Patient material

| Gene | Patient | Variant | Protein | Exon | Zygosity | Predicted mechanism |
|---|---|---|---|---|---|---|
| VSIG4 | 292741 | c.370C>T | p.Gln124Ter | 2 | Hemizygous (male) | NMD → **null** |
| VSIG4 | 272356 | c.509C>T | p.Ser170Phe | 3 | Hemizygous (male) | Missense — unknown |
| FN1 | A | c.6547G>T | p.Glu2183Ter | 40 | Heterozygous | Independent question — see 2.4 |
| FN1 | B | c.3103C>T | p.Arg1035Ter | 20 | Heterozygous | Independent question — see 2.4 |

Transcript NM_007268 (VSIG4). Both VSIG4 patients are male and hemizygous; the two FN1 patients are unrelated and each heterozygous.

### 0.6 Model–patient correspondence

State this explicitly in the methods rather than leaving it implicit — it is the study's principal methodological strength:

- THP-1 and MUTZ-3 are both male-derived, single-X lines. A single-allele *VSIG4* disruption is a **hemizygous null — the exact ploidy of the patient genotype.**
- For patient 292741, the knockout is a **direct model of the predicted molecular consequence of the patient allele**, conditional on NMD and on absence of a relevant truncated product.
- For patient 272356, the knockout is a null background only. The variant requires cDNA add-back.
- For both FN1 patients, the dosage-matched and mechanism-matched model is an **endogenous heterozygous clone**, not a biallelic knockout and not a KO-plus-cDNA construct.


### 0.7 Designated primary endpoints

The programme contains many informative readouts. Without a designated primary among
them, power cannot be calculated and multiple testing becomes uncontrolled. One primary
endpoint is therefore fixed per arm; everything else is secondary or mechanistic.

| Arm | Primary estimand | Gate |
|---|---|---|
| **Study 1 — VSIG4** | A single omnibus **genotype × dose interaction** across the complete fitted stimulus–response curve for viable-cell-normalised IL-1β | — |
| **Study 2 — FN1, molecular** | A pre-specified **composite decision rule** across RNA, intracellular protein, secreted protein and matrix assembly — see below | — |
| **Study 2 — FN1, functional** | Matrix-induced **intracellular pro-IL-1β** in naïve monocytes | Only after the molecular gate is passed |

**Why omnibus rather than EC₅₀ alone.** Naming log EC₅₀ as the sole primary would reinstate the left-shift-only assumption that §3.2 exists to remove: if the true effect were on the ceiling or the resolution kinetics, the primary would fail and a real result would be demoted to a secondary finding. A single interaction test across the whole curve asks the question the hypothesis actually poses — *does genotype change the response?* — in one inferential step, with multiplicity controlled by construction.

**Key secondary estimands**, reported with confidence intervals to explain a positive omnibus result rather than to generate one: log EC₅₀ (lead parameter), E_max, Hill slope, and resolution half-time.

**The FN1 molecular gate is a decision rule, not a single test.** Study 2 is gated molecular triage, where forcing a single-estimand structure would be artificial: the question is whether *any* reproducible molecular abnormality exists, and the informative measurement differs by allele. The gate is therefore a pre-specified composite, passed when **at least one** of the following is met **for a given allele**, reproducibly across ≥2 independent experiments:

| # | Criterion | Measured as |
|---|---|---|
| 1 | Allelic transcript ratio departs from 50:50 beyond a pre-declared margin | Allele-specific RT-PCR / amplicon sequencing |
| 2 | Total *FN1* transcript reduced relative to matched controls | qPCR |
| 3 | Truncated protein detected at the predicted size | N-terminal immunoblot, lysate and medium |
| 4 | Intracellular:secreted protein ratio altered | Paired N-/C-terminal immunoblot |
| 5 | Assembled matrix reduced | DOC-insoluble fraction |

Each allele is assessed independently (§6), and the criterion met is reported — the branch reached (A, B or C) follows from *which* criterion fires, not merely that one did.

**For the functional experiment, intracellular pro-IL-1β is primary and NF-κB activation is supportive.** Pro-IL-1β is the specific priming output the central hypothesis names; NF-κB activation is more proximal but also more general, and would respond to stimuli with no bearing on the loop under test.

**Dose-range requirements.** EC₅₀ is only interpretable when both asymptotes are adequately observed, so the concentration range must be wide enough to define them; this is established in the S1-0 pilot, not assumed. Area under the curve is sensitive to the range chosen, so it is reported only over a concentration interval **fixed in advance**, and as a descriptive summary rather than an inferential endpoint.

Other secondary endpoints — clearance, osteoclastogenesis, mineralisation, secretome, chemotaxis — are reported with the multiplicity correction stated in §8.3 and are not used to claim a positive result on their own.

---

## 1. Programme structure

The full four-aim programme is too broad to execute as a single linear project. It is therefore split into two linked studies with an explicitly contingent third component.

| | Content | Status |
|---|---|---|
| **Aim 0** | Molecular triage — shared, mandatory, precedes all editing at scale | Gate for both studies |
| **Study 1** | VSIG4 allelic loss of function in SAPHO | Primary; proceeds first |
| **Study 2** | FN1 variant mechanism and matrix–myeloid coupling | Secondary; gated on Aim 0.4 |
| **Contingent aim** | Factorial matrix × precursor coupling | Begins only if Study 2 yields a reproducible phenotype |

The two studies share Aim 0, the cell lines, and the myeloid readout platform, but are independently publishable and independently falsifiable.

---

## 2. Aim 0 — Molecular triage (mandatory before scaled editing)

### 2.1 Population genetics (days)

| Query | Why it matters | Disqualifying result |
|---|---|---|
| gnomAD **hemizygous male** count for VSIG4 p.Gln124Ter and p.Ser170Phe | For an X-linked gene this is close to decisive | Healthy hemizygous males carrying the allele |
| FN1 pLoF constraint (pLI, LOEUF) and raw high-confidence pLoF count | FN1 is very large; large genes accumulate pLoF. If heterozygous FN1 truncation is common, neither variant can be a strong driver | High pLoF tolerance |
| Presence of FN1 c.3103C>T specifically | CGA→TGA at arginine is the commonest nonsense class in the genome (CpG deamination hotspot). Recurrence is **not** evidence of selection | Present at appreciable frequency |

**Reviewer problem to confront here, not later.** No established FN1 disorder is caused by truncating variants. SMDCF arises from heterozygous missense variants affecting conserved N-terminal residues — particularly cysteines — that impair secretion and cause intracellular retention rather than haploinsufficiency (Lee et al., 2017; Costantini et al., 2019). Fibronectin glomerulopathy is likewise associated with heterozygous missense variants altering fibronectin interactions and deposition (Qiu et al., 2023; Sun et al., 2026). More broadly, ECM disorders arise through quantitative deficiency, dominant-negative matrix incorporation, or intracellular retention with ER stress (Lamandé & Bateman, 2019). **FN1 haploinsufficiency has no established human disease phenotype.**

If constraint data are permissive, FN1 is reframed as a candidate modifier and VSIG4 carries the primary narrative — which it can, given a bona fide hemizygous null.

### 2.2 Annotation and transcript checks (hours)

- **Confirm FN1 exon 40 is constitutive** in the transcripts actually expressed by macrophages and osteoblasts. FN1 has 47 exons including three alternatively spliced ones (EDA, EDB, V/IIICS); the V/IIICS region lies in the C-terminal third, not far from codon 2183. If exon 40 is alternatively spliced, both the patient variant and guides AX/AV/AI affect only the isoforms that include it — and NMD prediction changes with transcript architecture.
- **Confirm exon inclusion for exon 20** in the same transcripts.
- **Confirm VSIG4 guides AD/AA/AT target exons present in all expressed isoforms.** VSIG4 has long and short isoforms differing by an Ig-like C2 domain.
- **Map residue S170** onto the CRIg–C3b co-crystal (Wiesmann et al., 2006). Note that heparan sulphates compete with C3b/iC3b for overlapping binding regions on VSIG4 (Ebstein et al., 2023), so a missense variant in this region could affect complement binding, heparan-sulphate binding, or both. Both must be assayed.

### 2.3 VSIG4 patient material — **DECISION NODE 1**

VSIG4 is a monocyte/macrophage gene, so PBMCs are the appropriate tissue and the absence of fibroblasts is not a limitation. Differentiate PBMC-derived monocytes with M-CSF, then measure surface VSIG4 by flow cytometry.

| Result | Interpretation | Consequence |
|---|---|---|
| 292741 absent | Confirms null | KO is a validated model of this allele |
| 272356 absent | S170F causes misfolding/degradation | KO is a fair model of this allele too |
| 272356 present at normal level | S170F is a binding or signalling defect | **KO is the wrong model** — cDNA arm becomes essential |

*Confounders:* glucocorticoids induce VSIG4/CRIg — record medication status at draw and include treated and untreated controls. Activation state also matters, since activated macrophages downregulate, internalise or shed VSIG4 (Reissing et al., 2021); standardise the differentiation protocol and the interval to measurement.

### 2.4 FN1 allele-specific analysis — **DECISION NODES 2a and 2b (independent)**

NMD depends on premature-termination position relative to downstream exon–exon junctions in the *relevant cellular transcript*, and alternative splicing makes this transcript-specific. The exon 20 allele is more intuitively NMD-compatible than the late exon 40 allele, but neither can be inferred. **The two alleles are two independent molecular questions and may give opposite answers.**

For **each allele separately**, obtain:

1. Genomic DNA allelic ratio (baseline)
2. cDNA allelic ratio (allele-specific RT-PCR or amplicon sequencing)
3. Total FN1 transcript abundance versus controls (qPCR)
4. NMD perturbation (cycloheximide or *UPF1* knockdown) — recovery of the mutant peak
5. Intracellular FN1 protein, **N-terminal and C-terminal antibodies in parallel**
6. Secreted FN1 in conditioned medium, same two antibodies
7. Non-reducing SDS-PAGE — dimer versus monomer
8. DOC-insoluble fraction — assembled matrix

**Why paired antibodies are mandatory.** A C-terminal antibody cannot detect p.Glu2183Ter product. Using it alone, NMD and truncation are indistinguishable — both read as absence of protein.

| N-terminal signal | C-terminal signal | Interpretation |
|---|---|---|
| ~50% reduced | ~50% reduced | NMD → haploinsufficiency |
| Near-normal, plus band at predicted truncated size | ~50% reduced | Truncated protein produced (NMD escape) |
| Reduced, no truncated band | Reduced | NMD, **or** truncated product retained/degraded intracellularly — check lysate separately |

**Predicted truncated products, if NMD escapes:**

| | p.Arg1035* (exon 20) | p.Glu2183Ter (exon 40) |
|---|---|---|
| Position | ~FNIII4–5 of 2386 aa | 203 residues from C-terminus |
| RGD / synergy site | Lost | Retained |
| Hep-II | Lost | Retained |
| EDA / EDB / V | All lost | EDA/EDB retained |
| FNI 10–12 + interchain cysteines | Lost | Lost |
| Dimerisation | No | No |
| Predicted product | Assembly domain + gelatin-binding + ~4 FNIII repeats (~110–120 kDa predicted; higher observed with glycosylation) | Near-full-length **monomer** (~235–245 kDa) |

*Practical note:* resolving a ~240 kDa truncation from ~260 kDa wild-type requires low-percentage gels and extended runs. The exon 20 product is trivially resolvable by comparison.

**Add ER retention to the differential.** Because intracellular retention is the *established* mechanism in FN1 skeletal disease (Lee et al., 2017; Lamandé & Bateman, 2019), measure intracellular versus secreted FN1 ratio and ER stress markers (*HSPA5*/BiP, *DDIT3*/CHOP, *XBP1* splicing). A retention phenotype would be a third mechanism, distinct from both haploinsufficiency and secreted-DAMP.

*Caveat on tissue:* FN1 expression in whole blood is modest. Verify transcript abundance before committing sample; monocyte-derived macrophages from the same PBMCs express FN1 and provide a second attempt.

*Free proxy:* the exon 40 and exon 20 frameshift clones generated here. Measure FN1 mRNA by qPCR against NT controls — reduced transcript indicates NMD operates at that position.

### 2.5 VSIG4 expression window (prerequisite for all of Study 1)

VSIG4 is enriched in relatively resting or tissue-resident macrophage states. It is induced by M-CSF, IL-10, dexamethasone and vitamin D3, suppressed by LPS, IFN-γ, TNF and PMA, and reduced on activation through downregulation, internalisation or shedding (Gorgani et al., 2011; Munawara et al., 2017; Reissing et al., 2021). PKCα is a further regulatory handle demonstrated in human monocyte-derived macrophages (Ma et al., 2015). It also declines steeply during osteoclastogenesis.

> **The single largest risk to Study 1 is performing the challenge in a condition where wild-type cells do not express VSIG4 either.** A knockout of a silent gene has no phenotype.

*Deliverable:* qPCR + flow/Western time-course across **several differentiation protocols** defining a VSIG4-high condition in each line. All subsequent challenges are timed to that window, and surface VSIG4 is measured **immediately before challenge** in every functional experiment, not merely at protocol design.

*Design tension to state openly:* the pro-inflammatory stimuli under test themselves suppress VSIG4. Prime-and-challenge protocols must be timed so the wild-type comparator still expresses VSIG4 at the moment of challenge.

### 2.6 Recombinant 70 kDa FN fragment — assay development, not go/no-go

A soluble recombinant fragment differs from osteoblast-secreted mutant FN in folding, glycosylation, concentration, oligomeric state, matrix association, mechanical unfolding, proteolytic processing, and co-presentation with other matrix molecules. The general principle that remodelled ECM yields immune-active DAMPs signalling through integrins and TLRs is supported (McQuitty et al., 2020; Quan, 2026), but this does not establish that this specific fragment primes THP-1 or MUTZ-3.

- **If it primes:** you have the positive control and the dose–response reference for every decellularised-matrix experiment downstream.
- **If it does not prime:** the *soluble-fragment* version of the hypothesis is weakened. The mutant-matrix hypothesis is not refuted, and Study 2 proceeds.

### 2.7 Go/no-go criteria

**Proceed with Study 1 (VSIG4) if:**
- WT cells have measurable surface VSIG4 in at least one differentiation condition, **and**
- knockout eliminates it, **and**
- patient 292741 macrophages show absent or strongly reduced expression.

**Proceed with Study 2 (FN1) if at least one of:**
- reduced total FN1 transcript,
- mutant transcript escape,
- truncated protein detected,
- altered secretion or intracellular retention,
- altered fibril assembly,
- reproducible matrix-composition change.

---

## 3. STUDY 1 — VSIG4 allelic loss of function

### 3.1 Baseline characterisation

**Prediction: no difference.** Unstimulated IL-1β, IL-6, TNF and CXCL8 should be indistinguishable between KO and NT clones.

> **A baseline difference is a mechanistic reclassification, not a failure.** It would reject the narrow threshold model in favour of constitutive activation — but constitutive activation is still a VSIG4 phenotype, and arguably a more striking one. The programme continues down the same experimental path; only the description of the mechanism changes. This distinction matters because treating it as falsification would discard a positive result.

### 3.2 Threshold phenotyping — the core experiment

**Staged stimulus design.** Begin with defined, well-characterised reagents; add disease-relevant stimuli only after a reproducible phenotype exists.

| Stage                | Priming (signal 1)                                   | Activation (signal 2)                                                                    |
| -------------------- | ---------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| A — establish        | Pam3CSK4, graded                                     | ATP or nigericin, graded                                                                 |
| B — bone-relevant    | Pam3CSK4                                             | Basic calcium phosphate / hydroxyapatite crystals (Pazár et al., 2011; Jin et al., 2011) |
| C — disease-relevant | Heat-killed *C. acnes*, MOI 0.1–1 (Qin et al., 2014) | BCP crystals                                                                             |

**Mandatory readout set.** Measuring secreted IL-1β alone conflates priming, translation, assembly, caspase-1 activation, membrane damage, pyroptosis and ordinary cell death. Without separation, increased IL-1β may simply reflect increased death — and this failure mode produces a *positive-looking* result, which is the dangerous direction.

| Layer | Readout | Purpose |
|---|---|---|
| Priming | *NLRP3* and *IL1B* mRNA; intracellular pro-IL-1β (31 kDa, WB) | Transcriptional priming and translation |
| Assembly | ASC speck formation (imaging); caspase-1 p20 (WB) | Inflammasome-specific activation |
| Release | Mature IL-1β p17 (WB); IL-1β ELISA | Effector output |
| Membrane | GSDMD cleavage (WB) | Distinguishes regulated release from lysis |
| Cytotoxicity | LDH release; viable cell count | Normalisation denominator |
| **Normalisation** | **Cytokine per 10⁵ viable cells** | **Prevents death-driven false positives** |
| Parallel axes | TNF, IL-6, CXCL8 | Detects inflammasome-independent routes |

**Prediction (H1.2):** VSIG4 loss lowers the activation threshold. The P2RX7 CNO precedent showed a left shift with preserved maximum (Charras et al., 2024; Roberts et al., 2024), but that is one of several ways a threshold can fall, and committing to it alone risks scoring a real effect as negative.

**Four parameters are therefore pre-specified as distinct, individually reportable outcomes**, fitted from complete curves rather than compared at single doses:

| Parameter | Interpretation if altered |
|---|---|
| **EC₅₀** | Threshold shift — the P2RX7-type result, and the lead secondary parameter |
| **E_max** (upper asymptote) | Altered ceiling — greater maximal output, not merely earlier |
| **Hill slope** | Altered cooperativity or switch-like behaviour of the response |
| **Resolution kinetics** | Failure to terminate — time to 50% decay from peak |

Curves are fitted with a four-parameter log-logistic model including a **genotype × dose** interaction; kinetics with a **genotype × time** interaction. All four parameters are reported with confidence intervals whether or not they differ.

**Inferential step.** The single pre-specified test is the omnibus genotype × dose interaction (§0.7) — formally, an extra-sum-of-squares comparison between a model with parameters shared across genotypes and one allowing them to differ. The four parameters above are then estimated to explain *how* the curve moved. They are interpretive, not four separate chances at significance.

**Effect size for powering:** a 2-fold shift in EC₅₀ is the reference effect used for the power calculation (§8.1), chosen because it is the best-characterised parameter and the one with a published precedent; it is not a threshold the result must meet.

**Falsified if:** the omnibus genotype × dose interaction is null across an adequately ranged curve, on viable-cell-normalised output.

> **Resolution kinetics is a key secondary endpoint, not a second primary test.** An earlier formulation required *both* the dose and the time interaction to be null before H1.2 was falsified, which silently granted resolution independent confirmatory status and reopened the multiplicity problem. Dose–response is now the sole inferential test.

> The trade-off is accepted deliberately: if the primary is null but the genotype × time interaction on resolution is strong, H1.2 **as stated** is not supported, and a distinct "failure to terminate" hypothesis is generated. That result is reported as hypothesis-generating and requires prospective confirmation in an independent experiment designed around resolution as its primary endpoint. It is not used to rescue H1.2 post hoc.

### 3.3 The complement/clearance arm

VSIG4/CRIg participates in recognition and uptake of complement-opsonised material (Dustin, 2016; Hajishengallis et al., 2017; Reis et al., 2019); CRIg-high resident macrophages show markedly increased binding and internalisation of C3-opsonised particles (Gorgani et al., 2008). CRIg-edited THP-1 experiments support roles in adhesion, phagocytosis and killing of Gram-positive *S. aureus* (Perveen et al., 2026) — a near-exact methodological precedent worth reading before designing this assay.

**Critical protocol correction:** the current MUTZ-3 medium uses heat-inactivated FBS, which has no functional complement. **This experiment is impossible as currently written.**

**Design — 2 × 2 minimum, expanded:**

| Axis | Conditions |
|---|---|
| Genotype | WT / VSIG4-null (and, later, rescue lines) |
| Serum | Active normal human serum / heat-inactivated NHS / C3-depleted NHS ± reconstitution |
| Particle | Opsonised *C. acnes* / opsonised second Gram-positive particle (*S. aureus* or zymosan) / non-opsonised control |
| Competition | ± heparin or heparan sulphate, to test HS-versus-C3b binding contributions (Ebstein et al., 2023) |

**Readouts:** surface binding versus internalisation (quench or pH-sensitive dye); intracellular killing/persistence (CFU time-course); viable-cell-normalised cytokines; surface VSIG4 measured immediately before challenge.

Pairing *C. acnes* with a defined TLR2 agonist and a second opsonised particle distinguishes organism-specific effects from general complement-receptor biology — necessary, because defective *C. acnes* clearance is **not** an established SAPHO mechanism (Hedrich et al., 2020; Wang et al., 2025).

**Prediction (H1.3):** reduced uptake of opsonised particles by VSIG4-null cells in complement-active serum, with no difference in heat-inactivated serum.

**Falsified if:** uptake is complement-independent, or unaffected by VSIG4 status in active serum.

### 3.4 The osteoclast arm

VSIG4 declines steeply during osteoclastogenesis and its overexpression suppresses osteoclast formation (Miao et al., 2024). This implies VSIG4 **gates entry** into the lineage rather than setting its magnitude.

**Prediction (H1.4):** a leftward EC₅₀ shift in a **RANKL dose–response**, not a higher plateau. Readouts: TRAP⁺ multinucleated cell count, fusion index (DiI/Hoechst), normalised fusion events, fusion gene panel (CD9, CD44, CD47, DCSTAMP, OCSTAMP), resorbed area per nucleus.

*Timing risk:* VSIG4 may disappear before a differentiation phenotype manifests. Manipulate the early commitment window and document VSIG4 kinetics across differentiation in parallel.

**Falsified if:** the RANKL response curve is unshifted.

*Source-quality caveat:* the VSIG4–osteoclast link rests on a single 2024 overexpression-only study with no knockout confirmation and no independent replication. The knockout data reported here would be the **first loss-of-function test** of that claim — a contribution, but not a prior this study can lean on.

### 3.5 The allelic series — the arm that answers the clinical question

| Construct | Purpose |
|---|---|
| KO + empty vector | Baseline |
| KO + WT VSIG4 cDNA | **Rescue control — indispensable** |
| KO + p.Gln124Ter | Confirms the null (expected: no rescue) |
| KO + p.Ser170Phe | Does the variant allele retain function? |
| WT background + p.Ser170Phe | Dominant-negative test |

**Expression-level matching is mandatory.** VSIG4 signalling is anti-inflammatory (Li et al., 2017), so overexpression may suppress inflammation nonspecifically and make a partially functional variant appear normal. Use a titratable/inducible promoter or FACS-sort for **matched surface VSIG4**, and report only surface-expression-matched comparisons. Endogenous knock-in is preferable where feasible.

Without a successful WT rescue, a knockout phenotype cannot be confidently attributed to VSIG4.

**H1.5 — the strongest available internal control:** *if p.Ser170Phe phenocopies p.Gln124Ter across the threshold assays, that is strong evidence S170F is loss-of-function.* An allelic series within one gene from one disease cohort is considerably more persuasive than either variant alone. **The VSIG4 report should be built around this comparison rather than around each variant separately.**

For p.Gln124Ter specifically, agreement between **patient macrophages, knockout cells and WT rescue** is substantially more convincing than clone replication alone.

---

## 4. STUDY 2 — FN1 variant mechanism and matrix–myeloid coupling

### 4.1 Model hierarchy

A knockout-plus-mutant-cDNA design is useful for biochemical characterisation but is not a faithful model of a heterozygous patient, particularly if the mechanism is dominant-negative. The patient context contains one WT allele, one mutant allele, physiologically regulated expression, normal alternative splicing, and potentially mixed WT–mutant assembly intermediates. Strong cDNA expression in an FN1-null cell will exaggerate secretion defects, fragment abundance and DAMP activity.

| Rank | Model | Role |
|---|---|---|
| 1 | **Endogenous heterozygous frameshift clones** | **Primary patient model** |
| 2 | Endogenous biallelic KO | Mechanistic comparator / signal amplifier |
| 3 | KO + mutant cDNA | Domain dissection and dominant-negative testing **only** — never presented as a patient model |
| 4 | WT background + mutant cDNA | Dominant-negative test on an intact background |

**A point worth stating explicitly:** a CRISPR frameshift near codon 2183 reproduces the functional lesion of p.Glu2183Ter in kind — both lose the interchain cysteines, and both arise at an NMD-competent position. Endogenous heterozygous exon 40 clones therefore model **both** branches reasonably well, not merely the haploinsufficiency branch. The same logic applies to exon 20 clones.

> **But equivalence is per allele, not per locus.** Different indels at the same cut site terminate at different downstream residues, produce different terminal amino-acid sequences, may differ in NMD behaviour, and some will be in-frame. **The phenotypic unit is the individually sequenced allele, not "exon-40 edited."** Every clone is reported by its actual genotype — indel size, predicted termination codon, predicted NMD status — and clones are grouped for analysis by predicted consequence rather than by guide.

> *Validation contingency:* if a phenotype derived from regional frameshift clones becomes a headline result, it should be confirmed by exact heterozygous knock-in or prime editing of the patient nucleotide before publication. This is a contingency on a major finding, not a prerequisite for the programme.

> **Clone-selection criteria.** Heterozygous clones are the *most* valuable clones in the FN1 experiment and must not be discarded. Any screening rule that rejects clones retaining a wild-type allele will eliminate the primary patient model. Bank hets from every plate.

### 4.2 FN1 in the osteoclast lineage — pre-specified decision tree

Fibronectin's effects on osteoclasts are bidirectional. In at least one system, FN reduced osteoclast formation and fusion while *increasing* the activity of mature osteoclasts and increasing IL-1β-associated signalling (Gramoun et al., 2010). A single directional prediction is therefore inadequate.

**Primary prediction (retained):** adhesion/cytoskeletal effect — normal TRAP⁺ multinucleation with impaired F-actin ring integrity and reduced resorption per cell.

**All outcome classes pre-specified in advance**, so that whichever occurs is interpreted rather than narrated post hoc:

| Outcome | Interpretation |
|---|---|
| TRAP⁺ MNC number ↓, resorption per cell normal | Differentiation/commitment effect |
| TRAP⁺ number normal, nuclei per cell ↓ | Fusion effect |
| Both normal, F-actin ring disrupted, resorption per cell ↓ | **Adhesion/cytoskeletal effect (primary prediction)** |
| TRAP⁺ ↓ and resorption per cell ↑ | Gramoun-type: FN suppresses formation while restraining mature activity |
| Survival markers altered across the board | Survival effect — check before interpreting anything else |
| Viability ↓ generally | Generic defect — reject and troubleshoot |

**Falsified if:** no outcome class is reached — all parameters superimpose on controls.

*Confounder:* FN1 is both cell-derived and serum-derived. Use FN-depleted serum throughout and distinguish differentiation from resorption explicitly.

### 4.3 SAOS-2 cell-autonomous phenotype — reframed for hyperostosis

SAPHO shows excess bone formation alongside osteitis. The prediction is therefore **not** "mineralisation decreases."

**Prediction (H2.1):** exaggerated ALP activity and Alizarin red / von Kossa mineralisation **under inflammatory cytokine load** (IL-1β, TNF, oncostatin M — dose–response). Baseline mineralisation may be normal or reduced.

Supporting readouts: DOC-insoluble fraction assay; collagen I fibril organisation by IF; non-reducing SDS-PAGE for dimer versus monomer; qPCR panel (RUNX2, SP7, COL1A1, ALPL, BGLAP, IBSP); ER stress markers and viability.

*Model caveat:* SAOS-2 is transformed and not a faithful primary osteoblast. Use it for screening; validate key findings in primary osteoblasts or iPSC-derived osteoblasts before mechanistic claims.

### 4.4 Secretome coupling

**Prediction (H2.2):** FN1-perturbed osteoblasts become inflammatory amplifiers — increased IL-6, CXCL8, CCL2 and an increased RANKL/OPG ratio. CXCL8 matters specifically: SAPHO is neutrophil-driven, and a Transwell neutrophil chemotaxis assay on conditioned medium connects the osteoblast arm directly to pustulosis and sterile neutrophilic osteitis.

*Mandatory controls:* broad cytokine changes may be secondary to cellular stress. Include ER stress markers, viability, and total protein normalisation before interpreting any secretome change as specific.

**Falsified if:** no change in CXCL8/IL-6 output or neutrophil chemotaxis once stress and viability are controlled.

### 4.5 Matrix-as-DAMP

Generate decellularised matrix from WT and heterozygous-edited SAOS-2 by the 47 °C heat method (Weng et al., 2021), which on a Saos-2 matrix removed cellular constituents, inactivated alkaline phosphatase and preserved calcium deposition without the recellularisation cytotoxicity seen with SDS. Reseed naïve THP-1/MUTZ-3 and apply defined low-level priming.

*Encouraging precedent:* in that study the decellularised Saos-2 matrix supported osteoclast differentiation and mineralisation better than an inorganic calcium-phosphate matrix or plastic — so the assay platform is known to be permissive for the readout this Aim depends on.

**Primary readout: intracellular pro-IL-1β**, with NF-κB activation supportive (§0.7) — i.e. *priming*, measured before any second signal. Then apply a standard second signal to test whether the matrix has shifted the activation threshold. This separates matrix-driven priming from direct inflammasome activation.

**Prediction (H2.3):** matrix from FN1-perturbed osteoblasts primes naïve monocytes for IL-1β release relative to WT matrix, and this survives serum FN depletion.

**Falsified if:** the difference disappears after serum fibronectin depletion — implicating plasma FN rather than osteoblast cellular FN.

*Mandatory controls.* Residual cellular material and serum FN are the two variables most likely to dominate this assay, and decellularisation itself is a confound:

| Control | Guards against |
|---|---|
| DNA/nuclear staining; residual cellular contaminant assessment | Cell debris driving the priming signal |
| FN-depleted serum **plus purified plasma-FN add-back** | Depletion is itself a biological perturbation; add-back separates FN loss from serum depletion generally |
| Matched growth, viability, adhesion and matrix quantity | Genotype differences in how much matrix is deposited rather than what kind |
| Normalisation to matrix area or total matrix protein | Same |
| **An orthogonal decellularisation method** | See below — this one is not optional |
| Naïve cells through the identical heat/decellularisation workflow with no osteoblast matrix | Workflow artefacts mistaken for matrix signal |
| Assays distinguishing altered FN quantity from altered overall matrix composition | Attributing a general matrix defect to fibronectin specifically |

> **Why the orthogonal method is required rather than advisable.** The 47 °C protocol may act differently on a structurally abnormal matrix than on a normal one. A genotype difference measured *after* decellularisation is therefore not automatically evidence about the matrix as it existed *before*. Concordance across two decellularisation chemistries substantially strengthens the interpretation, because a method-specific artefact would have to operate identically through two different mechanisms — but it reduces rather than eliminates the possibility, and the residual uncertainty should be stated when the result is reported. One chemistry alone leaves the question open. This confound is specific to the present hypothesis, because the hypothesis is precisely that the mutant matrix is structurally abnormal.

### 4.6 Constructs — domain dissection only

Full-length FN1 cDNA is ~7.2 kb, at the edge of lentiviral packaging. FN1(1–1034) is ~3.1 kb and trivially clonable — so the most mechanistically interesting construct is also the easiest to build.

| Construct | Question |
|---|---|
| FN1-KO SAOS-2 + WT FN1 cDNA | Rescue control |
| FN1-KO SAOS-2 + FN1(1–1034) | Does the N-terminal fragment block assembly and prime monocytes? |
| FN1-KO SAOS-2 + FN1(1–2182) | Does the monomer do the same by a different route? |
| WT SAOS-2 + FN1(1–1034) | Dominant-negative test on an intact background |

**These are biochemical experiments, reported as such.** They test what the truncated products *can* do, not what the patients' cells *do* do. Expression levels must be reported and, where possible, matched to endogenous FN1.

---

## 5. Contingent aim — factorial coupling

**Begins only after a reproducible phenotype exists in one compartment.** Complex interpretation and multiplicative variability make this uninterpretable if run early.

| | WT matrix | FN1-edited matrix |
|---|---|---|
| **WT precursors** | Baseline | Matrix contribution |
| **FN1-edited precursors** | Cell-intrinsic contribution | Additive or redundant? |

If osteoclast-derived FN rescues on an edited matrix, the two sources are redundant and the patient phenotype is dose-dependent. If not, matrix FN performs a function osteoclast FN cannot.

---

## 6. Decision nodes

**NODE 1 — VSIG4 surface expression in patient macrophages.** If p.Ser170Phe is present at normal surface levels, the knockout does not model it and the cDNA arm moves from supporting to essential. If absent, the knockout models both patients and Study 1 simplifies considerably.

**NODE 2a — FN1 exon 20 (p.Arg1035*) NMD status.** Independent question.

**NODE 2b — FN1 exon 40 (p.Glu2183Ter) NMD status.** Independent question. Late truncation; may undergo NMD or may generate near-full-length monomer depending on transcript architecture.

**Branch outcomes, applied per allele:**

| Branch | Finding | Consequence |
|---|---|---|
| **A** | Mutant transcript degraded | Haploinsufficiency. Model = heterozygous clones. Question narrows to: *is 50% fibronectin sufficient to alter monocyte priming?* Reviewer risk high (no established FN1 haploinsufficiency phenotype) |
| **B** | Transcript survives, protein secreted | Bioactive fragment or monomer. Exploratory hypothesis H-C activated; Section 4.5 becomes the centrepiece |
| **C** | Transcript survives, protein retained intracellularly | ER retention mechanism — matches established FN1 skeletal disease biology (Lee et al., 2017). Readouts shift to ER stress and secretion, not matrix DAMP |

**The two alleles may land in different branches.** In that case the patients are mechanistically distinct and must be reported separately, not pooled.

*Note:* transcript recovery after NMD inhibition is informative but does **not** prove a stable secreted protein is produced physiologically. Branch B requires protein-level evidence in conditioned medium, not transcript evidence alone.

---

## 7. Consolidated controls and confounders

| # | Confounder | Consequence if ignored | Control |
|---|---|---|---|
| 1 | **Plasma fibronectin in FBS** | Adsorbs to plastic and matrix; masks FN1 phenotype. Most likely single cause of a false negative | Gelatin-Sepharose 4B depletion validated by anti-FN immunoblot (Sabatier et al., 2009; principle: Engvall & Ruoslahti, 1977, 1978); serum-free intervals during matrix assembly |
| 2 | **Heat-inactivated FBS has no complement** | Clearance arm cannot work | Active NHS, heat-inactivated NHS, C3-depleted ± reconstituted |
| 3 | **VSIG4 not expressed in undifferentiated cells** | KO of a silent gene shows nothing | Establish expression window; measure surface VSIG4 immediately before every challenge |
| 4 | **Activation-induced VSIG4 shedding/internalisation** | Wild-type comparator loses VSIG4 mid-experiment | Time the challenge to the expression window; measure at challenge, not at protocol design |
| 5 | **Glucocorticoids induce VSIG4** | Patient on steroids reads as artificially high | Record medication at draw; treated/untreated controls |
| 6 | **Cell death inflates IL-1β** | Death-driven false positive that looks like a threshold shift | LDH, GSDMD, viable count; normalise cytokine per viable cell |
| 7 | **cDNA overexpression artefact** | Partially functional variant reads as normal; overexpression is nonspecifically anti-inflammatory | Titratable promoter or FACS-matched surface expression; report matched comparisons only |
| 8 | **Heterozygous clones discarded** | Discards the primary FN1 model | Amend selection criteria; bank hets from every plate |
| 9 | **C-terminal-only FN1 antibody** | NMD and truncation indistinguishable | Paired N- and C-terminal detection, lysate and medium |
| 10 | **SAOS-2 aneuploidy** | FN1 may be present in >2 copies; "biallelic" may require editing 3–4 alleles | Copy-number check before setting clone-screening expectations |
| 11 | **SAOS-2 is transformed** | Not a faithful osteoblast | Screen in SAOS-2; validate in primary or iPSC-derived osteoblasts |
| 12 | **In-frame indels** | A −3 deletion near codon 2183 yields near-full-length functional FN; likewise near codon 124 in VSIG4 | Sanger genotype every clone individually; efficiency heuristics cannot screen these out |
| 13 | **Clonal artefact** | Any single clone's phenotype may be incidental | Pooled populations for screening; ≥3 clones per guide; ≥2 guides; WT rescue; patient-cell agreement |
| 14 | **Guide AV off-target score (26)** | Low predicted specificity | Retained rather than dropped: AV is the only + strand guide in the exon 40 set and carries the highest on-target score (82), so it supplies the opposite-side cut the bracketing design needs. Sequence-verify its top predicted coding off-targets in every AV clone used, and never assign a phenotype from AV clones alone |
| 15 | **Exon 40 guides cut within a 28-nt window** | Less independent than they appear | Describe as off-target controls, not three independent truncation models |
| 16 | **VSIG4 X-linkage** | A clone showing two alleles suggests X duplication | Expect a single clean Sanger trace; karyotype anomalies |
| 17 | **NMD-escaping VSIG4 frameshift upstream of the TM domain** | Would produce a soluble ectodomain — and soluble CRIg is itself a complement inhibitor | Confirm absence of protein, not just presence of indel |
| 18 | **Residual cellular material in decellularised matrix** | Dominates the DAMP readout | DNA/nuclear staining, composition characterisation, ALP inactivation check |
| 19 | **Secretome changes secondary to stress** | Non-specific cytokine increase read as coupling | ER stress markers, viability, total protein normalisation |
| 20 | **Line-to-line differences (THP-1 vs MUTZ-3)** | May dominate a subtle threshold phenotype | Analyse lines separately; require concordance in direction, not magnitude |
| 21 | **Clone pseudo-replication** | Clones from one editing event are not independent biological replicates; apparent *n* overstates real independence | Nested design across independent editing batches, analysed as in §8.1 |
| 22 | **Unblinded image quantification** | Fusion index, F-actin rings, ASC specks and TRAP counts are all judgement-dependent | Blind all image scoring to genotype; pre-declare exclusion rules before unblinding (§8.4) |
| 23 | **Soluble VSIG4 ectodomain in Q124\* modelling** | A knockout is an adequate model of the patient allele only if no functional protein remains in any compartment | Confirm absence of **both** surface VSIG4 (flow) and soluble/truncated VSIG4 (conditioned-medium and lysate immunoblot) before treating the KO as a null |

---

## 8. Design, replication and analysis

### 8.1 Units of replication

Three clones derived from a single editing experiment are not three independent biological
replicates. They share an editing event, a transfection, a passage history and a day. Treating
them as *n* = 3 overstates independence and inflates apparent significance.

The replication hierarchy is therefore explicit:

| Level | Minimum | Role in the analysis |
|---|---|---|
| Independent editing batch | 2 | **Fixed / blocking factor** |
| Guide per target | 2 | **Fixed factor**, and a planned sensitivity analysis |
| Clone | 3 per guide | **Random effect**, nested within batch × guide |
| Assay day | ≥2 | Separate blocking factor where curves are repeated across days |
| Technical replicate | 3 wells | Averaged, never counted as *n* |

Minimum for a genotype claim: **2 batches × 2 guides × 3 clones = 12 edited lines per gene**,
with matched non-targeting clones drawn from the same batches and carried through the same
passage history.

**Why batch and guide are fixed rather than random.** A variance component estimated from two levels is unstable, and treating a two-level factor as random invites a misleadingly precise variance estimate. Batch and guide therefore enter as fixed/blocking terms, which is what two levels can support; clone remains random because there are enough clones to estimate its variance. Guide additionally enters a planned sensitivity analysis — a phenotype present with one guide and absent with the other is a guide-specific artefact until shown otherwise.

**Analysis.** Nonlinear mixed-effects model on the fitted curves, with genotype, batch and guide as fixed effects and clone nested within batch × guide as a random effect. Report clone-level variance explicitly — if it dominates, the phenotype is clonal rather than genotypic, and that is itself the finding.

> **This is a replication design, not a power calculation.** "Two batches × two guides × three clones" protects against clonal artefact but says nothing about the sample size needed to detect the primary estimand. A formal power calculation is required before the main experiment, based on the omnibus curve-level estimand and on plausible between-clone and between-day variance.

> **Where each variance component comes from.** A pooled population contains no clones, so S1-0 cannot estimate between-clone variance. S1-0 supplies **dynamic range, residual assay variance and between-day variance**. **Between-clone variance requires an initial limited clone set — or prior internal data from comparable lines — and the power calculation is therefore updated before the clone panel is expanded**, not fixed at the outset. This section should be reviewed by a statistician before Stage S1-1 begins.

### 8.2 Curve fitting and interaction terms

Dose–response data are fitted with a four-parameter log-logistic model. The genotype comparison
is a **genotype × dose interaction** across the whole curve, not a *t*-test at a chosen dose.
Kinetic data are fitted with a **genotype × time** interaction, with time to 50% decay from peak
as the summary parameter.

All four curve parameters (§3.2) are reported with confidence intervals regardless of
significance. Selective reporting of whichever parameter reached significance would reintroduce
the multiplicity problem this design exists to control.

### 8.3 Endpoint hierarchy and multiplicity

The primary estimands are fixed in §0.7 — one per arm, each a single test. Secondary endpoints — clearance, osteoclastogenesis,
mineralisation, secretome, chemotaxis — are corrected for multiplicity across the endpoint family
within each arm (Benjamini–Hochberg, family defined per arm and stated in advance). Mechanistic
readouts used to interpret a positive primary result are reported descriptively without inference.

A secondary endpoint reaching significance while the primary does not is reported as
hypothesis-generating, not as a positive result.

### 8.4 Blinding and pre-declared exclusions

- **Blind all image-based quantification to genotype**: fusion index, nuclei per cell, F-actin
  ring integrity, ASC speck counts, TRAP⁺ counts, resorption area.
- **Pre-declare exclusion rules** before any unblinding: minimum viability threshold, failure of
  the positive control in that run, and clones carrying a confirmed coding off-target hit.
- **Log every exclusion with its reason** at the time it is applied.

### 8.5 Rescue as the interpretive anchor

A knockout phenotype cannot be attributed to the target gene without a successful wild-type
rescue. Rescue is performed in **at least two independent knockout backgrounds** derived from
different guides, at matched surface expression (§3.5). A phenotype that appears in knockouts and does not reverse on rescue is treated as **unattributed**, not as disproved. Failed rescue has several ordinary construct-side causes that should be excluded before an off-target or clonal explanation is preferred:

- the construct encodes the wrong isoform for the cell type;
- the protein is expressed but mislocalised;
- expression is above or below the functional range despite surface matching;
- delivery efficiency differs between the knockout backgrounds;
- the tag or vector interferes with function.

Only once these are addressed does a persistent failure to rescue point towards off-target or clonal origin. Until then the attribution is simply open.

---

## 9. Falsification summary

| Hypothesis | Falsified if |
|---|---|
| H1.2 threshold | No genotype interaction on any of EC₅₀, E_max, Hill slope or resolution kinetics, on viable-cell-normalised output, under the §8.1 replication structure |
| H1.3 clearance | Opsonised uptake unaffected by VSIG4 status in complement-active serum |
| H1.4 osteoclast gating | RANKL dose–response unshifted |
| H1.5 allelic series | S170F fully rescues while Q124X does not, with no intermediate phenotype |
| H2 osteoclast FN | No outcome class in the decision tree is reached |
| H2.1 hyperostosis | Mineralisation under cytokine load unchanged or uniformly reduced |
| H2.2 amplifier | No change in CXCL8/IL-6 or chemotaxis once stress and viability controlled |
| H2.3 matrix-DAMP | Difference disappears after serum FN depletion |
| H-A (primary) | VSIG4 confirmed expressed, knockout validated, WT rescue works — and no threshold or clearance phenotype appears |
| H-B (secondary) | No FN1 dosage, secretion, retention or assembly abnormality detectable in any model |
| H-C (exploratory) | Both alleles undergo complete NMD with no detectable protein |
| Central hypothesis | Baseline differences appear without any threshold shift — constitutive activation, not a threshold mechanism |

**Course-change triggers.** Reframe Study 1 if no threshold or clearance phenotype survives WT rescue validation. Reframe Study 2 if FN depletion abolishes the matrix difference, or if both alleles prove to be clean NMD with no measurable functional consequence at 50% dosage.

---

## 10. Anticipated criticisms and prepared responses

| Criticism | Response |
|---|---|
| Single-patient VUS with no segregation | Framed as threshold/modifier alleles, consistent with the oligogenic model applied to FBLIM1 and P2RX7. Dose–response phenotyping, not causation claims |
| VSIG4 barely expressed in these lines, and suppressed by the stimuli applied | Addressed first and explicitly (Aim 0.5); expression window defined and verified at each challenge |
| The VSIG4–osteoclast paper is single and overexpression-only | Acknowledged. Our loss-of-function data are the first test of that claim, not a reliance on it |
| VSIG4→NLRP3 is mouse/primary-macrophage | Acknowledged and labelled as the mechanism under test, not assumed. Non-IL-1β axes carried in parallel |
| No FN1 disorder is caused by truncating variants | Confronted with gnomAD constraint data up front; FN1 positioned as secondary hypothesis and reframed as modifier if constraint is permissive |
| Matrix-DAMP is speculative | Explicitly ranked as the exploratory hypothesis, gated on molecular evidence, and not the starting assumption |
| FBS fibronectin will confound the matrix work | Gelatin-Sepharose depletion with immunoblot validation, pre-specified |
| Increased IL-1β could just be cell death | Full priming/assembly/release/pyroptosis/cytotoxicity panel with viable-cell normalisation, pre-specified |
| Cell-line limitations | Screen in lines; validate in primary monocyte-derived macrophages and primary/iPSC osteoblasts |
| Two mechanistically different genes forced into one loop | Split into two independently publishable and independently falsifiable studies; the unifying frame is a hypothesis, not a premise |
| *C. acnes* causality is contested | Hedged throughout; paired with defined TLR2 agonist and second opsonised particle to separate organism-specific from receptor-general effects |

---

## 11. Staging

| Stage | Content | Gate to proceed |
|---|---|---|
| **0** | Orthogonal variant confirmation; gnomAD; annotation and exon-inclusion checks; structural mapping; VSIG4 patient macrophage flow; per-allele FN1 RNA/protein analysis; VSIG4 expression window; 70 kDa fragment assay development | Section 2.7 go/no-go criteria |
| **S1-0** | **Pooled pilot.** RNP editing in bulk; amplicon editing quantification; surface VSIG4 confirmation; small Pam3CSK4 × ATP/nigericin response matrix | Adequate editing efficiency **and** measurable dynamic range in the stimulus matrix — before any cloning |
| **S1-1** | VSIG4 clone isolation across ≥2 independent editing batches; Sanger genotyping; **limited initial clone set to estimate between-clone variance and update the power calculation** | ≥3 clones per guide, ≥2 guides, ≥2 batches; power recalculated before expansion |
| **S1-2** | Baseline characterisation | No baseline difference (as predicted) |
| **S1-3** | Threshold phenotyping — Pam3CSK4/ATP first, then BCP, then *C. acnes* | ≥2-fold EC₅₀ shift, viable-cell normalised |
| **S1-4** | Clearance arm; allelic series with expression matching; osteoclast arm | WT rescue succeeds |
| **S2-1** | FN1 heterozygous and biallelic clones in SAOS-2 and myeloid lines, individually genotyped and grouped by predicted consequence | Copy number known; hets banked; per-allele genotypes recorded |
| **S2-2** | Matrix assembly, secretion, retention, ER stress characterisation | Measurable FN1 abnormality |
| **S2-3** | Decellularised-matrix priming; secretome; chemotaxis | Serum FN depletion validated |
| **S2-4** | Construct series (domain dissection) | — |
| **C** | Factorial coupling | Reproducible phenotype in one compartment |
| **V** | Primary-cell triangulation | — |

---

## 12. Standing caveats

- The VSIG4→NLRP3/IL-1β brake rests on Huang et al. (2019) and its follow-up Chen et al. (2023) — the same group — plus convergent but mechanistically distinct work (Li et al., 2017). It is predominantly mouse and primary macrophage. Generalisation to human monocytic lines is assumed for design purposes and tested, not established.
- The VSIG4–osteoclast/Keap1–Nrf2 link rests on a single 2024 overexpression-only study.
- The matrix-DAMP mechanism is supported at the level of general principle (ECM remodelling yielding immune-active DAMPs) but not for these specific variants.
- IL-1β is a primary endpoint, not the only mechanistic endpoint. TNF, IL-6, CXCL8 and transcriptional signals remain in the panel throughout.
- In vitro NLRP3/crystal dominance may overstate the in vivo role of IL-1β: in the *Ank*⁻/⁻ calcification model, NLRP3 deficiency conferred only ~30% protection (Jin et al., 2011).
- MUTZ-3-derived cells carry documented transcriptional and functional defects relative to primary myeloid cells (Rasaiyaah et al., 2009), which is why the key IL-1β result is replicated in primary monocyte-derived macrophages.
- All four variants are private and n = 1. Every conclusion is framed as a threshold/modifier contribution consistent with the oligogenic model of SAPHO, not as Mendelian causation.

---

## 13. Reference library

The project library holds **55 curated references**, 35 with free PubMed Central full text and 20 requiring institutional access. Each entry notes what it is load-bearing for, with section references (§) pointing into this document.

**Every work cited in this document is held in the library.** There is no outstanding acquisition list.

### 13.1 SAPHO / CNO / CRMO disease biology

1. Hedrich CM, Morbach H, Reiser C, Girschick HJ. New Insights into Adult and Paediatric Chronic Non-bacterial Osteomyelitis CNO. *Curr Rheumatol Rep*. 2020;22(9):52. PMID 32705386 · PMC7378119 · doi:10.1007/s11926-020-00928-1.
   — Adult + paediatric CNO — myeloid cytokine dysregulation; also the hedge on C. acnes causality (§0.1, §0.3)

2. Liu S, Tang M, Cao Y, Li C. Synovitis, acne, pustulosis, hyperostosis, and osteitis syndrome: review and update. *Ther Adv Musculoskelet Dis*. 2020;12:1759720X20912865. PMID 32523634 · PMC7236399 · doi:10.1177/1759720X20912865.
   — SAPHO clinical review — clinical context for the disease frame (§0.1)

3. Zhao DY, McCann L, Hahn G, Hedrich CM. Chronic nonbacterial osteomyelitis (CNO) and chronic recurrent multifocal osteomyelitis (CRMO). *J Transl Autoimmun*. 2021;4:100095. PMID 33870159 · PMC8040271 · doi:10.1016/j.jtauto.2021.100095.
   — CNO/CRMO review — disease spectrum, osteolysis + hyperostosis coexistence (§0.1)

4. Sergi CM, Miller E, Demellawy DE, Shen F, Zhang M. Chronic recurrent multifocal osteomyelitis. A narrative and pictorial review. *Front Immunol*. 2022;13:959575. PMID 36072576 · PMC9441751 · doi:10.3389/fimmu.2022.959575.
   — CRMO narrative + pictorial review — imaging/lesion phenotype, useful for framing hyperostosis (§4.3)

5. Hetrick R, Oliver M. Pediatric autoinflammatory bone disorders-a mini review with special focus on pathogenesis and inborn errors of immunity. *Front Pediatr*. 2023;11:1169659. PMID 37342528 · PMC10277822 · doi:10.3389/fped.2023.1169659.
   — Autoinflammatory bone disorders — links cytokine imbalance/inflammasome to osteoclastogenesis (§0.1, §3.4)

6. Charras A, Hofmann SR, Cox A, Schulze F, Russ S, Northey S, et al.. P2RX7 gene variants associate with altered inflammasome assembly and reduced pyroptosis in chronic nonbacterial osteomyelitis (CNO). *J Autoimmun*. 2024;144:103183. PMID 38401466 · doi:10.1016/j.jaut.2024.103183. *[subscription]*
   — **Priority.** P2RX7 variants alter inflammasome assembly and reduce pyroptosis in CNO — the methodological template for the entire threshold design (§3.2)

7. Furer V, Kishimoto M, Tomita T, Elkayam O, Helliwell PS. Current and future advances in practice: SAPHO syndrome and chronic non-bacterial osteitis (CNO). *Rheumatol Adv Pract*. 2024;8(4):rkae114. PMID 39411288 · PMC11474108 · doi:10.1093/rap/rkae114.
   — Current practice review, SAPHO + CNO — primary citation for the multifactorial/threshold frame (§0.1, §0.3 assumed)

8. Roberts E, Charras A, Hahn G, Hedrich CM. An improved understanding of pediatric chronic nonbacterial osteomyelitis pathophysiology informs current and future treatment. *J Bone Miner Res*. 2024;39(11):1523-1538. PMID 39209330 · PMC11523093 · doi:10.1093/jbmr/zjae141.
   — Paediatric CNO pathophysiology → treatment; companion to the P2RX7 threshold precedent (§0.3, §3.2)

9. Wang Y(#), Gu M(#), Zheng Z(#), Jiang H(#), Han L, Huang H, et al.. Therapeutic approaches for SAPHO syndrome from the perspective of pathogenesis: a review of the literature. *Front Immunol*. 2025;16:1560398. PMID 40303415 · PMC12037609 · doi:10.3389/fimmu.2025.1560398.
   — Therapeutic approaches from pathogenesis — supports treating C. acnes as trigger/modifier, not sufficient cause (§0.3, §3.3)


### 13.2 VSIG4 / CRIg biology

10. Helmy KY, Katschke KJ Jr, Gorgani NN, Kljavin NM, Elliott JM, Diehl L, et al.. CRIg: a macrophage complement receptor required for phagocytosis of circulating pathogens. *Cell*. 2006;124(5):915-27. PMID 16530040 · doi:10.1016/j.cell.2005.12.039. *[subscription]*
   — DISCOVERY. CRIg as macrophage complement receptor required for phagocytosis of C3-opsonised pathogens — foundation of the clearance arm (§3.3)

11. Wiesmann C, Katschke KJ, Yin J, Helmy KY, Steffek M, Fairbrother WJ, et al.. Structure of C3b in complex with CRIg gives insights into regulation of complement activation. *Nature*. 2006;444(7116):217-20. PMID 17051150 · doi:10.1038/nature05263. *[subscription]*
   — STRUCTURE. C3b–CRIg co-crystal — map p.Ser170Phe onto this to test the binding-interface hypothesis (§2.2)

12. Gorgani NN, He JQ, Katschke KJ Jr, Helmy KY, Xi H, Steffek M, et al.. Complement receptor of the Ig superfamily enhances complement-mediated phagocytosis in a subpopulation of tissue resident macrophages. *J Immunol*. 2008;181(11):7902-8. PMID 19017980 · doi:10.4049/jimmunol.181.11.7902. *[subscription]*
   — CRIg enhances complement-mediated phagocytosis — primary functional data underpinning the clearance arm (§3.3)

13. Gorgani NN, Thathaisong U, Mukaro VR, Poungpair O, Tirimacco A, Hii CS, et al.. Regulation of CRIg expression and phagocytosis in human macrophages by arachidonate, dexamethasone, and cytokines. *Am J Pathol*. 2011;179(3):1310-8. PMID 21741936 · PMC3157186 · doi:10.1016/j.ajpath.2011.05.021.
   — CRIg regulation by arachidonate, dexamethasone and cytokines — expression window (§2.5) and the glucocorticoid confounder (#5)

14. Ma Y, Usuwanthim K, Munawara U, Quach A, Gorgani NN, Abbott CA, et al.. Protein kinase cα regulates the expression of complement receptor Ig in human monocyte-derived macrophages. *J Immunol*. 2015;194(6):2855-61. PMID 25687755 · doi:10.4049/jimmunol.1303477. *[subscription]*
   — PKCα regulates CRIg expression — third independent handle on making VSIG4 detectable before knockout (§2.5)

15. Dustin ML. Complement Receptors in Myeloid Cell Adhesion and Phagocytosis. *Microbiol Spectr*. 2016;4(6):10.1128. PMID 27809953 · PMC5580235 · doi:10.1128/microbiolspec.MCHD-0034-2016.
   — Complement receptors in myeloid adhesion and phagocytosis — background for assay design (§3.3)

16. Hajishengallis G, Reis ES, Mastellos DC, Ricklin D, Lambris JD. Novel mechanisms and functions of complement. *Nat Immunol*. 2017;18(12):1288-1298. PMID 29144501 · PMC5706779 · doi:10.1038/ni.3858.
   — Novel mechanisms and functions of complement — general background (§0.3 assumed)

17. Li J, Diao B, Guo S, Huang X, Yang C, Feng Z, et al.. VSIG4 inhibits proinflammatory macrophage activation by reprogramming mitochondrial pyruvate metabolism. *Nat Commun*. 2017;8(1):1322. PMID 29109438 · PMC5673889 · doi:10.1038/s41467-017-01327-4.
   — VSIG4 inhibits proinflammatory macrophage activation via metabolic reprogramming — mechanistic basis for the 'brake'; also the reason overexpression is nonspecifically anti-inflammatory (§0.3, §3.5)

18. Munawara U, Small AG, Quach A, Gorgani NN, Abbott CA, Ferrante A. Cytokines regulate complement receptor immunoglobulin expression and phagocytosis of Candida albicans in human macrophages: A control point in anti-microbial immunity. *Sci Rep*. 2017;7(1):4050. PMID 28642550 · PMC5481325 · doi:10.1038/s41598-017-04325-0.
   — Cytokines regulate CRIg expression and phagocytosis — direct evidence for the expression-window prerequisite (§2.5)

19. Huang X, Feng Z, Jiang Y, Li J, Xiang Q, Guo S, et al.. VSIG4 mediates transcriptional inhibition of Nlrp3 and Il-1β in macrophages. *Sci Adv*. 2019;5(1):eaau7426. PMID 30662948 · PMC6326752 · doi:10.1126/sciadv.aau7426.
   — **Priority.** VSIG4 mediates transcriptional inhibition of Nlrp3 and Il-1β — the primary prior for the candidate mechanism named in §0.3

20. Munawara U, Perveen K, Small AG, Putty T, Quach A, Gorgani NN, et al.. Human Dendritic Cells Express the Complement Receptor Immunoglobulin Which Regulates T Cell Responses. *Front Immunol*. 2019;10:2892. PMID 31921153 · PMC6914870 · doi:10.3389/fimmu.2019.02892.
   — CRIg on human dendritic cells — relevant given MUTZ-3's DC lineage (§2.5, confounder #20)

21. Reis ES, Mastellos DC, Hajishengallis G, Lambris JD. New insights into the immune functions of complement. *Nat Rev Immunol*. 2019;19(8):503-516. PMID 31048789 · PMC6667284 · doi:10.1038/s41577-019-0168-x.
   — Immune functions of complement — general background (§0.3 assumed)

22. Reißing J, Lutz P, Frissen M, Ibidapo-Obe O, Reuken PA, Wirtz TH, et al.. Immunomodulatory receptor VSIG4 is released during spontaneous bacterial peritonitis and predicts short-term mortality. *JHEP Rep*. 2021;4(1):100391. PMID 34917912 · PMC8666561 · doi:10.1016/j.jhepr.2021.100391.
   — VSIG4 is released/shed during infection — activation-induced loss of surface receptor; why surface VSIG4 must be measured at challenge (§2.5, confounder 4)

23. Chen Y, Li S, Huang X, Wang C, Pan Y, Xiang Q, et al.. Tetraspan MS4A6D is a coreceptor of MHC class II antigen (MHC-II) that promotes macrophages-derived inflammation. *Mol Immunol*. 2023;160:121-132. PMID 37429063 · doi:10.1016/j.molimm.2023.07.003. *[subscription]*
   — MS4A6D as coreceptor — MS4A6D is the partner in the VSIG4–MS4A6D–JAK2–STAT3–A20 axis; direct mechanistic support for §0.3

24. Ebstein SY, Rafique A, Zhou Y, Krasco A, Montalvo-Ortiz W, Yu L, et al.. VSIG4 interaction with heparan sulfates inhibits VSIG4-complement binding. *Glycobiology*. 2023;33(7):591-604. PMID 37341346 · PMC10426322 · doi:10.1093/glycob/cwad050.
   — Heparan sulfate competes with C3b for VSIG4 binding — S170F could be an HS-binding defect; mandates the HS/heparin competition arm (§2.2, §3.3)

25. Perveen K, Yang G, Skurray CD, Ngo A, Black N, Putty T, et al.. Dynamic expression of complement receptor immunoglobulin (CRIg) on monocytes and its role in phagocytosis and killing of Staphylococcus aureus. *J Biomed Sci*. 2026;33(1):29. PMID 41826968 · PMC12983484 · doi:10.1186/s12929-025-01212-z.
   — CRIg on monocytes, dynamic expression + Gram-positive handling — closest methodological precedent for the clearance assay design (§3.3)


### 13.3 Extracellular matrix and fibronectin biology

26. Engvall E, Ruoslahti E. Binding of soluble form of fibroblast surface protein, fibronectin, to collagen. *Int J Cancer*. 1977;20(1):1-5. PMID 903179 · doi:10.1002/ijc.2910200102. *[subscription]*
   — Binding of soluble fibronectin to collagen — original gelatin-affinity principle behind the FN-depletion step (§7 #1)

27. Engvall E, Ruoslahti E, Miller EJ. Affinity of fibronectin to collagens of different genetic types and to fibrinogen. *J Exp Med*. 1978;147(6):1584-95. PMID 567240 · PMC2184308 · doi:10.1084/jem.147.6.1584.
   — Affinity of fibronectin to collagens of different genetic types — establishes selectivity of the gelatin-Sepharose method

28. Ruoslahti E, Hayman EG, Engvall E, Cothran WC, Butler WT. Alignment of biologically active domains in the fibronectin molecule. *J Biol Chem*. 1981;256(14):7277-81. PMID 6788765. *[subscription]*
   — Alignment of biologically active domains in fibronectin — domain architecture for mapping the two truncations (§2.4)

29. Pankov R, Yamada KM. Fibronectin at a glance. *J Cell Sci*. 2002;115(Pt 20):3861-3. PMID 12244123 · doi:10.1242/jcs.00059. *[subscription]*
   — Fibronectin at a glance — compact domain-architecture reference for mapping the two truncations (§2.4)

30. Hynes RO. The extracellular matrix: not just pretty fibrils. *Science*. 2009;326(5957):1216-9. PMID 19965464 · PMC3536535 · doi:10.1126/science.1176009.
   — 'Not just pretty fibrils' — the canonical argument that ECM is an active regulator; sets up the whole Study 2 premise

31. Sabatier L, Chen D, Fagotto-Kaufmann C, Hubmacher D, McKee MD, Annis DS, et al.. Fibrillin assembly requires fibronectin. *Mol Biol Cell*. 2009;20(3):846-58. PMID 19037100 · PMC2633374 · doi:10.1091/mbc.e08-08-0830.
   — Fibrillin assembly requires fibronectin — the immunoblot-validated gelatin-Sepharose depletion protocol for confounder #1

32. Singh P, Carraher C, Schwarzbauer JE. Assembly of fibronectin extracellular matrix. *Annu Rev Cell Dev Biol*. 2010;26:397-419. PMID 20690820 · PMC3628685 · doi:10.1146/annurev-cellbio-100109-104020.
   — Assembly of the FN extracellular matrix — mechanistic basis for the DOC-insoluble assay and the assembly-inhibitor logic (§2.4, §4.6)

33. Schwarzbauer JE, DeSimone DW. Fibronectins, their fibrillogenesis, and in vivo functions. *Cold Spring Harb Perspect Biol*. 2011;3(7):a005041. PMID 21576254 · PMC3119908 · doi:10.1101/cshperspect.a005041.
   — Fibrillogenesis and in vivo function — core citation for why loss of the C-terminal cysteines abolishes assembly (§2.4)

34. Efthymiou G, Saint A, Ruff M, Rekad Z, Ciais D, Van Obberghen-Schilling E. Shaping Up the Tumor Microenvironment With Cellular Fibronectin. *Front Oncol*. 2020;10:641. PMID 32426283 · PMC7203475 · doi:10.3389/fonc.2020.00641.
   — Cellular fibronectin (EDA/EDB) in the microenvironment — cellular vs plasma FN distinction (§2.4, §4.5)

35. Lamandé SR, Bateman JF. Genetic Disorders of the Extracellular Matrix. *Anat Rec (Hoboken)*. 2020;303(6):1527-1542. PMID 30768852 · PMC7318566 · doi:10.1002/ar.24086.
   — Genetic disorders of the ECM — quantitative deficiency vs dominant-negative vs ER retention; the source of Branch C (§6)

36. McQuitty CE, Williams R, Chokshi S, Urbani L. Immunomodulatory Role of the Extracellular Matrix Within the Liver Disease Microenvironment. *Front Immunol*. 2020;11:574276. PMID 33262757 · PMC7686550 · doi:10.3389/fimmu.2020.574276.
   — ECM as immunomodulator in liver disease — precedent for matrix-driven innate priming (§2.6, §4.5)

37. Karamanos NK, Theocharis AD, Piperigkou Z, Manou D, Passi A, Skandalis SS, et al.. A guide to the composition and functions of the extracellular matrix. *FEBS J*. 2021;288(24):6850-6912. PMID 33605520 · doi:10.1111/febs.15776. *[subscription]*
   — Comprehensive ECM composition/function guide — reference text for the matrisome framing (§0.3 assumed)

38. Lambert C, Zappia J, Sanchez C, Florin A, Dubuc JE, Henrotin Y. The Damage-Associated Molecular Patterns (DAMPs) as Potential Targets to Treat Osteoarthritis: Perspectives From a Review of the Literature. *Front Med (Lausanne)*. 2021;7:607186. PMID 33537330 · PMC7847938 · doi:10.3389/fmed.2020.607186.
   — DAMPs as therapeutic targets — general DAMP framing for the exploratory hypothesis (§0.4 H-C)

39. Quan T. The Matrisome as an Immunomodulator: A Role Far Beyond Its Structural Support. *Biomolecules*. 2026;16(3):408. PMID 41897344 · PMC13023643 · doi:10.3390/biom16030408.
   — The matrisome as an immunomodulator — most current statement of the matrix-as-immune-signal concept (§0.3, §4.5)


### 13.4 Human *FN1* disease genetics

40. Lee CS, Fu H, Baratang N, Rousseau J, Kumra H, Sutton VR, et al.. Mutations in Fibronectin Cause a Subtype of Spondylometaphyseal Dysplasia with "Corner Fractures". *Am J Hum Genet*. 2017;101(5):815-823. PMID 29100092 · PMC5673654 · doi:10.1016/j.ajhg.2017.09.019.
   — SMDCF — N-terminal missense, secretion defect/ER retention. THE citation for 'no FN1 disorder is caused by truncating variants' (§2.1, §6 Branch C)

41. Costantini A, Valta H, Baratang NV, Yap P, Bertola DR, Yamamoto GL, et al.. Novel fibronectin mutations and expansion of the phenotype in spondylometaphyseal dysplasia with "corner fractures". *Bone*. 2019;121:163-171. PMID 30599297 · doi:10.1016/j.bone.2018.12.020. *[subscription]*
   — Novel FN1 mutations, expanded SMDCF phenotype — corroborates the missense/secretion mechanism (§2.1)

42. Qiu J, Chi H, Gan C, Zhou X, Chen D, Yang Q, et al.. A high-impact FN1 variant correlates with fibronectin-mediated glomerulopathy via decreased binding to collagen type IV. *Pathology*. 2023;55(4):498-507. PMID 36774238 · doi:10.1016/j.pathol.2022.10.016. *[subscription]*
   — High-impact FN1 variant in fibronectin glomerulopathy — second disease, second missense mechanism (§2.1)

43. Sun L, Kuang X, Wu Y, Huang W. A Novel FN1 Nucleotide Variant c.3051G>C (p.Trp1017Cys) in a Pediatric Patient with Fibronectin Glomerulopathy: Case Report and Literature Review. *J Clin Med*. 2026;15(13):5016. PMID 42452483 · PMC13361931 · doi:10.3390/jcm15135016.
   — Novel FN1 c.3051G>C paediatric fibronectin glomerulopathy — most recent variant-level precedent (§2.1)


### 13.5 Fibronectin, VSIG4 and bone cells

44. Moursi AM, Damsky CH, Lull J, Zimmerman D, Doty SB, Aota S, et al.. Fibronectin regulates calvarial osteoblast differentiation. *J Cell Sci*. 1996;. PMID 8799825 · doi:10.1242/jcs.109.6.1369. *[subscription]*
   — FN regulates calvarial osteoblast differentiation — osteoblast-side counterpart to Gramoun; underpins the SAOS-2 cell-autonomous arm (§4.3)

45. Gramoun A, Azizi N, Sodek J, Heersche JN, Nakchbandi I, Manolson MF. Fibronectin inhibits osteoclastogenesis while enhancing osteoclast activity via nitric oxide and interleukin-1β-mediated signaling pathways. *J Cell Biochem*. 2010;111(4):1020-34. PMID 20672308 · doi:10.1002/jcb.22791. *[subscription]*
   — FN inhibits osteoclastogenesis while ENHANCING osteoclast activity — the paper that forced H2 from a single prediction into a decision tree (§4.2)

46. Miao J, Tu Y, Jiang J, Ren R, Wu Q, Liang H, et al.. VSIG4 inhibits RANKL-induced osteoclastogenesis by enhancing Nrf2-dependent antioxidant response against reactive oxygen species production. *Int J Biol Macromol*. 2024;260(Pt 2):129357. PMID 38216011 · doi:10.1016/j.ijbiomac.2024.129357. *[subscription]*
   — **Priority.** VSIG4 inhibits RANKL-induced osteoclastogenesis via Keap1–Nrf2 — sole prior for §3.4. Single study, overexpression-only


### 13.6 Inflammasome activation and microbial stimuli

47. Jin C, Frayssinet P, Pelker R, Cwirka D, Hu B, Vignery A, et al.. NLRP3 inflammasome plays a critical role in the pathogenesis of hydroxyapatite-associated arthropathy. *Proc Natl Acad Sci U S A*. 2011;108(36):14867-72. PMID 21856950 · PMC3169126 · doi:10.1073/pnas.1111101108.
   — NLRP3 in hydroxyapatite-associated arthropathy — companion to Pazár; source of the ~30% protection figure in §12

48. Pazár B, Ea HK, Narayan S, Kolly L, Bagnoud N, Chobaz V, et al.. Basic calcium phosphate crystals induce monocyte/macrophage IL-1β secretion through the NLRP3 inflammasome in vitro. *J Immunol*. 2011;186(4):2495-502. PMID 21239716 · doi:10.4049/jimmunol.1001284. *[subscription]*
   — BCP crystals induce IL-1β via NLRP3 in THP-1 — the bone-relevant activator for stage B of §3.2

49. Qin M, Pirouz A, Kim MH, Krutzik SR, Garbán HJ, Kim J. Propionibacterium acnes Induces IL-1β secretion via the NLRP3 inflammasome in human monocytes. *J Invest Dermatol*. 2014;134(2):381-388. PMID 23884315 · PMC4116307 · doi:10.1038/jid.2013.309.
   — P. acnes induces IL-1β via NLRP3 in human monocytes — MOI, timepoints and readouts for stage C of §3.2

50. Zimmermann P, Curtis N. The role of Cutibacterium acnes in auto-inflammatory bone disorders. *Eur J Pediatr*. 2019;178(1):89-95. PMID 30324232 · doi:10.1007/s00431-018-3263-2. *[subscription]*
   — C. acnes in auto-inflammatory bone disorders — biopsy-positivity figure and the contamination caveat (§0.3, §10)


### 13.7 Methods and model systems

51. Masterson AJ, Sombroek CC, De Gruijl TD, Graus YM, van der Vliet HJ, Lougheed SM, et al.. MUTZ-3, a human cell line model for the cytokine-induced differentiation of dendritic cells from CD34+ precursors. *Blood*. 2002;100(2):701-3. PMID 12091369 · doi:10.1182/blood.v100.2.701. *[subscription]*
   — MUTZ-3 as a CD34+ DC differentiation model — original cell-line characterisation

52. Santegoets SJ, Masterson AJ, van der Sluis PC, Lougheed SM, Fluitsma DM, van den Eertwegh AJ, et al.. A CD34(+) human cell line model of myeloid dendritic cell differentiation: evidence for a CD14(+)CD11b(+) Langerhans cell precursor. *J Leukoc Biol*. 2006;80(6):1337-44. PMID 16959899 · doi:10.1189/jlb.0206111. *[subscription]*
   — CD34+ human cell line model of myeloid DC differentiation — supporting MUTZ-3 characterisation

53. Ciraci E, Barisani D, Parafioriti A, Formisano G, Arancia G, Bottazzo G, et al.. CD34 human hematopoietic progenitor cell line, MUTZ-3, differentiates into functional osteoclasts. *Exp Hematol*. 2007;35(6):967-77. PMID 17533051 · doi:10.1016/j.exphem.2007.03.003. *[subscription]*
   — MUTZ-3 differentiates into functional osteoclasts — primary source for the osteoclast model system

54. Rasaiyaah J, Noursadeghi M, Kellam P, Chain B. Transcriptional and functional defects of dendritic cells derived from the MUTZ-3 leukaemia line. *Immunology*. 2009;127(3):429-41. PMID 19538250 · PMC2712111 · doi:10.1111/j.1365-2567.2008.03018.x.
   — Transcriptional and functional defects of MUTZ-3-derived DCs — documents divergence from primary myeloid cells (§12, confounder #20)

55. Weng W, Zanetti F(#), Bovard D(#), Braun B(#), Ehnert S, Uynuk-Ool T, et al.. A simple method for decellularizing a cell-derived matrix for bone cell cultivation and differentiation. *J Mater Sci Mater Med*. 2021;32(9):124. PMID 34524552 · PMC8443471 · doi:10.1007/s10856-021-06601-y.
   — **Priority.** Simple decellularisation of cell-derived matrix — the method §4.5 specifies but could not previously cite
