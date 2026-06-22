authors:

- Rundong Jiang
- Joseph Kirma
- Jennifer Fox
- Xianying Xing
- Jiaqi Wang
- Mrinal K. Sarkar
- Rachael Bogle
- Tran Do
- Anthony Coon
- Christopher Cole
- Olesya Plazyo
- Joanna E. Rew
- Haihan Zhang
- J. Michelle Kahlenberg
- Allison C. Billi
- Hervé Bachelez
- Lam C. Tsoi
- Paul W. Harms
- Shuai Shao
- Xiang Chen
- Johann E. Gudjonsson  
    year: 2026  
    journal: Nature Communications  
    doi: 10.1038/s41467-025-67917-9  
    topics:
- generalized pustular psoriasis
- IL-36
- TNFSF15
- TL1A
- neutrophils
- keratinocytes
- single-cell RNA-seq
- spatial transcriptomics
- fibroblasts
- psoriasis  
    tags:
- literature-note
- gpp
- il36
- neutrophils
- keratinocytes
- scRNAseq
- spatial-transcriptomics  
    status: read


## One-sentence summary

This paper uses ==single-cell RNA-seq, spatial transcriptomics, and functional co-culture assay==s to show that GPP lesions are organized around an inflammatory communication network between ==**IL36G+ keratinocytes** and **TNFSF15/TL1A-producing neutrophils**,== with additional contributions from fibroblasts, endothelial cells, macrophages, and T cells- [@jiangDynamicNeutrophilkeratinocyteCommunication2025].

## Why this paper matters

Generalized pustular psoriasis is already known to be strongly linked to dysregulated **IL-36 signalling**, especially through genetic defects such as ***IL36RN*** loss of function. However, the ==precise cellular architecture== of GPP lesions has been poorly resolved. This paper is important because it moves beyond bulk transcriptomics and immunostaining by ==mapping which cell types participate in GPP inflammation, where they are located in the tissue, and how they communicate.==

For my own work on genetic risk factors in GPP, this paper is useful because it connects genetic and cytokine-level understanding of GPP to actual lesional cell states. It also suggests that neutrophils are not just passive recruited effector cells but active signalling partners that may amplify keratinocyte inflammation through **TL1A/DR3 signalling**.

## Main research question

What cellular subtypes and intercellular communication networks define GPP lesional skin, and how do neutrophils and keratinocytes interact to amplify IL-36-driven inflammation?

## Study design

The authors profiled lesional skin from **13 patients with GPP** and skin from **4 healthy controls** using single-cell RNA-seq. They analysed approximately **60,000 cells** and identified major skin and immune cell populations. They complemented this with **spatial transcriptomics** using the Xenium platform on selected GPP and control skin samples.

The analysis included:

- Single-cell RNA-seq of FFPE skin biopsies.
- Cell clustering and annotation using canonical skin/immune markers.
- Myeloid, neutrophil, T cell, fibroblast, endothelial, and keratinocyte subclustering.
- Pathway enrichment and module-score analysis.
- Pseudotime analysis of neutrophil and macrophage states.
- Cell-cell communication analysis using tools such as CellChat and NicheNet.
- Spatial transcriptomics to validate proximity of predicted interacting cells.
- In vitro neutrophil-keratinocyte co-culture experiments.
- TL1A blockade experiments.
- IL36G knockout keratinocyte experiments.

## Key findings

### 1. GPP lesional skin is dominated by innate immune remodelling

The authors identified ==11 major cell types,== including keratinocytes, fibroblasts, endothelial cells, myeloid cells, T cells, mast cells, melanocytes, pericytes, and eccrine cells. ==Myeloid cells were increased in GPP lesions, whereas T cells== did not show the same level of absolute expansion. This supports the idea that GPP is more strongly driven by innate immune mechanisms than classical plaque psoriasis.

### 2. Myeloid cells shift toward inflammatory macrophage and neutrophil states

