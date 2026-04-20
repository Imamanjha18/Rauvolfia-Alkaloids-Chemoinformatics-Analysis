# Rauvolfia-Alkaloids-Chemoinformatics-Analysis

This repository presents a comprehensive chemoinformatics workflow to analyze alkaloids from Rauvolfia serpentina, focusing on compound curation, chemical classification, drug-likeness evaluation, chemical space exploration, and target prediction using validated public databases and computational tools.
  
## Overview

Rauvolfia serpentina is a well-known medicinal plant rich in bioactive alkaloids, particularly associated with neurological and cardiovascular pharmacology (e.g., reserpine-like compounds).
 
  
This project integrates bioinformatics and chemoinformatics approaches to:
  
1. Identify and curate phytochemicals from multiple databases
2. Validate compounds across independent resources
3. Classify compounds based on chemical taxonomy
4. Evaluate drug-likeness and pharmacokinetic properties
5. Explore chemical space using PCA
6. Select structurally diverse representative compounds
7. Predict potential biological targets
8. Construct and analyze compound–target interaction networks
  
## Workflow Pipeline
  
- IMPPAT / NPASS Data Retrieval
- CMAUP Cross-validation
- Phytochemical Collection
- Data Curation & Deduplication
- Chemical Classification (ClassyFire)
- Drug-likeness Screening (SwissADME)
- PCA Analysis (ClustVis)
- Representative Compound Selection
- Target Prediction (SwissTargetPrediction)
- Network Construction & Analysis (Cytoscape)
  
## Dataset Used
  
### Source Databases
  
1. IMPPAT – Indian Medicinal Plants, Phytochemistry And Therapeutics (https://cb.imsc.res.in/imppat/)
2. NPASS – Natural Product Activity & Species Source Database (https://bidd.group/NPASS/)
3. CMAUP – Collective Molecular Activities of Useful Plants (https://bidd.group/CMAUP/)
  
  
### Organism
Rauvolfia serpentina
  
### Dataset Summary
  
  |Step|Output|
  |-|-|
  |Total compounds collected |285|
  |Unique compounds after curation |121|
  |Alkaloid selected|67|
  |Final compounds for analysis |11|
  
## Tools & Resources
1. SwissADME – Drug-likeness prediction (https://www.swissadme.ch/)
2. ClustVis – PCA & heatmap visualization (https://biit.cs.ut.ee/clustvis/)
3. SwissTargetPrediction – Target prediction (https://www.swisstargetprediction.ch/) 
4. PubChem – Chemical data retrieval (https://pubchem.ncbi.nlm.nih.gov/)
5. ClassyFire – Chemical classification (http://classyfire.wishartlab.com/)
6. Cytoscape - Network construction and visualization (https://cytoscape.org/) 
  
  
## Methodology
  
### 1\. Phytochemical Collection 
  
Phytochemicals of Rauvolfia serpentina were retrieved from IMPPAT and NPASS databases.
  
### 2\. Data Curation
  
- Removed duplicate entries
- Excluded compounds lacking PubChem IDs or valid identifiers
- Verified and standardized SMILES structures
- Removed invalid or merged entries (e.g., synthetic mixtures)
  
 
Final curated dataset: 121 compounds
  
### 3\. CMAUP Cross-validation
  
Tool used: CMAUP;
  
- Queried Rauvolfia serpentina
- Retrieved associated compounds and targets
- Compared with curated dataset
  
Result:
  
- Dataset consistency confirmed
- No additional unique compounds identified
- Used as a validation layer, not a primary source
  
  
### 4\. Alkaloid Classification
  
Tool used: ClassyFire
  
- Compounds classified based on chemical taxonomy
- Selected compounds with superclass: Alkaloids and derivatives
  
Final selection: 67 alkaloids
  
### 5\. Drug-likeness Analysis
  
Tool used: SwissADME

Parameters evaluated:
  
- Molecular Weight (MW)
- LogP
- Topological Polar Surface Area (TPSA)
- Lipinski’s Rule of Five
- GI Absorption
  
Result:
  
- Majority of compounds satisfied Lipinski’s criteria
- Only 10 compounds showed violations
  
### 6\. Chemical Space Analysis
  
Tool used: ClustVis
  
- PCA performed using key physicochemical descriptors
- PC1 (~64%) and PC2 (~27%) explained ~90% variance
- Observations:
[I] Dense main cluster (structural similarity)
[II] Secondary cluster (moderate variation)
[III] Distinct outliers (high chemical diversity)
 
### 7\. Representative Compound Selection
  
Selection based on PCA distribution:
  
- Main cluster compounds (representative structures)
- Secondary cluster compounds (moderate diversity)
- Outliers (extreme chemical diversity)
  
Final selected compounds:
  
RS_02, RS_04, RS_05, RS_13, RS_14, RS_18,
RS_24, RS_44, RS_54, RS_40, RS_65


### 8\. Target Prediction

Tool used: SwissTargetPrediction

- SMILES of selected compounds used as input
- Top predicted human targets retrieved
- Targets categorized by protein class


### 9\. Network Consruction and Analysis

Tool used: Cytoscape

- Constructed compound–target interaction network
- Nodes represent compounds and protein targets
- Edges represent predicted interactions

Node classification based on degree centrality:

- High connectivity (≥6) → Hub targets
- Moderate connectivity (4–5) → Secondary targets
- Low connectivity (≤2) → Peripheral targets

  
## Key Findings

1. Hub proteins: DRD2, OPRM1, HTR2A
2. Network dominated by G protein-coupled receptors (GPCRs)
3. Secondary roles observed for transporters and metabolic enzymes (e.g., ABCB1, CYP2D6)

## Results Summary

|Step|Output|
|-|-|
|Curated compounds|121|
|Alkaloid Selected|67|
|Final compounds |11|
|Major hub targets |DRD2, OPRM1, HTR2A|
|Dominant target class |GPCR|

## Key Insights

1. Alkaloids from Rauvolfia serpentina show strong enrichment toward GPCR targets
2. Chemical space analysis reveals both conserved and diverse structural regions
3. Selected compounds capture maximum diversity for downstream studies
4. Network analysis highlights key neuropharmacological targets

## Future Work 
- Molecular docking studies of selected compounds
- Molecular dynamics simulations
- KEGG pathway enrichment analysis
- Experimental validation (in vitro / in vivo)

## 👨‍🔬 Author

Aman Jha

MSc Bioinformatics

## If you find this useful

Give this repository a ⭐ and feel free to fork!


If you find any errors, missing information, or have suggestions for improvement, feel free to open an issue or contact me.

