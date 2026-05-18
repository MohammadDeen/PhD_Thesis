**1. The Core Mechanism**

- **Molecular Machinery:** The system requires two main parts: a **Cas enzyme** (the "scissors") and a **guide RNA** (the "GPS"). When joined, they form a **Ribonucleoprotein (RNP) complex**.
- **The Target:** The guide RNA directs Cas9 to a 20-nucleotide sequence in the genome. However, the enzyme will only cut if it first recognizes a **PAM (Protospacer-Adjacent Motif)** sequence, such as NGG, immediately following the target.
- **The Cut:** Once activated, Cas9 creates a **double-strand break (DSB)** typically 3–4 base pairs upstream of the PAM.

**2. DNA Repair & Editing Outcomes**

The "edit" itself is actually performed by the cell's own repair machinery in response to the break:

- **NHEJ (Non-Homologous End Joining):** The cell's default, error-prone repair. It often creates small insertions or deletions (**indels**), leading to a **gene knockout**.
- **HDR (Homology-Directed Repair):** A precise repair pathway that uses a provided **donor template** to integrate specific changes, such as a **gene knock-in** or point mutation.

**3. Optimized Delivery (RNP Electroporation)**

While there are multiple ways to deliver CRISPR (plasmids, virus, RNP), the **RNP delivery method** is highlighted as the superior choice for high-precision projects like your MUTZ-3 study:

- **Efficiency:** It achieves high editing rates (60–95%) even in hard-to-transfect cells.
- **Safety:** Because the RNP complex is transient and degrades within 24–72 hours, it significantly reduces the risk of **off-target effects** compared to permanent viral delivery.

**4. Laboratory Workflow & Validation**

For your specific project targeting **VSIG4** and **FN1**, the protocol follows a structured 7-week timeline:

- **Preparation:** Pre-assembling RNPs for 10 minutes at room temperature before using a **4D-Nucleofector** for delivery.
- **Bulk Validation:** Using the **T7 Endonuclease I (T7E1) assay** to quickly check editing efficiency in the overall cell population or via snager sequencing
- **Clonal Selection:** Performing limiting dilution to isolate single-cell clones and using **Sanger sequencing** or **NGS (Next-Generation Sequencing)** to confirm the exact genetic mutation.
- **Functional Readout:** Confirming the protein change via **Western Blot** and observing the cells' ability to differentiate into functional **osteoclasts**