Within the myeloid compartment, the authors identified several macrophage and dendritic cell subsets. ==GPP lesions showed an increase in **IL1B+ macrophages** and **MRC1+CCL18+ macrophages**, with a reduction in **MRC1+CXCL12+ macrophages**==. The IL1B+ macrophages had features of M1-like inflammatory macrophages, including expression of **IL1B**, **TLR2**, **LYZ**, and **FOS**.

==This suggests that GPP lesions contain a macrophage compartment skewed toward inflammatory activation==.

### 3. A CASP8-low/CXCL8-high neutrophil state characterizes GPP inflammation

The neutrophil analysis is one of the strongest parts of the paper. The authors identified neutrophil subtypes including:

- **CXCL8+ neutrophils**
- **S100A12+ neutrophils**
- **CASP8+ neutrophils**

The **CXCL8+ neutrophils** were largely specific to GPP lesions and expressed inflammatory genes such as **IL1B**, **IL1RN**, **CXCL8**, **PTGS2**, **NFKB1**, and **RIPK1**. In contrast, **CASP8+ neutrophils** were more associated with healthy skin and appeared less inflammatory.

==The authors propose a transition from a relatively pre-inflammatory **CASP8+ neutrophil state** toward a pro-inflammatory **CASP8-low/CXCL8+ state**. This is biologically interesting because CASP8 can suppress necroptotic inflammatory cell death. Loss of CASP8-like features may therefore permit inflammatory neutrophil activation.==

## Important mechanistic model

The paper proposes the following model:

```
IL36G+ keratinocytes → inflammatory epidermal programme
        ↑                         ↓
TNFSF15/TL1A+ neutrophils ← CXCL chemokine recruitment
```

More specifically:

1. IL-36 signalling activates keratinocytes.
2. Keratinocytes express chemokines such as **CXCL1** and **CXCL8**, attracting neutrophils.
3. Neutrophils contribute proteases that can activate IL-36 cytokines.
4. Neutrophils also produce **TNFSF15/TL1A**.
5. TL1A interacts with **TNFRSF25/DR3** on IL36G+ keratinocytes.
6. This amplifies keratinocyte inflammatory gene expression.
7. The loop sustains epidermal neutrophilic inflammation.

## Keratinocyte findings

The authors show that inflammatory keratinocyte responses are strongest in the **spinous and supraspinous epidermal compartments**. GPP-associated keratinocytes express genes such as:

- **IL36G**
- **IL36RN**
- **IL1RN**
- **S100A7**
- **S100A8**
- **S100A9**
- **KRT6A**
- **KRT6B**
- **KRT6C**
- **CXCL1**
- **CXCL2**

==The most inflammatory keratinocyte state appears to be the **IL36G+ supraspinous keratinocyte** population. However, the paper also suggests that **IL36G+ spinous keratinocytes** may be early responders in the neutrophil-keratinocyte loop.==

## Fibroblast and endothelial cell findings

The authors identify **SFRP2+ fibroblasts** as important stromal contributors in GPP. These fibroblasts express inflammatory and chemotactic genes including:

- **CCL2**
- **CXCL1**
- **CXCL2**
- **IL6**
- **CEBPB**
- **FOS**
- **JUNB**
- **STAT1**
- **NFKB1**
- **IRF1**

Cell-cell communication analysis suggested that SFRP2+ fibroblasts may promote recruitment of neutrophils and macrophages through CXCL and CSF1-related signals.

The authors also identify capillary endothelial cell states that may contribute to immune-cell trafficking, including T cell recruitment through **CCL21**.

## T cell findings

Although GPP is mainly presented here as an innate immune/neutrophilic disease, the authors also detect T cell involvement. They identify increased **Th17-like cells** and cytotoxic T cells in GPP lesions.

The Th17 compartment expresses genes such as:

- **IL22**
- **IL26**
- **CCR6**
- **IL17RB**

==However, the authors did not detect strong expression of **IL17A** or **IL17F**, which is worth noting when comparing GPP with plaque psoriasis.==

## Functional validation

