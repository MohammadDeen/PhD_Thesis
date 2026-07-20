# 1. Background

## The underlying problem

Most disease-associated variants are noncoding, but interpreting them is difficult because:

- A noncoding variant may only function in one cell type or developmental state.
- Variants in linkage disequilibrium make it difficult to identify the causal variant at a GWAS locus.
- Bulk RNA-seq and bulk eQTL studies mix multiple cell types.
- Rare and ultra-rare variants have too few carriers for conventional association testing.
- Chromatin accessibility tells you that a region is potentially regulatory, but not necessarily whether a particular allele changes its activity.

This is directly relevant to your work because your current variant analyses are strongest for coding variants such as those in **IL36RN, MPO, CARD14 and AP1S3**. A comparable framework for noncoding variants could help evaluate promoters, enhancers and UTR-associated candidates from your WGS and extended candidate-gene analyses.

## ChromBPNet

The authors use **ChromBPNet**, a convolutional neural network trained on ATAC-seq or DNase-seq.

For a given DNA sequence, it predicts:

1. The expected base-resolution ATAC-seq profile.
2. The total predicted accessibility.
3. How replacing the reference allele with the alternate allele changes accessibility.
4. Which sequence bases and transcription-factor motifs drive that prediction.

A major technical advantage is that ChromBPNet explicitly models and removes **Tn5 sequence bias**. This matters because an apparent sequence-specific ATAC signal can otherwise reflect transposase preference rather than genuine transcription-factor activity.

## FLARE

The new tool developed in this paper is:

**FLARE — Functional Lasso Analysis of Regulatory Evolution**

FLARE integrates:

- ChromBPNet-predicted regulatory effects;
- whether the locus is accessible;
- distance to the nearest transcription start site;
- genomic annotations;
- sequence conservation/evolutionary constraint, particularly PhyloP.

It learns which combinations of regulatory features predict evolutionary constraint. A variant receives a high FLARE score when its predicted regulatory effect is unusually strong relative to the genomic and evolutionary context.

A simple conceptual distinction is:

- **ChromBPNet:** “Will this allele change accessibility in this cell type?”
- **FLARE:** “Is that regulatory change sufficiently unusual and evolutionarily constrained that it may be deleterious?”

---

# 2. Main results

## 2.1 Cell-type-specific regulatory models

The authors combined scATAC-seq from five studies and generated pseudobulk profiles for **132 cellular contexts**:

- 30 fetal brain contexts;
- 24 adult brain contexts;
- 33 fetal heart contexts;
- 45 adult heart contexts.

They trained a separate ChromBPNet model for each context.

The models identified developmental and cell-type-specific regulatory motifs. For example:

- NDF/ATOH motifs were more characteristic of fetal excitatory neurons.
- EGR and AP-1 activity was more specific to adult excitatory neurons.
- Broadly acting motifs included CTCF, SP/KLF, NF-Y and MAZ.

They generated approximately **3 billion predictions** and assessed more than **22 million noncoding variants** across the different analyses.

### Relevance to you

This is the conceptual model you would want for:

- neutrophils;
- monocytes/macrophages;
- keratinocytes;
- lesional versus non-lesional skin;
- acute disease versus remission.

Your neutrophil RNA-seq already shows strong context-dependent modules involving **S100A8/A9/A12, CXCL1/2/3/8, TREM1 and innate immune pathways**. A cell-specific ChromBPNet model could potentially connect regulatory variants to those expression modules.

---

## 2.2 Shared and cell-type-specific regulatory variants behave differently

The authors classified variants according to how broadly their predicted effects occurred:

- **Cell-type-shared:** predicted effects in more than 80% of evaluated contexts.
- **Cell-type-specific:** predicted effect in only one context.
- Intermediate variants affected multiple but not nearly all contexts.

They found that cell-type-shared variants tended to:

- have larger predicted effects;
- be closer to transcription start sites;
- occur frequently in promoters;
- disrupt broadly used transcription-factor motifs.

Cell-type-specific variants tended to:

- occur more distally;
- reside in enhancers;
- affect lineage- or differentiation-specific motifs;
- lie near genes involved in developmental programs.

Among the strongest predicted variants, **46.9% of shared variants were in verified promoters**, compared with only **0.5% of cell-type-specific variants**.

### Interpretation for your research

A regulatory variant affecting multiple immune and skin cell types may be promoter-proximal and relatively easy to connect to a gene. A GPP-specific enhancer variant, however, might:

- be far from the nearest gene;
- only become active in stimulated neutrophils or keratinocytes;
- be invisible in generic blood or resting-cell annotations;
- require cell-type-specific chromatin models to identify.

This provides a strong argument against filtering noncoding WGS variants using only nearest-gene distance or generic conservation scores.

---

## 2.3 Prioritization of eQTLs

Fine-mapped GTEx eQTLs with high posterior inclusion probability had higher ChromBPNet scores than variants unlikely to be causal.

Importantly, this enrichment depended on using the correct biological context:

- adult brain models performed better for adult brain eQTLs;
- heart models performed better for artery/heart eQTLs;
- fetal models were less appropriate for adult eQTLs;
- mismatched brain/heart models showed weaker enrichment.

Bulk brain eQTLs could also be separated into predicted neuronal and microglial effects.

### Relevance to you

This is one of the paper’s most important lessons:

> A sophisticated model trained in the wrong cell type may be less useful than a simpler model trained in the correct biological context.

The supplied brain and heart models should therefore not be treated as appropriate models for your GPP variants. For your work, the optimal models would come from:

- neutrophil ATAC-seq;
- monocyte/macrophage ATAC-seq;
- keratinocyte ATAC-seq;
- preferably stimulated and disease-relevant states.

---

## 2.4 Prioritization of causal GWAS variants

ChromBPNet-prioritized accessible variants were enriched for GWAS heritability. Disease-context matching again mattered:

- brain models prioritized Alzheimer’s disease, neuroticism and BMI loci;
- microglia showed particularly strong signals for Alzheimer’s disease;
- heart models prioritized atrial fibrillation and coronary artery disease loci.

At an Alzheimer’s locus within **RASGEF1C**, statistical fine-mapping produced four plausible variants. ChromBPNet narrowed these to a candidate variant, **rs113706587**, predicted to:

- create a ZEB/SNAI repressive motif;
- reduce microglial chromatin accessibility;
- reduce RASGEF1C expression.

CRISPR interference targeting the regulatory element subsequently reduced RASGEF1C expression, providing experimental support.

### Why this example matters for you

This is an excellent blueprint for a GPP noncoding variant:

1. Identify a statistical or family-based candidate.
2. Confirm that it overlaps accessible chromatin in the relevant cell.
3. predict allele-specific accessibility;
4. identify the disrupted or created motif;
5. connect the element to a target gene;
6. compare with RNA-seq;
7. perturb the regulatory element using CRISPRi or edit the nucleotide;
8. measure gene expression and a disease-relevant phenotype.

This could fit naturally with the CRISPR optimization work you are already doing.

---

## 2.5 Common versus ultra-rare regulatory variants

The 1000 Genomes analysis included:

- **6,349,771 common SNPs**, MAF >5%;
- **8,757,029 ultra-rare SNPs**, MAF <0.1%.

The major observation was:

- Ultra-rare variants had larger predicted regulatory effects.
- Ultra-rare variants were more likely to affect multiple cell types.
- Common variants were more frequently cell-type-specific.
- The strongest evidence of purifying selection occurred in fetal neuronal regulatory elements.
- Immune-cell contexts showed a smaller difference between common and ultra-rare variants.

The authors interpret this as evidence that broadly disruptive regulatory variants are more strongly selected against and therefore remain rare.

### Important nuance for your project

The weaker common-versus-rare difference in immune cells does **not** mean immune regulatory variants are unimportant. It suggests that immune regulatory regions may tolerate more variation, potentially because immune regulation is evolutionarily dynamic and influenced by adaptation.

For GPP, this could mean that important immune regulatory variants may:

- not be extremely conserved;
- be population-specific;
- affect inducible rather than constitutive programs;
- require disease-relevant stimulation to become visible.

This is particularly pertinent when comparing European GPP cohorts with reported variants from Chinese or other populations, as in your BTN3A3 work.

---

## 2.6 FLARE and de novo developmental-disorder variants

The authors trained FLARE models for fetal brain and heart regulatory contexts and applied them to de novo noncoding variants.

For autism spectrum disorder:

- FLARE prioritized de novo mutations near established ASD genes.
- High-ranking examples occurred near or within genes such as **FOXG1** and **CNTNAP2**.
- One predicted variant disrupted an RFX3 motif.
- Another affected an NFI-associated regulatory sequence.
- They estimated that approximately **1.2% of probands** carried an impactful regulatory de novo mutation, with a 95% CI of 0.5–1.9%.

For congenital heart disease:

- Seven of the ten highest-scoring mutations near high-confidence CHD genes occurred in cases.
- An example in an **ARID1B** intron was predicted to alter an ETS-related regulatory sequence.

