GENETIC DISORDERS AND RARE DISEASES ANALYSIS
Author:  Aqba Ejaz, Hafsah Batool, Nagina Naweed
Date: March 1, 2025
Course: Special Topics in Bioinformatics
Institution: NUST

Table of Contents
Overview

Selected Disorders and Variants

Pipeline Workflow

Prerequisites

Installation

Usage

Results

Troubleshooting

Citations

License

Overview
This project provides a comprehensive analysis of six genetic conditions including three genetic disorders and three rare diseases. For each condition, we selected one clinically relevant variant from the ClinVar database, extracted detailed information, researched scientific literature, obtained phenotype data from OMIM, captured pathogenicity predictions from UCSC Genome Browser using AlphaMissense and RAVEL tracks, applied ACMG/AMP classification guidelines, created a VCF file simulating patient data, annotated all variants using ClinVar and NCBI Batch Entrez, and organized everything in this GitHub repository with complete documentation.

Dataset: Six disease-causing variants from ClinVar
Reference: GRCh38 human genome assembly
Tools: ClinVar, OMIM, UCSC Genome Browser, NCBI Batch Entrez, Excel

Selected Disorders and Variants
The three genetic disorders analyzed include Cystic Fibrosis caused by mutations in the CFTR gene, Duchenne Muscular Dystrophy caused by mutations in the DMD gene, and Hereditary Breast and Ovarian Cancer caused by mutations in the BRCA1 gene. The three rare diseases analyzed include Hemophilia A caused by mutations in the F8 gene, Congenital Myotonia also known as Thomsen disease caused by mutations in the CLCN1 gene, and Intellectual Disability X-linked Turner type caused by mutations in the HUWE1 gene.

For Cystic Fibrosis we selected the variant rs113993960 which corresponds to the common F508del mutation with nucleotide change c.1521_1523delCTT and protein change p.Phe508del. For Duchenne Muscular Dystrophy we selected variant 3718685 which is a frameshift deletion with nucleotide change c.10478del and protein change p.Gln3493fs. For Hereditary Breast Cancer we selected rs80359874 which is a forty base pair deletion with nucleotide change c.1175_1214del and protein change p.Leu392fs. For Hemophilia A we selected rs387906447 which is a duplication in the F8 gene with nucleotide change c.2945dup and protein change p.Asn982fs. For Congenital Myotonia we selected rs10282312 in the CLCN1 gene with nucleotide change c.352G>T and protein change p.Gly118Trp which is classified as benign although other variants in this gene cause the disease. For Intellectual Disability we selected rs121918527 in the HUWE1 gene with nucleotide change c.12559C>T and protein change p.Arg4187Cys.

Pipeline Workflow
Step 1 — ClinVar Analysis

We accessed the NCBI ClinVar database at ncbi.nlm.nih.gov slash clinvar and searched for each of the six conditions by disease name and gene symbol. For every disease we selected one well-characterized pathogenic variant with high review status ensuring that each variant had multiple submissions or expert panel review where available. From each variant page we extracted the gene symbol, variant ID, nucleotide change, protein change, clinical significance, review status indicated by star ratings, and the number of submissions. This information formed the foundation of our Excel sheet documenting the essential identifiers and clinical assertions for each variant.

Step 2 — Literature Review for Explanation Field

On each ClinVar variant page we followed PubMed links to research scientific studies about the variants. We read abstracts and key papers to understand the functional consequences of each mutation including how each alteration affects protein structure and function. For CFTR we learned about protein misfolding and degradation in the endoplasmic reticulum. For BRCA1 we studied the loss of DNA repair function through homologous recombination. For DMD we researched the complete absence of dystrophin protein leading to muscle membrane instability. For Hemophilia A we examined factor VIII deficiency affecting the coagulation cascade. For CLCN1 we explored chloride channel function in muscle relaxation and for HUWE1 we studied the role of ubiquitin ligases in neuronal development. We also gathered population genetics data such as allele frequencies and carrier rates in different ethnic groups along with clinical observations from affected individuals and families.

Step 3 — OMIM Phenotype Analysis