The most important functional experiment is the ==neutrophil-keratinocyte co-culture assay.==

The authors used neutrophils from healthy donors, activated them with PMA, and co-cultured them with primary human keratinocytes or N/TERT keratinocytes. They found that activated neutrophils could drive inflammatory gene expression in keratinocytes.

They then blocked **TL1A** and observed reduced keratinocyte inflammatory responses. In IL36G knockout keratinocytes, TL1A blockade no longer produced additional inhibition, suggesting that the TL1A-driven neutrophil-keratinocyte interaction depends on IL36G-expressing keratinocytes.

==This supports the idea that TL1A/TNFSF15 is not merely a predicted ligand-receptor interaction but functionally contributes to the inflammatory loop.==

## Figures to remember

### Figure 1

Provides the global single-cell and spatial atlas of GPP skin. Shows the major cell types, increased myeloid cells in GPP, and enhanced fibroblast-to-immune-cell interactions.

### Figure 2

Defines myeloid subtypes. Important for the macrophage shift toward inflammatory IL1B+ macrophages.

### Figure 3

Key neutrophil figure. Shows CXCL8+ inflammatory neutrophils, CASP8+ neutrophils in healthy/control skin, inflammatory pathway enrichment, pseudotime transition, and CASPASE-8/MPO staining.

### Figure 5

Key stromal figure. Shows SFRP2+ fibroblasts and their predicted role in myeloid recruitment via chemokines such as CXCL1/CXCL2.

### Figure 6

==Key keratinocyte figure. Shows that IL-36, IL-17, and IL-1β response scores are highest in spinous/supraspinous keratinocytes, especially IL36G+ supraspinous keratinocytes.==

### Figure 7

==Most important mechanistic figure. Shows predicted and spatially validated interaction between **TNFSF15/TL1A+ MPO+ neutrophils** and **IL36G+ TNFRSF25+ keratinocytes**, plus functional validation using TL1A blockade and IL36G knockout keratinocytes.==

## Strengths

- Uses lesional skin rather than only blood, making the results more directly relevant to disease-site pathology.
- Combines scRNA-seq with spatial transcriptomics, helping validate predicted cell-cell interactions anatomically.
- Goes beyond descriptive single-cell analysis by including functional co-culture validation.
- Identifies a potentially actionable signalling axis: **TNFSF15/TL1A → TNFRSF25/DR3**.
- Provides a more complete view of GPP involving keratinocytes, neutrophils, fibroblasts, endothelial cells, macrophages, and T cells.

## Limitations

The study has several important limitations.

First, it focuses on GPP and does not include other neutrophilic dermatoses such as Sweet syndrome. Therefore, it is not fully clear which findings are GPP-specific and which reflect broader neutrophilic skin inflammation.

Second, the study does not stratify deeply by ***IL36RN* mutation status**. This matters because IL36RN mutations are a major genetic driver of GPP, and patients with and without IL36RN mutations may have different molecular pathways.

Third, the TL1A/DR3 interaction was validated using IL36G knockout and wild-type keratinocytes, but this may not fully reproduce the exact behaviour of naturally occurring IL36G+ spinous keratinocytes in vivo.

Fourth, several predicted interactions, especially those involving SFRP2+ fibroblasts and neutrophils/macrophages, remain computational/spatial predictions and require direct experimental validation.

## My interpretation

This paper strengthens the model of GPP as an IL-36-centered neutrophilic autoinflammatory skin disease, but it adds a new layer: ==neutrophils may actively amplify keratinocyte inflammation through **TNFSF15/TL1A**, rather than only activating IL-36 through proteases or acting as final effector cells.==

The most useful conceptual advance is that GPP inflammation may be sustained by a reciprocal loop:

```
IL36G+ keratinocytes recruit and activate neutrophils.
Neutrophils process IL-36 and release TL1A.
TL1A stimulates DR3/TNFRSF25+ keratinocytes.
Keratinocytes amplify chemokine and inflammatory cytokine production.
```

