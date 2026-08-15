# Protocol amendment v9: updated All of Us controls and IL1RN–IL36RN Firth association analysis

**Status:** Final primary association analysis completed.  
**Amendment date:** 7 August 2026  
**Supersedes for association testing:** Section 28 (“Next planned analysis”) of `All_of_Us_pustular_psoriasis_case_control_protocol_v8.md`  
**Preserves:** All cohort-construction, Hail-configuration, targeted-extraction, genotype-QC, and data-integration procedures documented in protocol v8  
**Primary statistical method:** Firth penalized logistic regression using R package `logistf`  
**Multiple-testing method:** Benjamini–Hochberg correction across four prespecified models

## 1. Purpose and scope of this amendment

Protocol v8 documented construction of a new, genotype-independent All of Us disease cohort, construction of a nonoverlapping control cohort, and extraction of nine IL1RN/IL36RN variants from the All of Us v8 genomic callsets. At the time v8 was written, the definitive combined-cohort association analysis had not yet been performed.

This v9 amendment records:

1. the distinction between the exploratory nine-variant All of Us analysis and the primary manuscript association analysis;
2. replacement of the earlier, smaller All of Us control subset with the updated 19,487-person control cohort;
3. construction and validation of the updated combined PLINK cohort;
4. the four prespecified Firth logistic-regression models;
5. Benjamini–Hochberg adjustment across those four tests;
6. the final effect estimates, confidence intervals, and p-values;
7. the public repository outputs and controlled-data restrictions.

All procedures in protocol v8 remain valid unless explicitly amended below.

## 2. Separation of the two All of Us analyses

### 2.1 Exploratory nine-variant All of Us analysis

The genotype-independent disease cohort constructed in the Verily Researcher Workbench contained 138 participants before exclusion of three ACH-only participants. The final exploratory disease cohort contained 135 participants:

| Mutually exclusive group | Participants |
|---|---:|
| GPP only | 35 |
| GPP and PPP | 9 |
| PPP only | 91 |
| **Total** | **135** |

The corresponding updated All of Us control cohort contained 19,487 participants. Therefore, the exploratory nine-variant All of Us dataset contained 19,622 participants in total.

This dataset was used to determine genotype frequencies for nine queried IL1RN/IL36RN variants and to identify the phenotype subgroup of each carrier. It was not substituted for the historical manuscript case series.

### 2.2 Primary combined-cohort association analysis

To preserve comparability with the earlier analysis and the manuscript cohort definition, the original case series was retained unchanged. It comprised:

| Case source | Phenotype | Participants |
|---|---|---:|
| Multicentric German cohort | GPP | 82 |
| Multicentric German cohort | PPP | 428 |
| Earlier All of Us case series | GPP | 43 |
| Earlier All of Us case series | PPP | 101 |
| **Total PP cases** | **GPP and PPP combined as PP** | **654** |

The newer 135-person exploratory All of Us disease cohort must not be added to these 654 cases because it derives from the same underlying All of Us resource and would introduce duplication. The 135-person dataset is retained for descriptive and sensitivity analyses only.

## 3. Replacement of the earlier All of Us controls

The previous combined association dataset contained 9,849 controls, of whom 3,449 were from the earlier All of Us control analysis. The earlier 3,449 All of Us controls were removed before adding the updated All of Us controls.

The retained historical/non-All-of-Us controls were therefore:

\[
9,849 - 3,449 = 6,400.
\]

The updated control set was:

| Control source | Participants |
|---|---:|
| Retained historical/non-All-of-Us controls | 6,400 |
| Updated All of Us controls | 19,487 |
| **Total controls** | **25,887** |

The final combined analysis cohort contained:

| Phenotype | Participants |
|---|---:|
| PP cases | 654 |
| Controls | 25,887 |
| **Total** | **26,541** |

This replacement strategy prevents duplication of All of Us controls while retaining the non-All-of-Us participants from the earlier analysis.

## 4. Variants used in the primary association analysis

The primary combined-cohort analysis was restricted to the two variants evaluated in the earlier association analysis:

| Gene | Transcript-level variant | Protein consequence | GRCh38 variant used for updated All of Us genotypes |
|---|---|---|---|
| IL1RN | c.*75C>G | 3′-UTR | `chr2:113132946:C:G` |
| IL36RN | c.227C>T | p.Pro76Leu (P76L) | `chr2:113062235:C:T` |

The historical PLINK MAP/PED representation retained its original marker names and coordinate convention for compatibility with the earlier analysis. The GRCh38 identifiers above identify the variants extracted from the updated All of Us callsets.

## 5. Updated PLINK cohort construction

The final merged PLINK files were named:

- `PP_cohort_updated_AoU_v8.ped`
- `PP_cohort_updated_AoU_v8.map`
- `PP_cohort_updated_AoU_v8_manifest.tsv`

The PED file contained 26,541 participants, one row per participant, with unique synthetic identifiers used where necessary to avoid exposing controlled All of Us participant identifiers.

PLINK phenotype coding was:

- `1` = control;
- `2` = PP case.

The final PED validation showed:

- 26,541 rows;
- 654 cases;
- 25,887 controls;
- two variants;
- no duplicated participant identifiers;
- the expected ten PED fields per row for two biallelic markers;
- no individual-level All of Us identifiers in public outputs.

### 5.1 Genotype validation counts

The combined genotype distribution used for analysis was:

| Phenotype | IL1RN/P76L genotype category | Participants |
|---|---|---:|
| Cases | reference/reference at both variants | 650 |
| Cases | heterozygous at both variants | 2 |
| Cases | homozygous alternate at both variants | 2 |
| Controls | reference/reference at both variants, complete calls | 25,863 |
| Controls | heterozygous at both variants | 7 |
| Controls | IL1RN alternate only | 6 |
| Controls | P76L alternate only | 4 |
| Controls | IL1RN missing, P76L reference | 1 |
| Controls | P76L missing, IL1RN reference | 6 |

The category counts sum to 654 cases and 25,887 controls. The updated All of Us controls were not perfectly concordant across the two variants; consequently, the updated analysis evaluates joint genotype/co-carriage rather than assuming a universally phased haplotype.

## 6. PLINK additive-dosage export

The validated PED/MAP files were converted and the two markers were exported using PLINK additive coding:

```bash
plink \
  --file PP_cohort_updated_AoU_v8 \
  --make-bed \
  --out PP_cohort_updated_AoU_v8_check \
  --allow-no-sex

plink \
  --bfile PP_cohort_updated_AoU_v8_check \
  --snps IL1RN_c.75CG,IL36RN_c.C227T \
  --recode A \
  --out two_vars_updated_AoU_v8 \
  --allow-no-sex
```

The resulting controlled-access input to R was:

`two_vars_updated_AoU_v8.raw`

PLINK additive dosage was interpreted as:

- `0` = no alternate allele;
- `1` = one alternate allele;
- `2` = two alternate alleles;
- missing = genotype unavailable.

## 7. Statistical analysis environment

The primary analysis was performed in R using the `logistf` package. Firth penalized logistic regression was selected before examining the final model output because the variants were rare and the case-control tables contained small cells. Standard maximum-likelihood logistic regression can produce biased or unstable estimates under these conditions.

The models used profile-likelihood confidence intervals:

```r
logistf(
  case_status ~ predictor,
  data = dat,
  pl = TRUE
)
```

The public analysis script is:

`analyses/01_genetic_association/models_updated_AoU_v8.R`

The participant-level PLINK input is controlled access and is not included in the public repository.

## 8. Phenotype and dosage variables

PLINK phenotype values were converted to a binary model outcome:

```r
dat$case_status <- ifelse(
  dat$PHENOTYPE == 2,
  1,
  ifelse(dat$PHENOTYPE == 1, 0, NA)
)
```

**Purpose of this block:** It converts PLINK’s `2 = case` and `1 = control` coding into the `1 = case` and `0 = control` coding used by the regression models. Any other phenotype value is retained as missing.

The two additive-dosage variables were assigned as:

```r
dat$IL1RN_dosage <- as.numeric(dat[[il1rn_column]])
dat$P76L_dosage  <- as.numeric(dat[[p76l_column]])
```

