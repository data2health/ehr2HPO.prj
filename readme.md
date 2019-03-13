# HPO 2 EHR

## Problem statement

This tool converts FHIR/LOINC encoded laboratory test results as HPO codes; here we extend the conversion to other phenotype sources in the EHR.

## Project description

Electronic Health Record (EHR) systems typically define laboratory test results using the Laboratory Observation Identifier Names and Codes (LOINC) and can transmit them using Fast Healthcare Interoperability Resource (FHIR) standards. LOINC has not yet been semantically integrated with computational resources for phenotype analysis. The Human Phenotype Ontology (HPO) is a freely available and open source logically defined vocabulary for describing human abnormal phenotypes. The HPO has become the de facto standard for computational phenotype analysis in genomics and rare disease, being used by the NIH Undiagnosed Diseases Network, the 100,000 Genomes project, and many other academic, clinical, and commercial entities. The HPO currently contains 14,184 terms (February, 2019)  including a comprehensive representation of laboratory abnormalities such as *Hyperglycemia*, *Thrombocytopenia*, and *Increased urine alpha-ketoglutarate concentration*. In this project, we have developed software to encode the **outcome** of LOINC-encoded laboratory tests as HPO codes. We have develop a FHIR interface and a SMART on FHIR demonstration app. Our software can be used to characterize the spectrum of lab abnormalities identified in a single patient encounter or to analyze a cohort of patients, for example, to search for biomarkers. We are extending the software to additional areas of the EHR including radiology, pathology, and clinical notes, and are developing algorithms that will apply this library to single or multi-site projects with the goal of biomarker identification and stratification of disease-based cohorts into clusters. Please see our preprint [Semantic Integration of Clinical Laboratory Tests from Electronic Health Records for Deep Phenotyping and Biomarker Discovery](https://www.biorxiv.org/content/10.1101/519231v1?rss=1) for background about this project.


## Contact person

Point person (github handle) | Site | Program Director
----------|--------------|---------------
Peter Robinson (@pnrobinson) | JAX | Chris Chute (@cgchute)

## Leads 

Lead(s) (github handle) | Site
----------|--------------|
Peter Robinson (@pnrobinson) | JAX


## Team members 

See https://github.com/data2health/project-repo-template/tree/master/team.md

## Repositories

https://github.com/TheJacksonLaboratory/loinc2hpoAnnotation
https://github.com/monarch-initiative/loinc2hpo

## Deliverables
We have listed the main deliverables of our project as GitHub [milestones](https://github.com/data2health/hpo2ehr.prj/milestones).


## Education

See  [here](education.md)


## Engagement
See [here](engagement.md)