We visited the Online Mendelian Inheritance in Man database at omim.org and searched using disease names or OMIM IDs to obtain detailed phenotype information. For each condition we documented the inheritance pattern which ranged from autosomal recessive in Cystic Fibrosis to autosomal dominant in BRCA1 to X-linked recessive in DMD Hemophilia A and HUWE1. We recorded the typical age of onset from early childhood in Cystic Fibrosis and DMD to adulthood in other conditions. We described the major clinical features including pulmonary and pancreatic manifestations in Cystic Fibrosis, progressive muscle weakness in DMD, cancer risks in BRCA1, bleeding tendencies in Hemophilia A, muscle stiffness in myotonia, and developmental delay with distinctive facial features in intellectual disability. We also noted disease progression, complications, and any genotype-phenotype correlations that have been established in the medical literature.

Step 4 — UCSC Genome Browser Analysis

Using genomic coordinates obtained from each ClinVar variant page we accessed the UCSC Genome Browser at genome.ucsc.edu with the GRCh38 human genome assembly. For Hemophilia A we used coordinates chrX:154,930,844-154,930,845. For Congenital Myotonia we used chr7:143,320,700-143,320,730. For HUWE1 we used chrX:53,535,474. For each variant we navigated to the specific chromosomal region containing the mutation and then added the AlphaMissense and RAVEL pathogenicity prediction tracks by accessing the Track Hubs feature and searching for these specific tracks in the Public Hubs section. AlphaMissense is a deep learning tool from Google DeepMind that predicts the pathogenicity of missense variants with scores ranging from zero to one where scores above 0.564 indicate likely pathogenic variants shown in red. After adding both tracks we zoomed in until individual base pairs were visible at the top of the display as required to see the actual scores and then captured screenshots of each track for every variant showing the colored bars representing pathogenicity predictions.

Step 5 — ACMG AMP Classification

We applied the American College of Medical Genetics and Genomics and Association for Molecular Pathology guidelines to classify each variant based on evidence. The ACMG framework uses evidence codes with different strength levels including PVS1 for very strong evidence such as null variants in genes where loss of function is the disease mechanism, PS1 and PS3 and PS4 for strong evidence including same amino acid change as established pathogenic variants, functional studies, and prevalence in affected populations. Moderate evidence codes like PM2 for absence from population databases and PM3 for finding variants in trans with other pathogenic variants were applied where appropriate. Supporting evidence codes such as PP1 for co-segregation with disease in families and PP3 for computational predictions were also used. For CFTR we applied PVS1, PS1, PS3, PS4, PM2, PM3, PP1, and PP3 leading to a pathogenic classification. For BRCA1 we applied PVS1, PS1, PS4, PM2, PP1, and PP3 also resulting in pathogenic. For DMD we applied PVS1, PS1, PM2, PP3, and PP5 for pathogenic. For Hemophilia A we applied similar criteria resulting in pathogenic. For the CLCN1 variant we noted that it is classified as benign despite the disease being rare. For HUWE1 we applied PS1, PS3, PS4, PM2, PP1, and PP3 resulting in pathogenic classification.

Step 6 — VCF File Creation

We created a Variant Call Format file simulating patient data from whole genome or whole exome sequencing. The VCF file includes standard header lines with meta-information such as file format version VCFv4.3, file date, reference genome GRCh38, and contig definitions for chromosomes seven, seventeen, and X. The header line defines ten columns including chromosome, position, variant ID, reference allele, alternate allele, quality score, filter status, information field, format field, and patient genotype. For each of the six variants we added a data line with the appropriate chromosome, position, variant ID, reference and alternate alleles, quality score of 250 indicating high confidence, PASS filter status, information field containing clinical significance and disease name, genotype format, and patient genotype. For Cystic Fibrosis we used homozygous alternate genotype 1/1. For BRCA1 and the rare diseases we used heterozygous genotypes 0/1 for autosomal conditions and 1/0 for X-linked conditions in males.

Step 7 — ClinVar Annotation

We annotated our VCF file to verify that all variants are correctly identified in official databases. For variants with rs numbers we used NCBI Batch Entrez at ncbi.nlm.nih.gov slash sites slash batchentrez selecting the SNP database and uploading a text file containing all variant identifiers. The system successfully retrieved records for rs113993960 confirming it as CFTR pathogenic with inframe deletion, rs80359874 confirming it as BRCA1 pathogenic with frameshift, rs387906447 confirming it as F8 pathogenic with duplication, rs10282312 confirming it as CLCN1 benign with missense, and rs121918527 confirming it as HUWE1 pathogenic with missense. For the DMD variant which uses a ClinVar variation ID rather than an rs number we performed a direct search in the ClinVar database using the identifier 3718685 which confirmed the variant as pathogenic for Duchenne Muscular Dystrophy with frameshift consequence. All six variants were successfully verified with their clinical significance confirmed in NCBI databases.