### Relevance to your genomics software plans

FLARE represents the sort of algorithm that could eventually be incorporated into ATAG genomics as an evidence layer for noncoding variant prioritization. It should not be presented as a diagnostic classifier by itself. It would sit alongside:

- allele frequency;
- segregation;
- CADD/REVEL/SpliceAI-type predictions;
- ClinVar;
- enhancer/promoter overlap;
- disease-relevant chromatin accessibility;
- eQTL and expression evidence;
- evolutionary constraint;
- phenotype–gene matching.

---

## 2.7 Rare variants and expression outliers

The authors integrated WGS and adult brain RNA-seq from **791 ROSMAP individuals**.

FLARE-prioritized variants were enriched near genes showing marked underexpression:

- For variants in the top 0.1% of FLARE scores near genes with expression z<−3z < -3z<−3, the odds ratio was **5.4**.
- When restricted to promoter-proximal variants, the enrichment became stronger.
- Ten rare variants in the top 1% were found near strong underexpression outlier genes, corresponding to an OR of **15.4**.

There was little comparable enrichment near overexpressed genes.

### Direct application to your data

This suggests a potentially valuable WGS–RNA-seq analysis:

1. Identify rare noncoding variants near genes or linked regulatory regions.
2. Score those variants using a relevant accessibility model.
3. calculate sample-level expression z-scores;
4. test whether individuals carrying high-impact variants are expression outliers;
5. prioritize variants concordant with reduced or altered expression.

Your current RNA-seq cohorts are small, so formal enrichment testing would be limited. However, the approach could still be useful for individual-level mechanistic prioritization.

---

## 2.8 Common-variant disease heritability

FLARE scores also captured common disease-associated regulatory variation.

For schizophrenia, variants in the top 1% of fetal-brain FLARE scores showed approximately **19.1-fold enrichment** of per-SNP heritability. FLARE outperformed accessibility peaks alone.

This demonstrates that FLARE adds nucleotide-level information beyond simply knowing that a variant lies within an ATAC-seq peak.

---

# 3. Discussion and interpretation

## What the authors conclude

The paper argues that combining:

- single-cell chromatin accessibility;
- sequence-based deep learning;
- population allele frequencies;
- evolutionary constraint;
- eQTL/GWAS fine-mapping;
- expression outliers;

can interpret noncoding variants across the full frequency spectrum.

The main biological conclusions are:

1. Regulatory effects are highly context-dependent.
2. Bulk molecular data often obscure cell-type-specific effects.
3. Common variants are comparatively enriched for narrower, cell-specific effects.
4. Ultra-rare variants tend to have larger and broader regulatory effects.
5. Evolutionary constraint and predicted molecular effects are complementary.
6. A regulatory model can prioritize variants even when association studies lack power.

## Strengths

- Very large prediction resource.
- Multiple fetal and adult contexts.
- Explicit correction for Tn5 bias.
- Integration of common, rare and de novo variation.
- Validation across eQTLs, GWAS, expression outliers and disease cohorts.
- Mechanistic interpretation through DeepLIFT and motif analysis.
- Experimental validation of a selected regulatory element using CRISPRi.
- Open-source code and released models/scores.

## Limitations

### Tissue limitation

The models cover brain and heart—not skin, keratinocytes, neutrophils or monocytes. Their biological scores cannot simply be transferred to GPP.

### Predicted function is not confirmed function

A high ChromBPNet or FLARE score remains computational evidence. It does not prove:

- the affected target gene;
- the direction of gene-expression change;
- disease causality;
- the relevant physiological condition.

### Peak dependence

Variant interpretation is most reliable when the variant lies within accessible chromatin represented in the training data. A locus active only after IL-36, LPS, TNF, infection-like or inflammasome stimulation may be missed by a resting-cell model.

### SNP emphasis

Much of the large-scale population analysis focuses on SNPs. Although the scoring framework can technically accept insertions and deletions, indel interpretation is less extensively validated in the paper.

### Model and cohort complexity

Training high-quality models requires:

- deep ATAC-seq data;
- appropriate peak calling;
- matched genome builds;
- sufficient reads per pseudobulk context;
- GPU resources;
- careful Tn5-bias correction;
- held-out chromosome validation.

### Evolutionary constraint is incomplete

Recent, human-specific or population-specific immune regulatory elements may lack strong conservation despite genuine biological relevance. This is especially important for immune-mediated diseases.

---

# 4. Methods in structured form

## 4.1 Data preparation