This is highly relevant to genetic studies because *IL36RN* mutations may initiate or intensify this loop, but the loop itself may operate as a shared downstream inflammatory pathway across genetically heterogeneous GPP patients.

## Relevance to my PhD work

This paper is directly relevant to my project on genetic risk factors and molecular characterization of GPP because:

- It provides a cellular framework for interpreting variants in ***IL36RN**, **CARD14**, **MPO**, **AP1S3**,* and other innate immune genes.
- It supports the idea that neutrophils are central disease-amplifying cells in GPP.
- It provides candidate pathways to examine in my RNA-seq data, including **IL36G**, **TNFSF15**, **TNFRSF25**, **CXCL1**, **CXCL8**, **IL1B**, **IL1RN**, **S100A8/A9**, and **PTGS2**.
- It gives a rationale for comparing lesional vs non-lesional skin and neutrophil transcriptomes using cell-type-specific gene signatures.
- It may help explain why GPP can be clinically severe even when different patients carry different upstream genetic risk variants.

## Genes/pathways to check in my datasets

### Keratinocyte-related

- IL36G
- IL36A
- IL36RN
- IL1RN
- IL1RL2
- CARD14
- S100A7
- S100A8
- S100A9
- KRT6A
- KRT6B
- KRT6C
- CXCL1
- CXCL2
- CXCL8

### Neutrophil-related

- TNFSF15
- MPO
- CXCL8
- IL1B
- IL1RN
- PTGS2
- RIPK1
- NFKB1
- NFKBIA
- FOS
- S100A12
- CASP8
- IFNAR1

### Fibroblast/stromal-related

- SFRP2
- CCL2
- CXCL1
- CXCL2
- IL6
- CSF1
- CCL21
- STAT1
- NFKB1
- IRF1

## Possible follow-up analyses for my own work

- Score the paper’s IL36G+ keratinocyte signature in my GPP lesional/non-lesional RNA-seq data.
- Check whether **TNFSF15** is elevated in my neutrophil RNA-seq dataset during flare compared with remission.
- Compare **CASP8**, **RIPK1**, **IL1B**, **CXCL8**, and **PTGS2** in patient neutrophils across disease states.
- Test whether IL36RN-mutated patients show stronger IL36G/TNFSF15/CXCL8 signatures than non-mutated patients.
- Use this paper’s gene sets to interpret scRNA-seq or deconvolution results from GPP skin.
- Consider whether MPO variants could modify IL-36 activation or neutrophil inflammatory state.

## Questions this paper raises

- Is TNFSF15/TL1A activation specific to GPP, or is it shared with AGEP, Sweet syndrome, pustular psoriasis subtypes, or SAPHO-associated skin inflammation?
- Does IL36RN mutation status determine the strength of the TL1A/DR3 neutrophil-keratinocyte loop?
- Are CASP8-low/CXCL8-high neutrophils a cause of flare amplification or a consequence of the inflammatory environment?
- Could TL1A blockade be therapeutically useful in GPP, either alone or combined with IL-36R blockade?
- How do MPO variants affect neutrophil-driven IL-36 activation in this model?
- Are SFRP2+ fibroblasts actively recruiting neutrophils, or are they secondarily activated by keratinocyte/neutrophil inflammation?

## Take-home message

GPP lesional inflammation is organized around a spatially coordinated network involving **IL36G+ keratinocytes**, **CASP8-low/CXCL8+ inflammatory neutrophils**, and **TNFSF15/TL1A-mediated neutrophil-to-keratinocyte signalling**. Stromal cells, especially **SFRP2+ fibroblasts** and capillary endothelial cells, may further shape immune recruitment. The paper reframes neutrophils as active signalling amplifiers in GPP rather than merely recruited effector cells.

## Citation

Jiang R. et al. Dynamic neutrophil-keratinocyte communication network centered on IL-36/TNFSF15 responses characterizes inflammatory responses in generalized pustular psoriasis. _Nature Communications_. 2026;17:1156. doi:10.1038/s41467-025-67917-9.