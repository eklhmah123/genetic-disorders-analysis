Genetic Disorders and Rare Diseases Variant Analysis
group members : AQBA EJAZ,HAFSAH BATOOL ,NAGINA NAVEED
Date: February 23, 2025
Course: [SPECIAL TOPICS IN BIOINFORMATICS]
Institution: [NUST]
Submission For: Bioinformatics Assignment - Genetic Disorders Analysis
 EXECUTIVE SUMMARY
This report presents a comprehensive analysis of three genetic disorders: Cystic Fibrosis (CFTR gene), Hereditary Breast and Ovarian Cancer (BRCA1 gene), and Duchenne Muscular Dystrophy (DMD gene). For each disorder, one clinically relevant pathogenic variant was selected from the ClinVar database. The analysis included detailed variant characterization, literature review, phenotype analysis using OMIM, pathogenicity prediction using UCSC Genome Browser (AlphaMissense and RAVEL tracks), ACMG/AMP classification, VCF file creation, and ClinVar annotation. All three variants were confirmed as Pathogenic according to ACMG/AMP guidelines and validated through NCBI Batch Entrez and direct ClinVar search. All data, screenshots, and files have been organized in a GitHub repository for reproducibility.
2.0 INTRODUCTION
2.1 Objective
The objective of this assignment was to:

Select three genetic disorders and identify one most relevant variant per disorder from ClinVar

Extract detailed variant information into an Excel sheet

Research studies about each variant and provide explanations

Obtain phenotype information from OMIM database

Capture AlphaMissense and RAVEL pathogenicity scores from UCSC Genome Browser

Apply ACMG/AMP guidelines to classify each variant

Create a VCF file simulating patient data

Annotate the VCF file using ClinVar

Create a GitHub repository with complete documentation

Tools and Databases Used
Tool/Database	Purpose	Website
1 ClinVar	Variant selection and clinical significance	https:
2 PubMed	Literature review for Explanation field	
3 OMIM	Phenotype information	
4 UCSC Genome Browser	AlphaMissense & RAVEL pathogenicity scores	
5 ACMG/AMP Guidelines	Variant classification	
6 NCBI Batch Entrez	VCF annotation 
7 Microsoft Excel	Data organization	Microsoft Office
8 Notepad	VCF file creation	Built into Windows

3. SELECTED DISORDERS AND VARIANTS
Three genetic disorders were selected for this analysis based on their well-characterized genetic basis, availability of extensive research, and representation of different inheritance patterns. The first disorder selected was Cystic Fibrosis, which is caused by mutations in the CFTR gene and follows an autosomal recessive inheritance pattern. The second disorder selected was Hereditary Breast and Ovarian Cancer, caused by mutations in the BRCA1 gene with autosomal dominant inheritance. The third disorder selected was Duchenne Muscular Dystrophy, caused by mutations in the DMD gene with X-linked recessive inheritance.

For Cystic Fibrosis, the variant selected was rs113993960, which corresponds to the CFTR p.Phe508del mutation. This variant involves a 3-base pair deletion resulting in the loss of phenylalanine at position 508 of the CFTR protein. This variant was selected because it is the most common cause of cystic fibrosis worldwide, accounting for approximately seventy percent of CF alleles in Caucasian populations, and it has been extensively studied with multiple submissions in ClinVar.

For Hereditary Breast and Ovarian Cancer, the variant selected was rs80359874, which corresponds to the BRCA1 p.Leu392fs mutation. This variant involves a 40-base pair deletion causing a frameshift and premature stop codon, resulting in a truncated non-functional protein. This variant was selected because it has been reviewed by the ENIGMA expert panel, has multiple submissions in ClinVar, and is well-characterized in the literature.

For Duchenne Muscular Dystrophy, the variant selected was 3718685, which corresponds to the DMD c.10478del p.Gln3493fs mutation. This variant involves a single nucleotide deletion causing a frameshift and premature stop signal, resulting in absent dystrophin protein. This variant was selected because it represents a typical loss-of-function variant in DMD, has a recent ClinVar submission, and demonstrates clear pathogenicity.

All three selected variants are classified as Pathogenic in ClinVar, making them excellent candidates for this comprehensive analysis.

3. CLINVAR ANALYSIS
ClinVar is NCBI's database of human genetic variants and their relationship to disease.

For CFTR rs113993960: This variant is NM_000492.4(CFTR):c.1521_1523del (p.Phe508del). It is Pathogenic with ★★★★☆ review status from expert panel. There are 50+ submissions from multiple labs. Associated conditions include Cystic fibrosis, Bronchiectasis, and Hereditary pancreatitis.

For BRCA1 rs80359874: This variant is NM_007294.4(BRCA1):c.1175_1214del (p.Leu392fs). It is Pathogenic with ★★★★☆ review status from ENIGMA expert panel. There are 11+ submissions. The primary condition is Hereditary breast ovarian cancer syndrome.

For DMD 3718685: This variant is NM_004006.3(DMD):c.10478del (p.Gln3493fs). It is Pathogenic with ★★★★☆ review status from single submitter (Labcorp Genetics). Last evaluated December 2024. Condition is Duchenne muscular dystrophy.

4. LITERATURE REVIEW - EXPLANATION FIELD
CFTR p.Phe508del: Discovered in 1989, this is the most common CF variant (70% of Caucasian CF alleles). The 3bp deletion causes protein misfolding and degradation before reaching cell membrane. Functional studies show the mutant protein retains partial function if rescued. Population studies show allele frequency 0.66-0.82 in CF patients. Homozygotes have severe CF with pancreatic insufficiency. CFTR modulators (ivacaftor/lumacaftor) partially correct the defect.

