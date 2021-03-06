# Budget
Don't edit this - the RPPR generator populates this section

# Research Design
Electronic Health Record (EHR) systems typically define laboratory test results using the Laboratory Observation Identifier Names and Codes (LOINC) and can transmit them using Fast Healthcare Interoperability Resource (FHIR) standards. LOINC has not yet been semantically integrated with computational resources for phenotype analysis. The Human Phenotype Ontology (HPO) is a freely available and open source logically defined vocabulary for describing human abnormal phenotypes. The HPO has become the de facto standard for computational phenotype analysis in genomics and rare disease, being used by the NIH Undiagnosed Diseases Network, the 100,000 Genomes project, and many other academic, clinical, and commercial entities. The HPO currently contains 14,184 terms (February, 2019) including a comprehensive representation of laboratory abnormalities such as Hyperglycemia, Thrombocytopenia, and Increased urine alpha-ketoglutarate concentration. In this project, we have developed software to encode the outcome of LOINC-encoded laboratory tests as HPO codes. We have develop a FHIR interface and a SMART on FHIR demonstration app. Our software can be used to characterize the spectrum of lab abnormalities identified in a single patient encounter or to analyze a cohort of patients, for example, to search for biomarkers.
In this project, we propose to use our resources that map the outcomes of LOINC-encoded laboratory tests to HPO terms to address two challenges in EHR-driven research: (i) Biomarker identification and (ii) Clustering (Stratification) of diseases into subgroups. The current proposal is a pilot project that concentrates on biomarker identification but also lays the foundation for subgroup clustering.