**Purpose of this block:** It retrieves the PLINK additive-dosage columns and explicitly converts them to numeric variables.

## 9. Definition of joint genotype variables

```r
dat$joint_dosage <- pmin(
  dat$IL1RN_dosage,
  dat$P76L_dosage
)

dat$joint_carrier <- as.integer(
  dat$joint_dosage > 0
)
```

**Purpose of this block:**

- `joint_dosage` is the minimum alternate-allele dosage across the two loci.
- A participant must carry an alternate allele at both variants to have `joint_dosage > 0`.
- A value of 1 represents at least one alternate allele jointly present at both loci.
- A value of 2 requires two alternate alleles at each locus.
- `joint_carrier` collapses joint dosage into a binary carrier/noncarrier predictor.
- Because `pmin()` was used without `na.rm = TRUE`, a missing genotype at either locus yields missing joint dosage, preventing a missing call from being treated as reference.

These variables quantify joint genotype/co-carriage. They do not by themselves establish that the alleles are in cis. The term “haplotype” should be reserved for participants with demonstrated phase or used only when referring to the earlier perfectly concordant dataset with appropriate qualification.

## 10. Prespecified Firth models

Four models formed one prespecified multiple-testing family:

1. **Joint carrier model**  
   `case_status ~ joint_carrier`
2. **Joint additive-dosage model**  
   `case_status ~ joint_dosage`
3. **IL1RN additive-dosage model**  
   `case_status ~ IL1RN_dosage`
4. **IL36RN P76L additive-dosage model**  
   `case_status ~ P76L_dosage`

The joint carrier model was the primary model. The joint additive and individual-variant models were secondary prespecified analyses.

Fisher’s exact testing was not used as the primary inferential method. Descriptive cross-tabulations may be reported, but the manuscript association estimates derive from Firth logistic regression.

## 11. Missing-data handling

Missing genotypes were retained as missing during PED construction, PLINK conversion, and R import. They were never recoded as homozygous reference.

For each model, R used observations with complete values for the outcome and the relevant predictor. Consequently:

- joint models exclude a participant when either IL1RN or P76L dosage is missing;
- the IL1RN model excludes only observations missing IL1RN dosage;
- the P76L model excludes only observations missing P76L dosage.

No genotype imputation was performed.

## 12. Multiple-testing correction

The four raw model p-values were corrected together using the Benjamini–Hochberg procedure:

```r
results$p_BH <- p.adjust(
  results$p_value,
  method = "BH"
)
```

**Purpose of this block:** It controls the false-discovery rate across the four prespecified association tests and appends the adjusted values to the result table. Correction was performed only after all four model results had been assembled.

## 13. Final association results

| Model | Predictor | Beta | Odds ratio | 95% profile-likelihood CI | Raw p-value | BH-adjusted p-value |
|---|---|---:|---:|---:|---:|---:|
| Joint carrier | `joint_carrier` | 3.1724 | 23.8649 | 6.7431–75.1251 | 2.4031 × 10⁻⁵ | 2.4031 × 10⁻⁵ |
| Joint additive dosage | `joint_dosage` | 2.7178 | 15.1473 | 5.0546–51.5211 | 3.3476 × 10⁻⁶ | 1.3390 × 10⁻⁵ |
| IL1RN additive dosage | `IL1RN_dosage` | 2.3340 | 10.3189 | 3.9787–27.4877 | 1.5367 × 10⁻⁵ | 2.0490 × 10⁻⁵ |
| IL36RN P76L additive dosage | `P76L_dosage` | 2.4350 | 11.4154 | 4.2648–32.2567 | 9.7600 × 10⁻⁶ | 1.9520 × 10⁻⁵ |

All four associations remained significant after Benjamini–Hochberg correction.

The primary joint-carrier result indicates that participants carrying alternate alleles at both loci had approximately 23.9-fold greater odds of PP than non-joint carriers in this combined dataset. The confidence interval is wide because the joint-genotype category is rare; therefore, the odds ratio must always be reported with its confidence interval.

These estimates describe association and do not establish causality.

## 14. Output files

### 14.1 Public repository files

- `analyses/01_genetic_association/models_updated_AoU_v8.R`
- `results/genetic_association/firth_results_updated_AoU_v8_with_BH.csv`
- updated `README.md` instructions