The authors collected scATAC-seq/snATAC-seq from fetal and adult brain and heart.

For each annotated cell cluster:

1. Fragments were pooled into a cell-type pseudobulk.
2. Fragment files were converted to tagAlign format.
3. The ENCODE ATAC-seq pipeline was used.
4. MACS2 generated peak calls.
5. Reproducible peaks overlapping both pseudoreplicates were retained.

## 4.2 ChromBPNet training

- ChromBPNet version 0.1.7 was used.
- Input consisted of processed ATAC fragments/tagAlign files, peaks and genome sequence.
- A pretrained K562 ATAC bias model was used to account for Tn5 bias.
- Fivefold chromosome-held-out cross-validation was performed.
- Every chromosome appeared in a test fold.
- Models retaining excessive Tn5-motif sensitivity were retrained.
- Two poorly performing outlier models were excluded.

## 4.3 Variant scoring

For each variant and cell type:

1. A 1-kb sequence centred on the variant was generated.
2. One sequence contained the reference allele.
3. The other contained the alternate allele.
4. ChromBPNet predicted accessibility for both.
5. The primary effect was:

ChromBPNet score=log⁡2(predicted alternate accessibilitypredicted reference accessibility)\text{ChromBPNet score} = \log_2 \left( \frac{\text{predicted alternate accessibility}} {\text{predicted reference accessibility}} \right)ChromBPNet score=log2​(predicted reference accessibilitypredicted alternate accessibility​)

6. Empirical null distributions were used to estimate significance.

A positive or negative score indicates the predicted direction of accessibility change; the absolute value reflects effect magnitude.

## 4.4 Motif interpretation

The authors used:

- DeepLIFT/DeepSHAP for nucleotide contribution scores;
- TF-MoDISco to discover predictive sequence patterns;
- MotifCompendium to consolidate related motifs across models;
- Fi-NeMo to locate individual motif instances;
- JASPAR, CIS-BP and HOCOMOCO for motif annotation.

## 4.5 FLARE training

FLARE is a lasso regression framework predicting evolutionary constraint from:

- accessibility;
- ChromBPNet variant-effect scores;
- genomic context;
- TSS distance;
- related regulatory annotations.

The lasso penalty performs feature selection and reduces overfitting. Separate FLARE models can be trained for different tissues or collections of cell types.

## 4.6 Downstream evaluations

The authors evaluated the scores using:

- GTEx eQTL fine-mapping;
- disease GWAS fine-mapping;
- stratified LD-score regression;
- common versus ultra-rare 1000 Genomes variants;
- ASD and congenital heart disease de novo mutations;
- ROSMAP WGS and expression outliers;
- CRISPRi and RNA-seq validation.

---

# 5. Most relevant figures for you

|Figure|What it shows|Why it matters for your work|
|---|---|---|
|**Figure 1**|Construction of 132 cell-context ChromBPNet models; comparison of shared and cell-specific regulatory variants; promoter versus distal architecture|Best overview for designing a neutrophil/keratinocyte version of the framework|
|**Figure 2**|eQTL and GWAS prioritization; microglia-specific Alzheimer’s variant; motif disruption; CRISPRi validation|Closest blueprint for moving from a candidate GPP variant to an experimentally testable mechanism|
|**Figure 3**|Common versus ultra-rare regulatory effects and evidence of context-specific purifying selection|Most relevant to your rare-variant cohort and population-frequency interpretation|
|**Figure 4**|FLARE framework and prioritization of ASD de novo variants|Best explanation of what FLARE adds beyond ChromBPNet, CADD, PhyloP and TSS distance|
|**Figure 5**|CHD variants, expression outliers and schizophrenia heritability enrichment|Most relevant to integrating WGS, RNA-seq and disease association evidence|

If selecting only three figures for a journal club or project discussion, I would choose **Figures 1, 2 and 4**.

---

# 6. Where to find the tools

## ChromBPNet

The main package is available at:

- [ChromBPNet GitHub repository](https://github.com/kundajelab/ChromBPNet)
- Installable with `pip install chrombpnet`
- Docker image: `kundajelab/chrombpnet:latest`

The repository recommends an NVIDIA GPU for training and provides Docker and Conda workflows. [Its documentation](https://github.com/kundajelab/chrombpnet/blob/master/README.md?utm_source=chatgpt.com) includes training examples.

## Variant scorer

For scoring your own VCF-derived variant list with a trained ChromBPNet model:

- [variant-scorer repository](https://github.com/kundajelab/variant-scorer?utm_source=chatgpt.com)

It accepts SNVs, insertions and deletions and produces TSV outputs containing allele-effect predictions. It can also summarize scores across model folds, annotate peak/gene overlaps and calculate allele-specific SHAP values. [Repository documentation](https://github.com/kundajelab/variant-scorer?utm_source=chatgpt.com)

## FLARE

- [FLARE repository](https://github.com/drewmard/FLARE)
- [Paper-specific analysis repository](https://github.com/kundajelab/neuro-variants)
- Archived paper code
- Archived FLARE code

## Precomputed data

The authors released peak calls, trained models and variant scores through Synapse:

- Synapse resource 1
- Synapse resource 2

These precomputed scores primarily represent the paper’s brain and heart contexts.

---

# 7. How you could use it on your own data

There are three realistic levels.

## Level 1: Score selected variants using existing models

This is the easiest route.

You would need:

- a variant list derived from your WGS;
- GRCh38 coordinates;
- GRCh38 FASTA;
- chromosome sizes;
- one of the released ChromBPNet model files;
- preferably a disease-relevant model.

Example input:

```
chr1    1234567    G    A    sample1_variant1
chr2    2345678    C    T    sample2_variant1
```

Illustrative command:

```
python src/variant_scoring.py \
  --list gpp_variants.tsv \
  --genome Homo_sapiens_assembly38.fasta \
  --model chrombpnet_nobias.h5 \
  --out_prefix results/gpp \
  --chrom_sizes hg38.chrom.sizes \
  --schema chrombpnet \
  --no_hdf5
```

This would be technically straightforward, but the brain/heart context would make the biological interpretation weak for GPP.

## Level 2: Use public immune or skin ATAC-seq to train models

A better intermediate route would be to obtain public ATAC-seq/scATAC-seq for:

- neutrophils;
- monocytes;
- macrophages;
- keratinocytes;
- stimulated keratinocytes;
- psoriatic or inflammatory skin.

You could train context-specific models, then score variants from:

- your GPP exomes where regulatory flanking regions are available;
- your long-read WGS;
- your trio WGS;
- candidate-gene promoters/enhancers;
- future WGS cases.

This could become a valuable stand-alone computational analysis.

## Level 3: Train GPP-specific models using your ATAC-seq

This is the most biologically meaningful route.

Your existing ATAC-seq data are aligned to **hg19**, whereas this paper’s workflow and available reference resources are largely GRCh38-based. I would recommend reprocessing the original FASTQs against GRCh38 rather than lifting over peaks wherever possible.

A proposed pipeline would be:
![[Pasted image 20260720095138.png]]

Possible models from your current data might represent disease or sample contexts, but there is an important limitation: your ATAC-seq is bulk and has relatively few samples. The paper used cell-type pseudobulks derived from single-cell data. Bulk skin models would mix keratinocytes and infiltrating immune cells unless the samples are purified or the profiles are carefully interpreted.

## Recommended first application for you

I would start with a focused proof of concept:

1. Reprocess your ATAC-seq to GRCh38.
2. Establish whether the libraries have sufficient depth and quality for ChromBPNet.
3. Generate a high-confidence union peak set.
4. Train one or two initial models rather than many small subgroup models.
5. Score rare noncoding variants from your WGS cases.
6. Retain variants that:
    - overlap a GPP-accessible peak;
    - have a significant predicted allele effect;
    - disrupt a recognizable TF motif;
    - link to a biologically relevant gene;
    - agree with your skin or neutrophil RNA-seq.
7. Experimentally validate the strongest candidate.

For the first model, a well-powered pooled **pustular-disease ATAC model** may be more stable than separate models for every small phenotype group. Disease-specific subdivision can follow if model quality and sample depth support it.

---

# 8. How this could fit into your GPP thesis

This paper suggests a possible new analysis chapter:

> **Cell-context-aware prioritization of rare noncoding regulatory variants in pustular psoriasis**

The chapter could combine:

- rare variants from WGS;
- GPP/PPP/AGEP ATAC-seq;
- skin and neutrophil RNA-seq;
- ChromBPNet allele-effect predictions;
- motif disruption;
- expression concordance;
- selected CRISPR validation.

This would complement, rather than replace, your coding-variant meta-analysis. The coding work establishes the burden of genes such as **IL36RN and MPO**; the ChromBPNet/FLARE approach would investigate whether unexplained patients carry rare regulatory variants affecting the same or convergent pathways.

The central message I would take from the paper for your work is:

> Do not ask only whether a noncoding variant is conserved or close to a known gene. Ask whether it changes regulatory activity in the particular cell state that drives the disease.