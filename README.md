# Polygenic Risk Score (PRS) Analysis

## Project Overview
This repository contains code for a Polygenic Risk Score (PRS) analysis project, focusing on breast cancer susceptibility in East Asian populations. 

## Prerequisites
The following tools are required for this project:
- bcftools
- tabix
- plink2
- snpEff
- Python libraries:
  - pandas
  - scipy
  - seaborn
  - matplotlib

## Data Sources
- **Genetic Data**: 1000 Genomes Project Phase 3 VCF files (GRCh38)
- **PGS Summary Statistics**: PGS Catalog (PGS003758)
- **Disease of Interest**: Breast Cancer
- **Population of Interest**: East Asians (EAS)
  - Beijing Han Chinese (CHB)
  - Southern Han Chinese (CHS)
  - Kinh Vietnamese (KHV)
  - Japanese (JPT)
  - Dai Chinese (CDX)

## Workflow

### 1. Data Exploration
- Identified and accessed 1000 Genomes Project VCF files
- Determined sample and variant counts
- Extracted East Asian samples (504) from the global population
- Created population-specific VCF files for all 22 chromosomes

### 2. Variant Annotation
- Identified clinically relevant genes for East Asians
- Selected the GJB2 gene for detailed analysis
- Created a gene-specific VCF file for East Asian samples
- Annotated variants using snpEff to identify variants with HIGH or MODERATE consequences
- Identified 41 variants with significant impact

### 3. PGS Selection
- Selected a breast cancer polygenic score from PGS Catalog (PGS003758)
- Verified the score was developed using East Asian populations
- Training size: 2254 samples (100% East Asian)
- Testing size: 8001 samples

### 4. PRS Calculation
- Harmonized variant IDs between the VCF files and PGS summary statistics
- Found 4997 overlapping variants (0.0064% of total variants)
- Calculated PRS for all East Asian individuals using plink2
- Scaled scores using z-score normalization
- Visualized distribution of scores across East Asian sub-populations

## Results
The analysis resulted in:
- Population-specific VCF files for East Asians
- Identification of clinically significant variants in the GJB2 gene
- PRS scores for breast cancer susceptibility across East Asian sub-populations
- Visualization showing the distribution of risk scores by population 
![Untitled](https://github.com/user-attachments/assets/0917969b-07d2-40ef-b5c0-d19838c906fa)

## Acknowledgements
This project was developed as part of the BIOL 6150 course. Special thanks to the course instructors, the PACE-ICE HPC support team for their guidance and resources, and my team members Anagha Mohana Krishna and Hina Gaur.
