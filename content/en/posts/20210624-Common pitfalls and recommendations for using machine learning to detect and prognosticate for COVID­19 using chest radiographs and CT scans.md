---
title: 【Note·Review】 Common pitfalls and recommendations for using machine learning to detect and prognosticate for COVID­-19 using chest radiographs and CT scans
description:
toc: true
tags:
categories: paper notes
series: General NLP/CV
lastmod: '2021-06-24'
featuredImage:
draft: false
---

AIX­COVNET, Roberts, M., Driggs, D., Thorpe, M., Gilbey, J., Yeung, M., Ursprung, S., Aviles­Rivero, A. I., Etmann, C., McCague, C., Beer, L., Weir­McCall, J. R., Teng, Z., Gkrania­Klotsas, E., Rudd, J. H. F., Sala, E., & Schönlieb, C.­B. (2021). Common pitfalls and recommendations for using machine learning to detect and prognosticate for COVID­19 using chest radiographs and CT scans. *Nature Machine Intelligence, 3*(3), 199–217. https://doi.org/10.1038/s42256­021­00307­0

<!--more-->

# Metadata
# Abstract
Machine learning methods offer great promise for fast and accurate detection and prognostication of coronavirus disease 2019 (COVID­19) from standard­of­care chest radiographs (CXR) and chest computed tomography (CT) images. Many articles have been published in 2020 describing new machine learning­based models for both of these tasks, but it is unclear which are of potential clinical utility. In this systematic review, we consider all published papers and preprints, for the period from 1 January 2020 to 3 October 2020, which describe new machine learning models for the diagnosis or prognosis of COVID­19 from CXR or CT images. All manuscripts uploaded to bioRxiv, medRxiv and arXiv along with all entries in EMBASE and MEDLINE in this timeframe are considered. Our search identified 2,212 studies, of which 415 were included after initial screening and, after quality screening, 62 studies were included in this systematic review. Our review finds that none of the models identified are of potential clinical use due to methodological flaws and/or underlying biases. This is a major weakness, given the urgency with which validated COVID­19 models are needed. To address this, we give many recommendations which, if followed, will solve these issues and lead to higher­quality model development and well­documented manuscripts.

# Methods 
Based on Prediction models for diagnosis and prognosis of COVID­-19: systematic review and critical appraisal (Wynants, L. et al., 2020). Researchers included clinicians and algorithm developers. Focus on: (1) risk of bias assessment; (2) quality screening to only include papers with sufficiently documented methodologies; (3) systematic methodological flaws.
## Search strategy and selection criteria

![Flowchart](/flowchart.png)  

1.	Search strategy with reference to requirements of meta­ analysis
-    Followed the Preferred Reporting Items for Systematic Reviews and Meta¬Analyses (PRISMA) checklist. (Liberati, A., Altman, D. G., Tetzlaff, J., Mulrow, C., Gøtzsche, P. C., Ioannidis, J. P., ... & Moher, D. (2009). The PRISMA statement for reporting systematic reviews and meta¬analyses of studies that evaluate health care interventions: explanation and elaboration. Journal of clinical epidemiology, 62(10), e1¬e34.)
-    Databases to search: arxiv, ”Living Evidence on COVID¬19”, OVID, MEDLINE (PubMed), bioRxiv and medRxiv. Find the codes and data by clicking this.
    - initial extraction:
        - arXiv papers: papers including 'ncov' (as a complete word), 'coronavirus', 'covid', 'sars-cov-2' or 'sars¬cov2' in their title or abstract.
        -    Living Evidence on COVID¬19: all papers
    -    Refined search:
        -    title or abstract contain one of: 'ai', 'deep', 'learning', 'machine', 'neural', 'intelligence', ‘prognos’, 'diagnos', 'classification', 'segmentation' and also contain one of 'ct', 'cxr', 'x-ray', 'xray’, ‘imaging’, ‘image’, ‘radiograph’.
        -    Only 'ai', 'ct' and 'cxr' are required to be complete words.
-    Time period: 2020.01.01 -- 2020.10.03
-    Remove duplicated papers: manually and by Covidence

2.	Three­stage process to determine whether to include a paper or not
-   title and abstract screening
-   full­text screening
-   quality review
    - allow the results to be reliably reproduced
    - NOT a judgment on the quality or impact of a paper or algorithm
