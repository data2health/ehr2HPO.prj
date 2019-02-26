# HPO 2 EHR

## Problem statement

This tool converts FHIR/LOINC encoded laboratory test results as HPO codes; here we extend the conversion to other phenotype sources in the EHR.

## Project description

1. EHR semantic modeling and integration
The first phase of the LOINC2HPO project aimed to encode FHIR/LOINC laboratory test results as HPO codes. However, It would be advantageous to have all phenotypically relevant parts of the EHR in an integrated semantic model that would allow HPO-based computations or other extractions and would include other relevant phenotypic attributes such as imaging results, pathology results, and moving forward medications, procedures, etc. We will use MONDO and (nascent) computational models of common disease to enable analysis of this data in many ways.
The work would be roughly similar to the LOINC work -- develop tools and strategies for biocuration to record observations and test outcomes using HPO terms. This is obviously a large project, and as such, we propose to start with the radiology and pathology data. 
2. Modelling  a medical encounter/patient
Medicine is noisy, and there are multiple levels of data cleansing, data interpretation, and inference in the medical process. In order to make the envisioned system maximally useful, we will want to model some parts of these processes algorithmically. The simplest example is that if we measure electrolytes 20 times in one patient, and one measurement shows a slightly increased sodium, do we want to infer that the HPO term for Hypernatremia should be used for downstream analysis? In our asthma pilot study, we required that a laboratory abnormality be observed at least three times to call the corresponding HPO term, but this is not a robust general approach.To address this issue, we will aim to characterize patterns of abnormalities in real EHR data, and develop strategies for “denoising” the primary data. 

3. Rare disease use case
Text-mining is being increasingly used to extract HPO terms from EHR data and to use it for genomic diagnostics (Kai Wang group in New York) [1] (also personal communication by several practitioners of genomic medicine at other institutions). It would be valuable to have a SMART on FHIR app that would extract HPO terms from various textual parts of the medical record, present them to the physician for “vetting”, and transmit them to genome analysis software (in form of a phenopacket). 

 We propose to advance the software engineering of the SMART on FHIR app we developed in phase I to accommodate this new functionality.. The work on the “semantically integrated model” as per above, is important for choosing the right combination of HPO terms for the genomic diagnostics. Finally, the current generation of HPO algorithms works best with modest numbers of characteristic HPO terms (e.g., 7), but we will be able to extract up to over 100 HPO terms from HPO data (personal communication). Also, we will be able to extract negated HPO terms (e.g., not Abnormal sodium concentration). Optimally, we will extend current HPO-based algorithms to deal with high numbers of HPO terms, including high numbers of negated terms.

4. Common disease use case
Making the correct diagnosis in common disease can be as challenging as in rare disease, even though there are numerous presentations such as acute myocardial infarction that are familiar to nearly all physicians. Asking questions about the underlying cause of new complications in patients with multimorbid past medical histories is challenging and is not well addressed by any current algorithm we are aware of. Here, we propose to begin to develop data structures and algorithms to  represent common disease phenotypes using the “semantically integrated model” as input into the this new generation of algorithms. This will be a preliminary exploration but will be important to validate and develop the semantically integrated model.

5. Data mining use case
A phenotype-driven approach opens up entirely new ways of mining EHR data for correlations that might be important in understanding disease pathophysiology, gender or age-differences, and biomarkers. It is important to develop clever ways of analyzing the data. We expect that many phenotype abnormalities might be highly correlated in all disease states, and thus identifying such an “obvious” correlation would not be an interesting result. For instance, Abnormal hematocrit and Abnormal hemoglobin level are expected to be highly correlated.

Here, wee propose adapting the approach taken to characterize synergy networks in expression data [2], which was developed to find gene-gene interactions that are specifically associated with a phenotype (such as a particular cancer). The method is based on an information theoretic analysis of multivariate synergy that decomposes sets of genes into submodules each of which contains synergistically interacting gene [3]. The method can be extended to phenotype to search for pairs of markers (HPO terms) that show mutual information conditional upon the presence of a specific diagnosis (e.g., an ICD9 code, or possible an eMERGE classification). The result would be a data driven way of defining pairs of features that show a surprising correlation in the presence of a disease  -- this might lead to the discovery of potential biomarkers (in this case, if one finds some HPO term in a person with some disease, then “synergy” would suggest the other HPO term of the pair would be more likely to be present than expected by chance). We also believe this might be a good opportunity to engage CTSA hubs in data exploration or the use of this approach/resulting derived data for DREAM challenges.

References
1. Son JH, Xie G, Yuan C, Ena L, Li Z, Goldstein A, et al. Deep Phenotyping on Electronic Health Records Facilitates Genetic Diagnosis by Clinical Exomes. Am J Hum Genet. 2018;103:58–73.
2. Watkinson J, Wang X, Zheng T, Anastassiou D. Identification of gene interactions associated with disease from gene expression data using synergy networks. BMC Syst Biol. 2008;2:10.
3. Anastassiou D. Computational analysis of the synergy among multiple interacting genes. Mol Syst Biol. 2007;3:83.

## Contact person

We require a contact person for each project for administrative purposes. Each project should also have a CD2H Program director assigned.

Point person (github handle) | Site | Program Director
----------|--------------|---------------
Peter Robinson (@pnrobinson) | JAX | Chris Chute (@cgchute)

## Leads 

``Project scientific leadership, should be 1-3 persons. ``

Lead(s) (github handle) | Site
----------|--------------|
Peter Robinson (@pnrobinson) | JAX


## Team members 

``No action required here, a list of team members will be imported and linked below.``

See https://github.com/data2health/project-repo-template/tree/master/team.md

## Repositories

https://github.com/TheJacksonLaboratory/loinc2hpoAnnotation
https://github.com/monarch-initiative/loinc2hpo

## Deliverables
`` Each project should propose one or more deliverables. Examples: a released code package, a best practices document, a final survey, a set of survey results, etc.``

## Milestones 

In progress see https://github.com/data2health/hpo2ehr.prj/milestones

## Evaluation
````
Each project should propose a set of evaluation measures, recorded in a separate Evaluation Plan file, for example [here](https://github.com/data2health/project-repo-template/blob/master/evaluation.md). These will be reviewed by the Evaluation committee and approved by the Program Directors and NCATS. The Evaluation committee will meet with each Project team leads to assist. 

Each project should have Evaluation-realated issues, that can be tagged with the "evaluation" tag. see [Example Evaluation Issue](https://github.com/data2health/project-repo-template/issues/5)
````
## Education
````
See [education.md](https://github.com/data2health/project-repo-template/blob/master/education.md) for details. Each project should have Education-realated issues, that can be tagged with the "education" tag. 
````
## Get involved
We encourage the community to get involved. 

````
We require all CD2H projects to have non-CD2H CTSA participants, as CD2H is a CTSA coordinating center. Each project should include an Engagement plan file, example [here](https://github.com/data2health/project-repo-template/blob/master/engagement.md). 

Please tag any engagment related issues with "engagement".
````

## Working documents
Documentation may be natively in GitHub using the wiki or .md files in the appropriate folder, or in Google Drive.
[Documentating projects in Github](https://guides.github.com/features/wikis/)

[The project Google drive folder](https://drive.google.com/drive/u/0/folders/1vLp-H32KTNobiZF2cK82At90S6dVJNUf) is accessible to onboarded participants. 

## Slack room
The project slack room is accessible to onboarded participants. You will not automatically be added to the Slack room, you will be invited after onboarding at the link above.
