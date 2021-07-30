---
title: Alzheimer's Dementia Detection from Audio and Text Modalities
description:
tags: 
categories: paper notes
series: Computational AD
lastmod: '2021-03-30'
featuredImage:
draft: false
---

Campbell, E. L., Docío-Fernández, L., Raboso, J. J., & García-Mateo, C. (2020). Alzheimer's Dementia Detection from Audio and Text Modalities. *arXiv preprint arXiv*:2008.04617.

<!--more-->

```
@misc{campbell2020alzheimers,
      title={Alzheimer's Dementia Detection from Audio and Text Modalities}, 
      author={Edward L. Campbell and Laura Docío-Fernández and Javier Jiménez Raboso and Carmen García-Mateo},
      year={2020},
      eprint={2008.04617},
      archivePrefix={arXiv},
      abstract={Automatic detection of Alzheimer's dementia by speech processing is enhanced when features of both the acoustic waveform and the content are extracted. Audio and text transcription have been widely used in health-related tasks, as spectral and prosodic speech features, as well as semantic and linguistic content, convey information about various diseases. Hence, this paper describes the joint work of the GTM-UVIGO research group and acceXible startup to the ADDReSS challenge at INTERSPEECH 2020. The submitted systems aim to detect patterns of Alzheimer's disease from both the patient's voice and message transcription. Six different systems have been built and compared: four of them are speech-based and the other two systems are text-based. The x-vector, i-vector, and statistical speech-based functionals features are evaluated. As a lower speaking fluency is a common pattern in patients with Alzheimer's disease, rhythmic features are also proposed. For transcription analysis, two systems are proposed: one uses GloVe word embedding features and the other uses several features extracted by language modelling. Several intra-modality and inter-modality score fusion strategies are investigated. The performance of single modality and multimodal systems are presented. The achieved results are promising, outperforming the results achieved by the ADDReSS's baseline systems.}
}
```

# Abstract
Automatic detection of Alzheimer’s dementia by speech processing is enhanced when features of both the acoustic waveform and the content are extracted. Audio and text transcription have been widely used in health-related tasks, as spectral and prosodic speech features, as well as semantic and linguistic content, convey information about various diseases. Hence, this paper describes the joint work of the GTM-UVIGO research group and acceXible startup to the ADDReSS chal-lenge at INTERSPEECH 2020. The submitted systems aim to detect patterns of Alzheimer’s disease from both the patient’s voice and message transcription. ==Six different systems have been built and compared: four of them are speech-based and the other two systems are text-based.== The x-vector, i-vector, and statistical speech-based functionals features are evaluated. As a ==lower speaking fluency== is a common pattern in patients with Alzheimer’s disease, ==rhythmic features== are also proposed. For transcription analysis, two systems are proposed: one uses ==GloVe word embedding features== and the other uses ==several features extracted by language modelling==. Several intra-modality and inter-modality score fusion strategies are investigated. The performance of single modality and multimodal systems are presented. The achieved results are promising, outperforming the results achieved by the ADDReSS’s baseline systems.

# General Description of the detectors
1. six systems: 4 speech-based and 2 text-based
2. speech-based systems

feature | classfier
---|---
i-vectior | SVM
x-vectore | SVM
rhythmic features | SVM
statistical functionals | LDA
3. text-based: 1 with GloVe and 1 with features extracted by language modelling
4. evaluated on ADReSS Challenge (INTERSPEECH 2020)

# speech-based systems
1. i-vectors
- 125-dimension vectors and length normalized
2. x-vectors
- 512 dimensions
- projected to 200 dimensions using LDA and then length normalized 
- i-x comparison on zhihu   
[X-vector 说话人识别 为何 会比i-vector 好很多？ - Leon晋的回答 - 知乎](https://www.zhihu.com/question/317772323/answer/635747215)

> Since a number of embeddings are extracted from each audio, there will also be a set of classification results (one for each embedding), which must be combined to obtain a patient’s classification in AD or non-AD. In this work, the mean of the classifications was used as score for the final decision. 

3. statistical functionals
- extracted by openSMILE and selected the mose relevant 57 ones using CFS algorithm
- [openSMILE简介及使用 - trans2018的文章 - 知乎](https://zhuanlan.zhihu.com/p/69170521)
- [特征选择之-CFS（Correlation-based Feature Selection） - 刘佩的文章 - 知乎](https://zhuanlan.zhihu.com/p/51710394/)
- [【机器学习】特征选择(Feature Selection)方法汇总 - 孙佳伟的文章 - 知乎](https://zhuanlan.zhihu.com/p/74198735)
- Energy and spectral features
  - Loudness, MFCC and delta-MFCC,
  - energy in bands 250–650Hz and 1 kHz–4 kHz, 25% spectral roll-of points,
  - spectral flux, entropy, skewness, 
  - psychoacousitc sharpness, harmonicity, flatness
- Voicing related
  -  F0,voicing probability, jitter

4. speech fluency
- prosodic features
    - Number of syllables
    - Rate of speech (syllables / original duration)
    - Speaking duration
    - Average fundamental frequency
    - Median of fundamental frequency
    - Minimum fundamental frequency
    - Pronunciation posterior probability
    - Average voice interval duration
    - Average duration of pairs 3
    - Mean energy
    - The ratio between the energy mean and its standard-deviation

# text-based systems
1. sequential model  
50-dimension GloVe + LSTM RNN
2. feature-based
- features
  - Extension information such as the number of interven-tions, number of words per intervention and mean word length.
  - Vocabulary richness,    by measuring the number of unique words used by the subject.
  - Presence of key informational concepts: kitchen, mother, stool, boy and girl.
  - Frequency of verbs, nouns, adjectives and pronouns from POS-tagging.


# Thoughts
1. Generally speaking, the proposed models in this paper have shown a moderate performace (hihgest accuracy: speech: 0.7500; text: 0.7962). But I think this accuracy is not enough for real use. When we put the classifier into real use, we need to consider many external factors that made the recordings (as well as the transcriptions) not that perfect as we have in the dataset.
2. The authors used transcripts from dataset. I don't like this idea as these transcripts were made by human. I expect a speech-detetor to be fully automated and not requiring human efforts, because it is harder and cost more to have a linguists in AD screening room writting transcripts all day than to use imaging techniques. A better option should be using an automated speech recognizor and used the automatedly produced transcripts.
3. I'm not very clear about the objective of this paper, but I think it might be related to comparison of different features in predicting AD. Then I'm a bit confused when they used different classifier in these systems. For example, in text-based system, they used RNN for GloVe-based sequential model but SVM for feature-based one. The difference in performance might also result from the different classifiers. 
4. The features and classifiers used are very classicial in mathine learning. For classifiers, they used SVM and linear discriminant analysis; for word embedding features, they used GloVe embeddings. These are not the state-of-art techniques in mathine learning, especially for text-based systems (e.g. for the first text-based model, GloVe is context-free and contextual embeddings like ELMo and Bert may have better performances, and BiLSTM may work better than LSTM). I think maybe they used this for more practical and commercial reasons (e.g. faster, lower cost ... ) but I'm not sure. 
5. (This has been mentioned in the conclusion). Linguistic feature set and fluency feature set are coarse-grained and incomplete. Especially for fluency, I think non-verbal features like fillers and pauses should be included. 

