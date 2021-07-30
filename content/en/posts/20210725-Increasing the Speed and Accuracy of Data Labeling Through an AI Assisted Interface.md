---
title: Increasing the Speed and Accuracy of Data Labeling Through an AI Assisted Interface
description:
tags: General NLP
categories: paper notes
series: Conference Paper
lastmod: '2021-07-25'
featuredImage:
draft: false
---

Desmond, M., Muller, M., Ashktorab, Z., Dugan, C., Duesterwald, E., Brimijoin, K., ... \& Pan, Q. (2021, April). Increasing the Speed and Accuracy of Data Labeling Through an AI Assisted Interface. In *26th International Conference on Intelligent User Interfaces* (pp. 392-401). doi: 10.1145/3397481.3450698

<!--more-->

# Abstract
Labeling data is an important step in the supervised machine learning lifecycle. It is a laborious human activity comprised of repeated decision making: the human labeler decides which of several potential labels to apply to each example. Prior work has shown that providing AI assistance can improve the accuracy of binary decision tasks. However, the role of AI assistance in more complex data-labeling scenarios with a larger set of labels has not yet been explored. We designed an AI labeling assistant that uses a semi-supervised learning algorithm to predict the most probable labels for each example. We leverage these predictions to provide assistance in two ways: (i) providing a label recommendation and (ii) reducing the labeler’s decision space by focusing their attention on only the most probable labels. We conducted a user study (n=54) to evaluate an AI-assisted interface for data labeling in this context. Our results highlight that the AI assistance improves both labeler accuracy and speed, especially when the labeler finds the correct label in the reduced label space. We discuss findings related to the presentation of AI assistance and design implications for intelligent labeling interfaces.

# Methods
## Task
Participants were asked to examine and label a total of 100 (21 training + 79 experimental) short-text customer inquiries, within 30 minutes.

- Task type: intent recognition

- Label set: 21 labels

## 54 lablers in 3 groups

- 19 labelers without referential labels 

- 18 labelers with referential labels from weakly trained model (acc = 44\%)

- 17 labelers with referential labels from strongly trained model (acc = 59\%)

## Participants
Most of participants had significant experience on Mechanical Turk: 43 had more than 3 years of experience, 7 had 2-3 years, and 4 had 1-2 years. Of our participants, 50 primarily spoke English, while 2 primarily spoke Hindi and 1 primarily spoke Tamil. All participants had at least a high school education, and 41 participants had formal education beyond high school. While most participants (30) had heard about AI, 13 closely followed AI-related news, 8 had AI related work experience, and 3 had extensive experience in AI research or development.

## Materials
Datasets:

- 420 examples, 21-label balanced with minor variances

- encoded by a 512-dimensional vector using Universal Sentence Encoder and then forwarded 

## Data collection

- selected labels

- labelling duration

- view more (view the full list)

- questionnaire (post-experiment questionnaire requesting feedback about labeling experiences)

# Results
## Accuracy

Accuracy was significantly different between the three conditions, F(2, 51) = 4.18, p < 0.02. 

Accuracy decreased in the baseline condition (0.72 ± 0.10) compared to the weak assistance condition (0.79 ± 0.05) and the strong assistance condition (0.78 ± 0.05). 

Tukey post-hoc analyses revealed that the increase from baseline to weak assistance was statistically significant (p < 0.03). Participants were more accurate in the weak assistance condition than in the baseline condition. No other condition differences were statistically significant. The accuracy difference between the baseline condition and strong assistance condition was not statistically significant (p < 0.07), but survey results suggest that strong assistance positively affected labeler accuracy. 

## Speed

There was a significant effect of assistance condition (baseline, weak assistance, strong assistance) on overall labeling duration (measured in seconds) F(2, 58.2) =5.71, p < .001. 

Tukey post hoc tests showed that users spent less time on each trial in the weak assistance condition (8.81 ± 14.6) than baseline condition (9.36 ± 9.58), p < 0.004, and spent less time on each trial in the strong assistance condition (9.07 ± 16.5) than the baseline condition (9.36 ± 9.58), p < 0.04.

# Key conclusions
- Human labelers are significantly more accurate when assisted by a predictive model during labeling activities. 

- Overall our AI assisted participants were 6\% more accurate than the unassisted participants. No significant difference in accuracy between weaker (less accurate) AI assistance and stronger (more accurate)
AI assistance. 

- This was somewhat surprising and suggests that labelers are unlikely to overly rely on assistance; instead, they can discern when the predictions are inaccurate and make their own labeling decisions. 

- We also found significant improvement in the amount of time required to perform labeling tasks in the presence of AI assistance. Labeling speed
improvements were especially pronounced when labelers found the desired label in the reduced label space provided by the AI assistant. 