BRCA1 p.Leu392fs: This 40bp deletion causes frameshift leading to truncated non-functional protein. Loss of BRCA1 function disrupts DNA repair via homologous recombination. Lifetime cancer risks: breast cancer 50-85%, ovarian cancer 20-50%. ENIGMA expert panel confirms pathogenicity. Extremely rare in population databases (MAF <0.00001).

DMD c.10478del: Single nucleotide deletion causing frameshift and premature stop codon (p.Gln3493fs). Results in absent dystrophin protein. Loss-of-function variants in DMD are well-established as pathogenic (PMID: 16770791, 25007885). Absent from population databases (gnomAD). X-linked recessive inheritance.

5. OMIM PHENOTYPE INFORMATION
Cystic Fibrosis (#219700): Autosomal recessive disorder characterized by chronic lung disease, pancreatic insufficiency, and elevated sweat chloride (>60 mmol/L). Onset in childhood. Pulmonary manifestations include chronic infections, bronchiectasis. GI features include meconium ileus (10-15%), pancreatic insufficiency (85%). Nearly all males infertile due to CBAVD.

Hereditary Breast Cancer (#604370): Autosomal dominant cancer predisposition. Lifetime breast cancer risk 57-82%, ovarian cancer 20-50%. Breast cancers often triple-negative, early-onset (<50 years). Male carriers have increased prostate cancer risk. Incomplete penetrance.

Duchenne MD (#310200): X-linked recessive, affects 1 in 3,500 males. Onset before age 6 with proximal muscle weakness, Gower's sign. Wheelchair by age 12. Cardiomyopathy by age 18. Death by age 20-30 from respiratory failure or cardiomyopathy.

6. UCSC GENOME BROWSER ANALYSIS
Coordinates used (GRCh38/hg38):

CFTR: chr7:117,559,591-117,559,593

BRCA1: chr17:43,094,317-43,094,356

DMD: chrX:31,169,500-31,169,530

AlphaMissense Track: Deep learning tool predicting missense variant pathogenicity. Scores range 0-1. ≥0.564 = Likely Pathogenic (red), 0.340-0.564 = Likely Neutral (yellow), ≤0.340 = Likely Benign (green). Four subtracks for A, C, G, T nucleotide changes.

RAVEL Track: Variant effect predictor supporting pathogenicity assessment.

Method: Added tracks via Track Hubs → Public Hubs. Set display to "full" with track height 50 pixels. Took screenshots for each variant.

7. ACMG/AMP CLASSIFICATION
ACMG Evidence Codes Used:

PVS1: Null variant in gene where LOF is mechanism (Very Strong)

PS1: Same amino acid change as established pathogenic (Strong)

PS3: Functional studies support damaging effect (Strong)

PS4: Prevalence in affected >> controls (Strong)

PM2: Absent from population databases (Moderate)

PM3: Found in trans with pathogenic variants (Moderate)

PP1: Co-segregation with disease (Supporting)

PP3: Computational evidence supports deleterious (Supporting)

PP5: Reputable source reports pathogenic (Supporting)

CFTR p.Phe508del: PVS1 + PS1 + PS3 + PS4 + PM2 + PM3 + PP1 + PP3 = PATHOGENIC

BRCA1 p.Leu392fs: PVS1 + PS1 + PS4 + PM2 + PP1 + PP3 = PATHOGENIC

DMD c.10478del: PVS1 + PS1 + PM2 + PP3 + PP5 = PATHOGENIC

8. VCF FILE CREATION
VCF (Variant Call Format) is a standardized text file for storing genetic variants.

##fileformat=VCFv4.3
##fileDate=20250223
##source=ClinVar_annotation
##reference=GRCh38
##contig=<ID=chr7,length=159345973>
##contig=<ID=chr17,length=83257441>
##contig=<ID=chrX,length=156040895>
##INFO=<ID=CLNSIG,Number=.,Type=String,Description="Clinical significance">
##INFO=<ID=CLNDN,Number=.,Type=String,Description="Disease name">
##FORMAT=<ID=GT,Number=1,Type=String,Description="Genotype">           
#CHROM  	POS	      ID	     REF	                                       ALT	  QUAL	    FILTER	INFO	                                               FORMAT	       PATIENT_01
chr7	        117559591     rs113993960    CTT	                                       C	  250	     PASS       CLNSIG=Pathogenic;CLNDN=Cystic_fibrosis	               GT	         1/1
chr17	        43094317      rs80359874     GATTCAGACTCCCCTCATGATGATGCATCAGAACCTAACAG	       G	  250	     PASS	CLNSIG=Pathogenic;CLNDN=Hereditary_breast_cancer       GT                0/1
chrX	        31169518	.	     T	                                               .	  250	     PASS	CLNSIG=Pathogenic;CLNDN=Duchenne_muscular_dystrophy    GT	         1/0
Genotype meanings: 1/1 = homozygous alternate, 0/1 = heterozygous, 1/0 = hemizygous (X chromosome).
9. CLINVAR ANNOTATION
Two methods were used for annotation due to technical issues with Variation Reporter.

For CFTR and BRCA1 (rs numbers): Used NCBI Batch Entrez with SNP database.

rs113993960 confirmed as CFTR, Pathogenic, inframe_deletion, MAF T=0.003121

rs80359874 confirmed as BRCA1, Pathogenic, frameshift_variant, MAF <0.00001

For DMD (3718685): Direct ClinVar search confirmed variant as NM_004006.3(DMD):c.10478del (p.Gln3493fs), Pathogenic, reviewed by Labcorp Genetics, last evaluated December 2024.

All three variants confirmed Pathogenic in NCBI databases.
RESULT :All three variants are Pathogenic according to ACMG/AMP guidelines and confirmed in ClinVar.