3.	Paper grouping and assessment
-   deep learning models: assessed against CLAIM (Mongan, J., Moy, L., & Kahn Jr, C. E.(2020). Checklist for artificial intelligence in medical imaging (CLAIM): a guide for authors and reviewers.)
-   traditional machine learning models: scored using RQS (Lambin, P., Leijenaar, R. T., Deist, T. M., Peerlings, J., De Jong, E. E., Van Timmeren, J., ... & Walsh, S. (2017). Radiomics: the bridge between medical imaging and personalized medicine. Nature reviews Clinical oncology, 14(12), 749­762.)
-   Only on the papers themselves. Not on the codes even if available.

## Assessment
1. Risk of bias
PROBAST: The papers that passed the quality assessment stage were split among three teams of two reviewers to complete the PROBAST review. Within each team, the two reviewers independently scored the risk of bias for each paper and then resolved by conflicts any remaining conflicts were resolved by a third reviewer. (Wolff, R. F., Moons, K., Riley, R. D., Whiting, P. F., Westwood, M., Collins, G. S., Reitsma, J. B., Kleijnen, J., Mallett, S., & PROBAST Group† (2019). PROBAST: A Tool to Assess the Risk of Bias and Applicability of Prediction Model Studies. Annals of internal medicine, 170(1), 51–58. https://doi.org/10.7326/M18­1376)

2. Data Analysis
The papers were allocated among five teams of two reviewer, with focus on 7 kinds of information. Any conflicts were initially resolved by team discussions and remaining conflicts were resolved by a third reviewer.
-   Is this paper describing a COVID­19 diagnosis or prognosis model (or both)?
-   Data: Does the paper use CXR or CT (or both)?
-   Predictors: What are the predictors?
-   Sample sizes used for development (train and val, but not test), sample sizes used for test, and holdout cohorts (along with the number of COVID­19 positive cases)
-   the type of validation, and evaluation matrix
-   the best performance quoted in the paper for the validation cohort (whether internal, external or both)
-   whether the code for training the model and the trained model were publicly available.

# Results
## Study selection
62 papers included, with 37 deep learning models, 23 traditional machine learning models and 2 hybrid models
## Quality screening failures
Top 3 failures for DL papers (CLAIM check):
1.	How the final model was selected, 61% (132)
2.	The method of pre­processing of the image, 58% (125)
3.	The details of the training approach (e.g. optimizer, loss function, learning rate), 49%(105)

Top 2 failures for TML papers (RQS check):
1.	Feature reduction techniques, 52% (23)
2.	Model validation, 61% (27)

## Risks of bias
1.	Participants: 6 low, 11 unclear, 45 high
2.	Predictors: 20 low, 4 high (38 N/A due to DL models)
3.	Outcomes: 25 low, 26 unclear, 11 high
4.	Analyses: 10 low

## Data analysis
-   validation type: 48 internal, 13 external, 1 test on train data
-   model evaluation: 10 cross­val
-   partition (by class) analysis: 20 balance between classes. 19 fewer than 2000 datapoints for development. Only 7 papers used a balanced dataset of over 2000 datapoints.
-   public availability: 13 public, 1 on request

# Discussion
1.	Limitations of the current literature most frequently reflect either a limitation of the dataset used in the model or methodological mistakes repeated in many studies that probably lead to overly optimistic performance evaluations
2. Datasets: big problems of public datasets: source and duplication issues; Frankenstein dataset; implicit biases in the source data
3. All proposed models suffer from a high or unclear risk of bias in at least one domain.
-   population bias: using datasets not representative for target population, e.g.
paediatric patients

## recommendations
1.	the data used for model development and common pitfalls
2.	the evaluation of trained models
3.	reproducibility
4.	documentation in manuscripts
5.	the peer­review process

# Conclusion
**None of the models are currently ready to be deployed clinically.**
1.	the bias in small datasets;
2.	the variability of large internationally sourced datasets;
3.	the poor integration of multi­stream data, particularly imaging data;
4.	the difficulty of the task of prognostication; and
5.	the necessity for clinicians and data analysts to work side­by­side to ensure the developed AI algorithms are clinically relevant and implementable into routine clinical care.
