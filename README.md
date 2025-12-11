# The Global Parkinson’s Disease Genetics (GP2) Genome Browser

`GP2 ❤️ Open Science 😍`

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)


**Last Updated:** December 2025

---

## Summary

This repository accompanies the brief report **“The Global Parkinson’s Disease Genetics (GP2) Genome Browser.”** 

The GP2 Genome Browser is an open-access platform that provides gene- and variant-level information from one of the largest ancestry-diverse sequencing datasets assembled for Parkinson’s disease (PD) research.

The browser integrates:

- **31,665 whole-genome sequences (WGS)**  
- **9,559 clinical exomes (CES)**  
- **11 genetically determined ancestries**

using a unified joint-calling, QC, and annotation pipeline (DeepVariant → GLnexus → GenoTools → VEP). It enables:

- Gene-level pages with annotations, resources, and constraint metrics  
- Variant-level pages showing functional consequence, allele frequencies, ClinVar, dbSNP, and CADD  
- Frequency tables stratified by **ancestry** and **phenotype** (Case / Control / Other)

The GP2 Genome Browser is openly available at:  
**https://gp2.broadinstitute.org**

This repository contains the script used to produce the browser-ready Hail tables and frequency outputs used in the manuscript.

---

## Citation

If you use this repository or find it helpful, please cite:

> **Fang Z-H., Grant R.H., Vitale D., Hernandez C.F., Hong S., Leonard H.L., Makarious M.B., Lange L.M., Solomonson M., Heutink P., Dilliott A., Ghosh Galvelis K., Nalls M.A., Singleton A.B., Blauwendraat C., and the Global Parkinson’s Genetics Program (GP2).**  
> *The Global Parkinson’s Disease Genetics (GP2) Genome Browser* (2025).  
>  
> **Manuscript DOI:** coming soon  
> **GitHub DOI:** xx

---

## Data Statement

- **GP2 WGS Data**  
  - GP2 Release 10 (WGS): DOI **10.5281/zenodo.15748014**  
  - Accessible via AMP-PD: https://amp-pd.org  

- **GP2 CES Data**  
  - GP2 Release 8 (PDGENEration CES): DOI **10.5281/zenodo.13755496**

- **Additional Controls**  
  - Alzheimer’s Disease Sequencing Project (ADSP) WGS: DOI **10.60859/z6z9-9692**, accessed via NIAGADS  

- **Variant Processing Pipeline**  
  - Single-sample calling: **DeepVariant v1.6.1**  
  - Joint-genotyping: **GLnexus v1.4.3**  
  - Quality control: genotype-, sample-, and variant-level filters from AMP-PD & GP2  
  - Genetic ancestry assignment: **GenoTools v1.2.3**  
  - Annotation: **Ensembl VEP v111** (adds ClinVar, CADD, dbSNP, functional consequence)  
  - Intergenic variants excluded from browser display  
  - Allele frequencies computed by **genetic ancestry** and **phenotype**

---

## Helpful Links

- **GP2 Website:** https://gp2.org  
  - GP2 Cohort Dashboard: https://gp2.org/cohort-dashboard-advanced  
- **AMP-PD:** https://amp-pd.org  
- **PDGENEration:** https://www.parkinson.org/PDGENEration  
- **ADSP / NIAGADS:** https://www.niagads.org  
- **GP2 Overview:** https://movementdisorders.onlinelibrary.wiley.com/doi/10.1002/mds.28494  
- **GP2 Manuscripts:**  
  https://pubmed.ncbi.nlm.nih.gov/?term=%22global+parkinson%27s+genetics+program%22

---

# Repository Orientation

```
├── LICENSE.txt
├── README.md
└── analyses/
    └── gp2_genome_browser_hail_table.ipynb
```


---

## Analysis Notebook

**Languages:** Python (Hail), and bash

**Description:**  
This notebook performs all steps needed to generate the tables consumed by the GP2 Genome Browser, including:

- Importing GP2, AMP-PD, and ADSP Hail tables  
- Applying genotype-, sample-, and variant-level QC  
- Merging WGS and CES high-quality datasets  
- Annotating variants with VEP, ClinVar, dbSNP, and CADD  
- Assigning genetic ancestry groups (via precomputed metadata)  
- Calculating allele frequencies stratified by ancestry & phenotype  
- Exporting browser-ready tables for *gene* and *variant* pages  


---

# Software

| Software | Version | URL | RRID | Notes |
|---------|---------|-----|------|-------|
| **Python** | 3.9 / 3.10 | http://python.org | RRID:SCR_008394 | Main analysis environment |
| **R** | 4.2 | http://www.r-project.org | RRID:SCR_001905 | Used for summary figures |
| **Hail** | 0.2.x | https://hail.is | — | Variant processing, QC, tables |
| **DeepVariant** | 1.6.1 | https://github.com/google/deepvariant | — | Single-sample variant calling |
| **GLnexus** | 1.4.3 | https://github.com/dnanexus-rnd/GLnexus | — | Joint-genotyping (DV-WGS / DV-WES presets) |
| **GenoTools** | 1.2.3 | https://github.com/GP2code/GenoTools | — | Genetic ancestry assignment |
| **VEP** | v111 | https://ensembl.org/info/docs/tools/vep/ | RRID:SCR_007931 | Variant consequence + annotation |
| **KING** | 2.3.0 | https://kingrelatedness.com | RRID:SCR_009251 | Relatedness inference |


---

# Data & Code Availability

- GP2 and AMP-PD datasets are available through application via **AMP-PD** (https://amp-pd.org).  
- ADSP data are available via **NIAGADS** (NG00067; DOI: 10.60859/z6z9-9692).  
- Code in this repository reproduces browser-ready data tables and manuscript figures.  
- A permanent Zenodo archive of this repository will be linked via the DOI badge above.

---