Prerequisites
Compute environment

This analysis was performed on a standard computer with internet access for database queries.

Storage: 1 GB free for files and screenshots

Internet: Required for accessing ClinVar, OMIM, UCSC, and NCBI databases

Software dependencies

Web browser (Chrome, Firefox, or Safari)

Microsoft Excel or compatible spreadsheet software

Text editor such as Notepad for creating VCF files

GitHub account for repository hosting

Databases accessed

All data was obtained from publicly available online resources:

ClinVar at ncbi.nlm.nih.gov slash clinvar

OMIM at omim.org

UCSC Genome Browser at genome.ucsc.edu

NCBI Batch Entrez at ncbi.nlm.nih.gov slash sites slash batchentrez

PubMed at pubmed.ncbi.nlm.nih.gov

Installation
Step 1 — Clone the repository

git clone https://github.com/eklhmah123/genetic-disorders-analysis.git

cd genetic-disorders-analysis

Step 2 — Download reference resources

Reference genome GRCh38 information was accessed through UCSC Genome Browser. Coordinates for each variant were obtained directly from ClinVar variant pages.

Step 3 — Prepare workspace

Create folders for organizing files:

mkdir -p data screenshots annotation_results

Usage
Running the Full Analysis

1) ClinVar Data Extraction

For each disease, navigate to ClinVar at ncbi.nlm.nih.gov slash clinvar and search by disease name or gene symbol. Select one pathogenic variant per disease and extract the following information into Excel: gene symbol, variant ID, nucleotide change, protein change, clinical significance, review status, and number of submissions.

2) Literature Review

On each ClinVar variant page, follow PubMed links to access scientific publications. Read abstracts and key papers to understand the functional consequences, population genetics, and clinical observations for each variant. Summarize findings in paragraph form for the Explanation field.

3) OMIM Phenotype Analysis

Navigate to OMIM at omim.org and search by disease name or OMIM ID. For each condition, document inheritance pattern, age of onset, major clinical features, disease progression, and any genotype-phenotype correlations. Write this information in the Phenotype field.

4) UCSC Screenshot Capture

For each variant, obtain genomic coordinates from the ClinVar variant page. Go to UCSC Genome Browser at genome.ucsc.edu, select Human GRCh38 assembly, enter the coordinates, and click GO. Add AlphaMissense and RAVEL tracks via Track Hubs and Public Hubs. Zoom in until individual base pairs are visible and take screenshots. Insert screenshots into Excel columns L and M.

5) ACMG Classification

Apply ACMG AMP guidelines to each variant by evaluating evidence codes including PVS1, PS1, PS3, PS4, PM2, PM3, PP1, PP3, and PP5. Document which codes apply and record the final classification in Column K.

6) VCF File Creation

Open a text editor and create a VCF file with proper header lines including file format, date, reference, and contig definitions. Add column headers with tabs between each column. Add data lines for all six variants with chromosome, position, ID, reference allele, alternate allele, quality score, filter, INFO field, FORMAT, and patient genotype. Save the file with .vcf extension.

7) Variant Annotation

For rs-number variants, go to NCBI Batch Entrez at ncbi.nlm.nih.gov slash sites slash batchentrez, select SNP database, upload a text file with all variant IDs, and click Retrieve. For the DMD variant 3718685, search directly in ClinVar. Save all results and take screenshots of confirmation pages.

Results
Top performer: All five pathogenic variants were confirmed as disease-causing with strong evidence from multiple sources. The CLCN1 variant was correctly identified as benign demonstrating that not every variant in a disease gene is pathogenic.

Alignment Statistics

Not applicable for this analysis as we worked with variant data rather than raw sequencing reads.

Variant Totals

Total variants analyzed: 6

Pathogenic variants: 5

Benign variants: 1

Variants with expert panel review: 3

Variants with multiple submissions: 4
