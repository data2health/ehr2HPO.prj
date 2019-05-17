# HPO 2 EHR

## Problem statement

Electronic health records (EHRs) contain rich phenotype information that can be utilized to stratify diseases and to develop hypotheses. Despite the great potential of EHR data, patient phenotyping from EHRs is still challenging because the phenotype information is distributed in many EHR locations (laboratories, notes, problem lists, imaging data, etc.) and since EHRs have vastly different structures across sites. This lack of integration represents a substantial barrier to widespread use of EHR data in translational research. In the first phase of this project, we developed a method for mapping LOINC-encoded laboratory test results transmitted in FHIR standards to Human Phenotype Ontology (HPO) terms ([Zhang et al. (2019) npj Digital Medicine 2:3](https://www.nature.com/articles/s41746-019-0110-4)). In the current phase of the project, we will use the software to search for biomarkers in EHR data of participating CTSA centers. In future work, we will extend the resource to additional phenotype sources in the EHR.

## Project description

The [Human Phenotype Ontology](http://www.human-phenotype-ontology.org) (HPO) is a freely available and open source logically defined vocabulary for describing human abnormal phenotypes. The HPO has become the de facto standard for computational phenotype analysis in genomics and rare disease, being used by the NIH Undiagnosed Diseases Network, the 100,000 Genomes project, and many other academic, clinical, and commercial entities. The HPO currently contains 14,184 terms (February, 2019).

A phenotype-driven approach opens up entirely new ways of mining EHR data for correlations that might be important in understanding disease pathophysiology, gender or age-differences, and biomarkers. It is important to develop clever ways of analyzing the data. We expect that many phenotype abnormalities might be highly correlated in all disease states, and thus identifying such an “obvious” correlation would not be an interesting result. For instance, Abnormal hematocrit and Abnormal hemoglobin level are expected to be highly correlated. Here, we propose adapting the approach taken to characterize [synergy networks](https://www.ncbi.nlm.nih.gov/pubmed/18234101) in expression data which was developed to find gene-gene interactions that are specifically associated with a phenotype (such as a particular cancer). The method is based on an information theoretic analysis of [multivariate synergy](https://www.ncbi.nlm.nih.gov/pubmed/17299419) that decomposes sets of genes into submodules each of which contains synergistically interacting gene. The method can be extended to phenotype to search for pairs of markers (HPO terms) that show mutual information conditional upon the presence of a specific diagnosis (e.g., an ICD9 code, or possible an eMERGE classification). The result would be a data driven way of defining pairs of features that show a surprising correlation in the presence of a disease — this might lead to the discovery of potential biomarkers (in this case, if one finds some HPO term in a person with some disease, then “synergy” would suggest the other HPO term of the pair would be more likely to be present than expected by chance). We also believe this might be a good opportunity to engage CTSA hubs in data exploration or the use of this approach/resulting derived data for DREAM challenges. 

A detailed Implementation protocol is available in this [GoogleDoc](https://docs.google.com/document/d/1ydNi9X8E-Fb-xdbEzN7mDq6vhrheXFcZ4xBOo30Qwoc/edit?usp=sharing).


## Contact person

Point person (github handle) | Site 
------------------------|---------------
Peter Robinson (@pnrobinson) | JAX 

## Leads 

Lead(s) (github handle) | Site
----------|--------------|
Peter Robinson (@pnrobinson) | JAX
Aaron Zhang (@kingmanzhang ) | JAX
Amy Yates (@aeyates ) | OHSU

## Team members 

See https://github.com/data2health/project-repo-template/tree/master/team.md

## Repositories

https://github.com/TheJacksonLaboratory/loinc2hpoAnnotation
https://github.com/monarch-initiative/loinc2hpo

## Deliverables
Current 6 month period

Item | Delivery
---- | --------
Publication of LOINC2HPO and presentation of LOINC2HPO data on HPO website | May 2019
Mutual information content algorithm for biomarker identification implemented in Java ready for use in CTSA sites | August 2019
Analysis of test datasets (Asthma, ICU) | September 2019
Implementation of algorithm at two CTSA sites and initial analysis of results | September 2019


Subsequent six month period
* Publication about novel algorithm and results in collaboration with CTSA sites
* Cross-site clustering algorithm
* Analysis of test datasets (cross-clustering)
* Implementation of cross-site clustering at CTSA sites
* Implementation plan for adding additional datatypes (e.g., radiology) to EHR2HPO software

## Evaluation plan
The operational architecture evaluation plan is [here](evaluation.md).

## Education

See  [here](education.md)

## Engagement
See [here](engagement.md)