The earlier `analyses/01_genetic_association/models.R` was preserved as the historical analysis.

### 14.2 Controlled-access or local-only files

The following must not be published in GitHub:

- `PP_cohort_updated_AoU_v8.ped`
- `PP_cohort_updated_AoU_v8.map` when linked to controlled participant rows;
- `PP_cohort_updated_AoU_v8_manifest.tsv`
- `two_vars_updated_AoU_v8.raw`
- `firth_models_updated_AoU_v8.rds` if it retains participant-level model frames or other potentially disclosive objects;
- participant-level Parquet or CSV genotype files;
- files containing actual All of Us `person_id` values.

Only aggregate, non-disclosive outputs were added to the public repository.

## 15. Relationship to the exploratory nine-variant result

The exploratory All of Us analysis found:

- no IL1RN c.*75C>G carrier among 135 disease-defined cases;
- no IL36RN P76L carrier among those 135 cases;
- three heterozygous carriers of `IL36RN chr2:113062547:C:T`, all in the PPP-only group;
- 11 IL1RN c.*75C>G carriers among 19,487 controls;
- nine P76L carriers among 19,487 controls;
- five IL1RN–P76L co-carriers among 19,487 controls.

These findings do not contradict the primary combined-cohort association because the analyses answer different questions and use different case definitions:

- the exploratory analysis evaluates nine variants in a newly constructed genotype-independent All of Us cohort;
- the primary association analysis retains the original 654-case manuscript series and replaces only the earlier All of Us control subset.

Neither dataset should be appended to the other without participant-level deduplication and a revised analysis plan.

## 16. Interpretation safeguards and limitations

1. **No phase inference:** Joint dosage and joint carriage do not prove that IL1RN c.*75C>G and IL36RN P76L occur on the same chromosome.
2. **Rare cells:** The large odds ratios and wide confidence intervals reflect rare carrier counts; point estimates must not be reported without confidence intervals.
3. **Source heterogeneity:** Cases and controls derive from multiple cohorts and may differ in recruitment, sequencing, ancestry composition, and other measured or unmeasured factors.
4. **Population structure:** The present models are unadjusted. Residual ancestry or population structure may confound the estimates.
5. **Batch effects:** Genotype generation and ascertainment differed between historical and updated data sources.
6. **Phenotype harmonization:** GPP and PPP were combined as PP for the primary association model, consistent with the earlier analysis, but they represent clinically distinct phenotypes.
7. **No causal claim:** Statistical association does not demonstrate that either variant, or their joint occurrence, is functionally causal.
8. **No duplicate All of Us controls:** The older 3,449-person All of Us control subset was removed before the updated 19,487-person control set was added.
9. **No duplicate All of Us cases:** The newer 135-person exploratory disease cohort was not added to the retained 144-person historical All of Us case series.
10. **Data governance:** Controlled All of Us participant-level data remain inside authorized environments and are excluded from the public repository.

## 17. Reproducibility checklist

- [x] Preserve protocol v8 as the immutable record of cohort and genotype extraction.
- [x] Retain the original 654 PP cases for the primary manuscript analysis.
- [x] Remove the earlier 3,449 All of Us controls.
- [x] Add the updated 19,487 All of Us controls.
- [x] Validate 25,887 total controls and 26,541 total participants.
- [x] Preserve missing genotypes as missing.
- [x] Export IL1RN and P76L additive dosages with PLINK.
- [x] Define joint dosage as the minimum dosage across both loci.
- [x] Fit four prespecified Firth logistic-regression models.
- [x] Calculate profile-likelihood confidence intervals.
- [x] Apply BH correction across the four tests.
- [x] Save aggregate results to the public repository.
- [x] Exclude participant-level controlled data from GitHub.
- [x] Record the final effect estimates in this protocol amendment.

## 18. Final analysis status

The primary updated association analysis is complete and reproducible from the controlled PLINK input and the public R script. Further ancestry-adjusted, source-stratified, or phenotype-specific analyses should be treated as new sensitivity analyses and documented in a subsequent amendment rather than silently replacing the results recorded here.

