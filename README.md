# 🧬 Genetic Disorders and Rare Diseases Analysis

**Authors:** Aqba Ejaz, Hafsah Batool, Nagina Naweed  
**Date:** March 1, 2025  
**Course:** Special Topics in Bioinformatics  
**Institution:** NUST

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Selected Disorders and Variants](#selected-disorders-and-variants)
3. [Pipeline Workflow](#pipeline-workflow)
4. [Prerequisites](#prerequisites)
5. [Installation](#installation)
6. [Usage](#usage)
7. [Results](#results)
8. [Citations](#citations)
9. [License](#license)

---

## Overview

This project provides a comprehensive analysis of **six genetic conditions** — three genetic disorders and three rare diseases. For each condition, we:

- Selected one clinically relevant variant from the **ClinVar** database
- Extracted detailed variant information and reviewed scientific literature
- Obtained phenotype data from **OMIM**
- Captured pathogenicity predictions from **UCSC Genome Browser** using AlphaMissense and RAVEL tracks
- Applied **ACMG/AMP** classification guidelines
- Created a **VCF file** simulating patient data
- Annotated all variants using **ClinVar** and **NCBI Batch Entrez**

| Detail | Value |
|---|---|
| Dataset | Six disease-causing variants from ClinVar |
| Reference Genome | GRCh38 human genome assembly |
| Tools Used | ClinVar, OMIM, UCSC Genome Browser, NCBI Batch Entrez, Excel |

---

## Selected Disorders and Variants

### Genetic Disorders

| Disease | Gene | Variant ID | Nucleotide Change | Protein Change |
|---|---|---|---|---|
| Cystic Fibrosis | *CFTR* | rs113993960 | c.1521_1523delCTT | p.Phe508del |
| Duchenne Muscular Dystrophy | *DMD* | 3718685 | c.10478del | p.Gln3493fs |
| Hereditary Breast & Ovarian Cancer | *BRCA1* | rs80359874 | c.1175_1214del | p.Leu392fs |

### Rare Diseases

| Disease | Gene | Variant ID | Nucleotide Change | Protein Change |
|---|---|---|---|---|
| Hemophilia A | *F8* | rs387906447 | c.2945dup | p.Asn982fs |
| Congenital Myotonia (Thomsen disease) | *CLCN1* | rs10282312 | c.352G>T | p.Gly118Trp |
| Intellectual Disability X-linked (Turner type) | *HUWE1* | rs121918527 | c.12559C>T | p.Arg4187Cys |

---

## Pipeline Workflow

### Step 1 — ClinVar Analysis

We accessed the [NCBI ClinVar database](https://www.ncbi.nlm.nih.gov/clinvar) and searched for each of the six conditions by disease name and gene symbol. For every disease, we selected one well-characterized pathogenic variant with high review status, ensuring multiple submissions or expert panel review where available.

**Data extracted per variant:**
- Gene symbol, Variant ID, Nucleotide change, Protein change
- Clinical significance, Review status (star ratings), Number of submissions

---

### Step 2 — Literature Review

On each ClinVar variant page, we followed PubMed links to research scientific studies. Key functional consequences investigated:

| Disease | Functional Consequence Studied |
|---|---|
| Cystic Fibrosis | Protein misfolding and ER degradation |
| BRCA1 | Loss of DNA repair via homologous recombination |
| DMD | Complete absence of dystrophin → muscle membrane instability |
| Hemophilia A | Factor VIII deficiency affecting coagulation cascade |
| CLCN1 | Chloride channel dysfunction in muscle relaxation |
| HUWE1 | Ubiquitin ligase role in neuronal development |

We also gathered population genetics data including allele frequencies and carrier rates across ethnic groups.

---

### Step 3 — OMIM Phenotype Analysis

We visited [OMIM](https://www.omim.org) and documented the following for each condition:

- **Inheritance pattern** — AR (Cystic Fibrosis), AD (BRCA1), X-linked recessive (DMD, Hemophilia A, HUWE1)
- **Age of onset** — Early childhood to adulthood depending on condition
- **Major clinical features** — Pulmonary/pancreatic (CF), progressive muscle weakness (DMD), cancer risk (BRCA1), bleeding (Hemophilia A), muscle stiffness (myotonia), developmental delay (HUWE1)
- **Disease progression, complications, and genotype-phenotype correlations**

---

### Step 4 — UCSC Genome Browser Analysis

We accessed the [UCSC Genome Browser](https://genome.ucsc.edu) with the **GRCh38** assembly using these genomic coordinates:

| Disease | Coordinates |
|---|---|
| Hemophilia A | chrX:154,930,844–154,930,845 |
| Congenital Myotonia | chr7:143,320,700–143,320,730 |
| HUWE1 | chrX:53,535,474 |

**Tracks added:** AlphaMissense and RAVEL (via Track Hubs → Public Hubs)

> **AlphaMissense** (Google DeepMind) predicts missense variant pathogenicity with scores from 0–1. Scores above **0.564** indicate likely pathogenic variants (shown in red).

Screenshots were captured at base-pair resolution for all variants.

---

### Step 5 — ACMG/AMP Classification

We applied ACMG/AMP guidelines using the following evidence codes:

| Code | Strength | Description |
|---|---|---|
| PVS1 | Very Strong | Null variant in LoF disease gene |
| PS1, PS3, PS4 | Strong | Same AA change as known pathogenic; functional studies; prevalence in affected |
| PM2, PM3 | Moderate | Absent from population databases; variant in trans with pathogenic |
| PP1, PP3, PP5 | Supporting | Co-segregation; computational predictions; reputable source |

**Classification results:**

| Disease | Codes Applied | Classification |
|---|---|---|
| Cystic Fibrosis | PVS1, PS1, PS3, PS4, PM2, PM3, PP1, PP3 | Pathogenic |
| BRCA1 | PVS1, PS1, PS4, PM2, PP1, PP3 | Pathogenic |
| DMD | PVS1, PS1, PM2, PP3, PP5 | Pathogenic |
| Hemophilia A | PVS1, PS1, PS3, PM2, PP1, PP3 | Pathogenic |
| Congenital Myotonia | — | Benign |
| HUWE1 | PS1, PS3, PS4, PM2, PP1, PP3 | Pathogenic |

---

### Step 6 — VCF File Creation

We created a **Variant Call Format (VCF v4.3)** file simulating whole-genome/exome sequencing patient data.

**Header includes:** file format version, date, GRCh38 reference, contig definitions (chr7, chr17, chrX)  
**Columns:** CHROM, POS, ID, REF, ALT, QUAL, FILTER, INFO, FORMAT, PATIENT

**Genotype conventions used:**

| Condition | Genotype | Rationale |
|---|---|---|
| Cystic Fibrosis | 1/1 | Homozygous alternate (AR) |
| BRCA1 / Autosomal rare | 0/1 | Heterozygous |
| X-linked (male) | 1/0 | Hemizygous |

---

### Step 7 — ClinVar Annotation

All variants were verified via **NCBI Batch Entrez** (SNP database) and direct ClinVar search:

| Variant | Gene | Confirmation |
|---|---|---|
| rs113993960 | CFTR | Pathogenic — inframe deletion ✅ |
| rs80359874 | BRCA1 | Pathogenic — frameshift ✅ |
| rs387906447 | F8 | Pathogenic — duplication ✅ |
| rs10282312 | CLCN1 | Benign — missense ✅ |
| rs121918527 | HUWE1 | Pathogenic — missense ✅ |
| 3718685 | DMD | Pathogenic — frameshift (ClinVar direct) ✅ |

---

## Prerequisites

### Compute Environment

| Requirement | Detail |
|---|---|
| Storage | ≥ 1 GB free (files + screenshots) |
| Internet | Required for all database queries |
| OS | Any (browser-based analysis) |

### Software

- Web browser (Chrome, Firefox, or Safari)
- Microsoft Excel or compatible spreadsheet software
- Text editor (e.g., Notepad) for VCF file creation
- GitHub account for repository hosting

### Databases

| Database | URL |
|---|---|
| ClinVar | https://www.ncbi.nlm.nih.gov/clinvar |
| OMIM | https://www.omim.org |
| UCSC Genome Browser | https://genome.ucsc.edu |
| NCBI Batch Entrez | https://www.ncbi.nlm.nih.gov/sites/batchentrez |
| PubMed | https://pubmed.ncbi.nlm.nih.gov |

---

## Installation

```bash
# Step 1 — Clone the repository
git clone https://github.com/eklhmah123/genetic-disorders-analysis.git
cd genetic-disorders-analysis

# Step 2 — Prepare workspace
mkdir -p data screenshots annotation_results
```

> **Note:** Reference genome GRCh38 information was accessed through the UCSC Genome Browser. Variant coordinates were obtained directly from ClinVar variant pages.

---

## Usage

### 1. ClinVar Data Extraction
Navigate to ClinVar and search by disease name or gene symbol. Select one pathogenic variant per disease and extract gene symbol, variant ID, nucleotide change, protein change, clinical significance, review status, and number of submissions into Excel.

### 2. Literature Review
Follow PubMed links from each ClinVar variant page. Read abstracts and key papers to understand functional consequences, population genetics, and clinical observations. Summarize in paragraph form for the **Explanation** field.

### 3. OMIM Phenotype Analysis
Search OMIM by disease name or OMIM ID. Document inheritance pattern, age of onset, major clinical features, disease progression, and genotype-phenotype correlations for the **Phenotype** field.

### 4. UCSC Screenshot Capture
1. Obtain genomic coordinates from ClinVar
2. Go to UCSC Genome Browser → select **Human GRCh38** → enter coordinates → click **GO**
3. Add **AlphaMissense** and **RAVEL** tracks via Track Hubs → Public Hubs
4. Zoom in to base-pair resolution and take screenshots
5. Insert screenshots into Excel columns **L** and **M**

### 5. ACMG Classification
Apply ACMG/AMP guidelines (PVS1, PS1–PS4, PM2–PM3, PP1–PP5). Document applicable evidence codes and record final classification in **Column K**.

### 6. VCF File Creation
Create a `.vcf` file in a text editor with:
- Header lines: `##fileformat`, `##fileDate`, `##reference`, `##contig`
- Column headers separated by tabs
- Data lines for all six variants with CHROM, POS, ID, REF, ALT, QUAL, FILTER, INFO, FORMAT, and genotype

### 7. Variant Annotation
- **rs-number variants:** Use NCBI Batch Entrez → SNP database → upload variant ID list → Retrieve
- **DMD variant (3718685):** Search directly in ClinVar
- Save results and screenshot confirmation pages

---

## Results

### Summary

| Metric | Value |
|---|---|
| Total variants analyzed | 6 |
| Pathogenic variants | 5 |
| Benign variants | 1 |
| Variants with expert panel review | 3 |
| Variants with multiple submissions | 4 |

> All five pathogenic variants were confirmed as disease-causing with strong multi-source evidence. The CLCN1 variant was correctly identified as benign, demonstrating that not every variant in a disease-associated gene is pathogenic.

---