# Methodology
Detailed methods are available in the protocol document available on [this projects GitHub repository](https://github.com/data2health/ehr2HPO.prj). In brief, we propose two approaches to use and extend our existing LOINC2HPO software with data from CD2H and non-CD2H CTSAs. Our first approach involves the extraction of LOINC and HPO terms much the same as we did in the original publication (npj Digital Medicine Volume 2, Article number: 32; 2019). We will then apply a statistical approach that is based on mutual information content and synergy networks to search for disease-specific biomarkers. We anticipate that we will complete this project within the coming 12 month period. We will additionally implement a clustering procedure that has the goal of identifying reproducible phenotype-driven disease stratifications that are consistent across multiple CTSAs.
We are planning on developing and validating the algorithms using two datasets (an asthma patient dataset from UNC and an intensive care unit patient from MIT) and then applying them to a ca. 2,2 million patient dataset at JHU. We have initiated discussions with CTSAs that expressed interest and anticipate that we will be able to apply our analysis at at least one additional center.

# Expected Outcomes
1. Implementation of  mutual information content and synergy network algorithm to extend LOINC2HPO project (Java). The detailed implementation method is described [here](https://docs.google.com/document/d/1ydNi9X8E-Fb-xdbEzN7mDq6vhrheXFcZ4xBOo30Qwoc/edit?usp=sharing).
2. Implementation of phenotype-driven disease stratification to extend LOINC2HPO project (Java). The detailed implementation method is described [here](https://docs.google.com/document/d/1ydNi9X8E-Fb-xdbEzN7mDq6vhrheXFcZ4xBOo30Qwoc/edit?usp=sharing).
3. Pilot analysis of MIMIC3 publicly available dataset. The dataset contains records on ~45,000 ICU patients, including 28 million laboratory tests. We will convert the lab tests into HPO terms. Using the results from this and the asthma dataset, we will test the algorithms implemented in 1 and 2.
4. Analysis of JHU dataset. We will follow a similar strategy as described in Step 3, but this is a much larger dataset and less biased toward specific disease cohorts. We anticipate getting HPO-encoded patient profiles for ~2.2 million patients,  obtaining conditional phenotypic associations on disease diagnosis, and obtaining phenotype-based patient clusters. However, the progress of this exercise is dependent on the speed of IRB approval and data transfer. 
5. Analysis of at least one additional CTSA dataset (phenotype-driven disease stratification). The analysis results will be similar to Step 4. Additionally, we will get disease stratification comparisons across CTSA sites. The comparison methods has been described [here](https://docs.google.com/document/d/1ydNi9X8E-Fb-xdbEzN7mDq6vhrheXFcZ4xBOo30Qwoc/edit?usp=sharing).

# Deliverables
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


# Timeline (monthly)
1. Planning/architecture of mutual information content algorithm (M1)
2. Implementation of initial version of mutual information content (M2)
3. Analysis of MIMIC3 dataset (M3,4) and testing algorithms implemented in 1 and 2.
4. Analysis of JHU dataset (M5-M7).
5. Second half of 12 month period -- depending on results, we will write a manuscript. We will make the code available open source on GitHub. We will plan/architect and implement the phenotype-driven disease stratification algorithm and test it on JHU/CTSA data

# Potential Pitfalls and Alternative Strategies
1. Data access. We will work with interested centers and IRB to obtain appropriate access. We will develop code that can be run within a center’s firewall so that no PHI sharing is required to perform the analysis.
2. Performance of algorithms. If the algorithms do not perform as anticipated we will explore alternative algorithmic strategies. For the first algorithm, we could search for simple conditional correlation instead of conditional mutual information, for instance. For the second algorithm, there are numerous heuristics for defining features and clusters, many of which are available in software “toolkits” such as the machine learning toolkit for Java called Weka. We will define a gold standard test set with the MIMIC data and explore the performance of several algorithms.


# Y3 (July 1, 2019-June 30, 2020) Accomplishments 
The following content is from the June 30 - Dec 30, 2019 mid year progress report [here](https://docs.google.com/document/d/1LLe3uCfEUakWxIJyi5SA4ZocYDmINvhySTperaui1Bw/edit).  Please add progress for Jan 1 - June 30th, 2020. 

* Implementation of phenotype-driven disease stratification to extend LOINC2HPO project (Java). 
    * 100% complete. The basic EHR2HPO tool that we created (repo here; demo here) allows us to examine disease prediction by HPO features identified by our synergy analysis. There was a certain predictive power with ROC scores typically around 75%. 
    
* Publication of LOINC2HPO and presentation of LOINC2HPO data on HPO website:
    * 100% Completed. [Link](https://www.nature.com/articles/s41746-019-0110-4). Example of LOINC data on HPO website [here](https://hpo.jax.org/app/browse/term/HP:0011015).
    
* Planning/architecture and implementation of mutual information content algorithm for biomarker identification; implemented in Java ready for use in CTSA sites:
    * 100% Completed. We implemented in Python [here](https://github.com/TheJacksonLaboratory/MIMIC_HPO/tree/develop/src/main/python). 

* Analysis of test datasets (Asthma, ICU):
    * 100% completed. Asthma analysis completed with MIMIC3 dataset. See [Jupyter notebooks](https://github.com/TheJacksonLaboratory/MIMIC_HPO/tree/develop/src/main/notebooks).

* Analysis of JHU dataset:
    * 50% completed. In progress. Analysis of JHU dataset. We will follow a similar strategy as described in Step 3, but this is a much larger dataset and less biased toward specific disease cohorts. We anticipate getting HPO-encoded patient profiles for ~2.2 million patients, obtaining conditional phenotypic associations on disease diagnosis, and obtaining
phenotype-based patient clusters. However, the progress of this exercise is dependent on the speed of IRB approval and data transfer.
We have completed the code development for this task, and can now move forward with a pilot analysis at JHU. We will work with OCTRI and the JHU team to implement in the next period, if funded. (note that the data/analysis is behind clinical firewall).

* Implementation of algorithm at two CTSA sites and initial analysis of results. Analysis of at least one additional CTSA dataset (phenotype-driven disease stratification). The analysis results will be similar to Step 4. Additionally, we will get disease stratification comparisons across CTSA sites.
    * 50% completed. Technical testing with OHSU data was successful. Still waiting for Colorado IRB. Software requires further maturation before further deployment. 
The comparison methods has been described here.
We postponed this activity. We contacted the University of Colorado site and have agreed to implement at their site; however no progress has been made with their IRB. We will revisit this goal in the next period if funded.

