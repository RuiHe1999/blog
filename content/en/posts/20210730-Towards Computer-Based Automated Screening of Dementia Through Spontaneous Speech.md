---
title: [Note | Research] Towards Computer-Based Automated Screening of Dementia Through Spontaneous Speech
description:
tags: 
categories: paper notes
series: Computational AD
lastmod: '2021-07-30'
featuredImage:
draft: false
---

Chlasta, K., & Wołk, K. (2021). Towards Computer-Based Automated Screening of Dementia Through Spontaneous Speech. *Frontiers in psychology, 11*, 623237. https://doi.org/10.3389/fpsyg.2020.623237

<!--more-->

```
@ARTICLE{10.3389/fpsyg.2020.623237,
AUTHOR={Chlasta, Karol and Wołk, Krzysztof},   
TITLE={Towards Computer-Based Automated Screening of Dementia Through Spontaneous Speech},      JOURNAL={Frontiers in Psychology},  VOLUME={11},
PAGES={4091},     
YEAR={2021},      
URL={https://www.frontiersin.org/article/10.3389/fpsyg.2020.623237},       
DOI={10.3389/fpsyg.2020.623237},   
ISSN={1664-1078},   
ABSTRACT={Dementia, a prevalent disorder of the brain, has negative effects on individuals and society. This paper concerns using Spontaneous Speech (ADReSS) Challenge of Interspeech 2020 to classify Alzheimer's dementia. We used (1) VGGish, a deep, pretrained, Tensorflow model as an audio feature extractor, and Scikit-learn classifiers to detect signs of dementia in speech. Three classifiers (LinearSVM, Perceptron, 1NN) were 59.1% accurate, which was 3% above the best-performing baseline models trained on the acoustic features used in the challenge. We also proposed (2) DemCNN, a new PyTorch raw waveform-based convolutional neural network model that was 63.6% accurate, 7% more accurate then the best-performing baseline linear discriminant analysis model. We discovered that audio transfer learning with a pretrained VGGish feature extractor performs better than the baseline approach using automatically extracted acoustic features. Our DepCNN exhibits good generalization capabilities. Both methods presented in this paper offer progress toward new, innovative, and more effective computer-based screening of dementia through spontaneous speech.}
}
```

# Abstract
Dementia, a prevalent disorder of the brain, has negative effects on individuals and society. This paper concerns using Spontaneous Speech (ADReSS) Challenge of Interspeech 2020 to classify Alzheimer's dementia. We used (1) VGGish, a deep, pretrained, Tensorflow model as an audio feature extractor, and Scikit-learn classifiers to detect signs of dementia in speech. Three classifiers (LinearSVM, Perceptron, 1NN) were 59.1% accurate, which was 3% above the best-performing baseline models trained on the acoustic features used in the challenge. We also proposed (2) DemCNN, a new PyTorch raw waveform-based convolutional neural network model that was 63.6% accurate, 7% more accurate then the best-performing baseline linear discriminant analysis model. We discovered that audio transfer learning with a pretrained VGGish feature extractor performs better than the baseline approach using automatically extracted acoustic features. Our DepCNN exhibits good generalization capabilities. Both methods presented in this paper offer progress toward new, innovative, and more effective computer-based screening of dementia through spontaneous speech.

# Introduction
1. Dementia is estimated to be responsible for 11.2% of years lived with disability in people over 60 years of age, compared with 9.5% for stroke, 5.0% for cardiovascular disease, and 2.4% for cancer.
2. There is a significant relation between old-age depression and subsequent dementia in patients over the age of 50. This supports the hypothesis of old-age depression being a predictor, and possibly a causal factor of subsequent dementia (Buntinx et al., 1996).

# Methods
## Data
1. 2020 ADReSS challenge  
   78 non-AD subjects, and 78 AD subjects
2. Model: VGGish Model with Scikit-Learn Classifiers  
   VGGish for feature extraction while Scikit-learn for classification
   - Feature Extraction
     - pre-trained embedding model (VGGNet)
	 - Principal component analysis: dimension reduction
	 - embedding dimension: 128
   - Classification
	 - 5 methods: SVM, LSVM,perceptron, MLP, INN	  
3. DemCNN	
![DemCNN](20210730-Towards Computer-Based Automated Screening of Dementia Through Spont-0001.jpg) 
4. Code: 
   https://github.com/KarolChlasta/ADReSS-Challenge2020

# Results
1. train/test split: 80% : 20% (randomly split)
2. accuracy result
   ![fpsyg-11-623237-t001.jpg](20210730-Towards Computer-Based Automated Screening of Dementia Through Spont-0002.jpg)
   ![fpsyg-11-623237-t002.jpg](20210730-Towards Computer-Based Automated Screening of Dementia Through Spont-0003.jpg)

# Discussion
1. Relatively small gains were found when fusing acoustics and linguistics approaches
