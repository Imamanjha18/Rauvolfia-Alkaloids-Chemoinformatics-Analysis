# Rauvolfia-Alkaloids-Chemoinformatics-Analysis

This repository presents a complete chemoinformatics workflow to analyze alkaloids from Rauvolfia serpentina, focusing on drug-likeness, chemical space diversity, and predicted biological targets using multiple validated databases and computational tools.

## Overview

Rauvolfia serpentina is a medicinal plant rich in alkaloids with well-documented pharmacological effects, particularly in neurological and cardiovascular systems.



This project integrates multiple bioinformatics and chemoinformatics approaches to:

1. Identify and curate phytochemicals
2. Validate compounds across databases
3. Classify alkaloids based on chemical taxonomy
4. Evaluate drug-likeness properties
5. Analyze chemical diversity using PCA
6. Predict biological targets

## Workflow Pipeline

1. IMPPAT / NPASS Databases
2. CMAUP Validation
3. Phytochemical Collection
4. Data Curation \& Deduplication
5. ClassyFire Classification
6. Drug-likeness Screening (SwissADME)
7. PCA Analysis (ClustVis)
8. Compound Selection (PCA-based)
9. Target Prediction (SwissTargetPrediction)

## Dataset Used

### Source Databases

1. IMPPAT – Indian Medicinal Plants, Phytochemistry And Therapeutics
2. NPASS – Natural Product Activity & Species Source Database
3. CMAUP – Collective Molecular Activities of Useful Plants

### Organism

Rauvolfia serpentina

### Dataset Summary

|Step|Output|
|-|-|
|Total compounds collected |285|
|Unique compounds after curation |121|
|Alkaloid selected|67|
|Final compounds for analysis |12|

## Tools & Resources
1. SwissADME – Drug-likeness prediction (https://www.swissadme.ch/)
2. ClustVis – PCA & heatmap visualization (https://biit.cs.ut.ee/clustvis/)
3. SwissTargetPrediction – Target prediction (https://www.swisstargetprediction.ch/) 
4. PubChem – Chemical data retrieval (https://pubchem.ncbi.nlm.nih.gov/)
5. ClassyFire – Chemical classification (http://classyfire.wishartlab.com/)


## Methodology

### 1\. Phytochemical Collection 

Phytochemicals of Rauvolfia serpentina were retrieved from IMPPAT and NPASS databases.

### 2\. Data Curation

- Removed duplicate entries
- Filtered compounds lacking PubChem ID or valid identifiers
- Verified SMILES structures
- Removed invalid or merged entries (e.g., mixture containing synthetic drug component)


Final curated dataset: 121 compounds

### 3\. CMAUP Croos-validation

Tool used: CMAUP;

- Queried Rauvolfia serpentina
- Retrieved associated compounds and known targets
- Compared results with curated dataset

Result:

- Confirmed consistency of phytochemical dataset
- No additional unique compounds identified
- Used as validation layer rather than primary data source


### 4\. Hub Gene Identification

Tool used: Cytoscape (cytoHubba);
Method: Degree centrality

Tol 10 Hub genes: EZH2, CCNB1, RAD51, BUB1B, NUF2, UHRF1, KIF2C, HDAC1, ASPM, ESPL1

### 5\. Module Detection

Tool used: Cytoscape (MCODE);

top MCODE cluster (functional module):
Score - 10.6;
Nodes - 11;
Edges - 53 (highly interconnected)

Genes: NUF2, EZH2, HMMR, ESPL1, SKA3, UHRF1, CCNB1, BUB1B, RAD51, ASPM, KIF2C

### 6\. Final Key Genes

Genes were finalized from the intersection of Hub genes (cytoHubba) and top MCODE cluster: EZH2, CCNB1, RAD51, BUB1B, NUF2, UHRF1, KIF2C, ASPM, ESPL1

### 7\. Regulatory Network Analysis

Tool used: NetworkAnalyst

1. Transcription Factors (TFs):
ELF1, KDM5A, KLF9, KLF1, POLR2A, IRF1, ZNF175, ZNF263
2. miRNAs:
hsa-miR-193b-3p, hsa-let-7a-5p, hsa-let-7b-5p, hsa-miR-192-5p, hsa-miR-215-5p, hsa-miR-124-3p, hsa-miR-25-3p, hsa-miR-92a-3p

### 8\. Drug Enrichment Analysis

Tool used: Enrichr (DSigDB(Drug SIGnatures DataBase))

Top candidate drugs: LUCANTHONE, Phytoestrogens, Troglitazone, Etoposide, Enterolactone, Calcitriol, Resveratrol

## Key Findings

Core genes are mainly involved in:

1. Cell cycle regulation
2. DNA repair
3. Epigenetic modification

Regulatory network reveals: Multi-layer gene control (TF + miRNA)

Drug enrichment suggests: Potential therapeutic candidates targeting key pathways

## Results Summary

|Step|Output|
|-|-|
|DEGs|16605|
|Common Genes|124|
|Hub Genes|10|
|Final Key Genes|9|
|TFs Identified|8|
|miRNAs Identified|8|

## Future Work

1. Experimental validation (qPCR, Western blot)
2. Survival analysis
3. Molecular docking and MD simulations
4. Clinical validation

## 👨‍🔬 Author

Aman Jha

MSc Bioinformatics

## If you find this useful

Give this repository a ⭐ and feel free to fork!

