# Aspect-Level Information Discrepancies across Heterogeneous Vulnerability Reports: Severity, Types and Detection Methods

This repository shows the labels, supplement files and training details of paper **Aspect-Level Information Discrepancies across Heterogeneous Vulnerability Reports: Severity, Types and Detection Methods**

## Contents

| File | Description |
|-|-|
| [labels_ner](https://github.com/anonymous-dev905/aspect_discrepency/tree/master/Labels/labels_ner) | Labels for training and testing NER models (See Section II-F-2)  |
| [labels_qa](https://github.com/anonymous-dev905/aspect_discrepency/tree/master/Labels/labels_qa) | Labels for training and testing QA models (See Section II-F-3) |
| [labels_discrepancy_classifier](https://github.com/anonymous-dev905/aspect_discrepency/tree/master/Labels/labels_discrepancy_classifier) | Labels for training and testing discrepancy detection classifiers (See Section II-F-4) |
| [samples_discrepancy_detection](https://github.com/anonymous-dev905/aspect_discrepency/tree/master/Labels/samples_discrepancy_detection) | Manually sampled data for discrepancy detection (See Section II-F-4) |
| [Supply_Figures](https://github.com/anonymous-dev905/aspect_discrepency/tree/master/Supplementary_Materials) | Supplementary materials of larger figures of Fig 2:Scale of Aspect Absence, Fig 3:Scale of Aspect Mismatch and Fig 4:Percentages of Mismatch Types (See Section IV-A, IV-B and IV-C) |

## Training Details
We train all the models on Windows 10 with 16-core Intel 9900K CPU, one NVDIA GTX 1080Ti GPU and 64 GB RAM.

### GloVe
We use pre-trained [glove.840.300d](https://nlp.stanford.edu/projects/glove/) by Stanford, fine-tuned with vulnerability reports and [Mitten](https://github.com/roamanalytics/mittens).

### NER
#### BERT
For the training of BERT-NER and BERT-QA, we use the Transformers of [HuggingFace](https://github.com/huggingface/transformers/).
We set learning rate to 2e-5 with 20 training epochs and 8 batch sizes for BERT-NER.
We use pre-trained uncased English model as the initial model.
The rest of hyperparameters are kept with defalt value.

#### LSTM
Model can be found [here](https://github.com/JOJO201/API_Extraction)
We set learning rate to 0.01 with 100 training epochs and 10 batch sizes.
The rest of hyperparameters are kept with defalt value.

### QA
#### BERT
We set learning rate to 5e-5 with 20 training epochs and 8 batch sizes for BERT-QA.
We use pre-trained uncased English model as the initial model.
The rest of hyperparameters are kept with defalt value.

#### BiDAF
Model can be found [here](https://github.com/white127/SQUAD-2.0-bidaf)
We set learning rate to 0.001 with 100 training epochs and 30 batch sizes.
The rest of hyperparameters are kept with defalt value.

### Discrepancy Detection Classifier
#### Sentence BERT
We set learning rate to 2e-5 with 10 training epochs and 8 batch sizes.
We use pre-trained uncased English model as the initial model.
The rest of hyperparameters are kept with defalt value.

#### Siamese CNN
We set learning rate to 0.001 with 15 training epochs and 64 batch sizes.
We set filter sizes to 2, 3, and 4 with 128 filters each, and we also set dropout with 0.5 keep probability. 

## References
[1] J. Pennington, R. Socher, and C. D. Manning. 2014. GloVe: Global Vectors for Word Representation.

[2] N. Dingwall and C. Potts. 2018. Mittens: An Extension of GloVe for Learning Domain-Specialized Representations.

[3] ] S. Ma, Z. Xing, C. Chen, C. Chen, L. Qu, and G. Li. 2019. Easy-to-deploy api extraction by multi-level feature embedding and transfer learning.

[4] J. Devlin, M.-W. Chang, K. Lee, and K. Toutanova. 2019. BERT: Pretraining of deep bidirectional transformers for language understanding.

[5] M. Seo, A. Kembhavi, A. Farhadi, H. Hajishirzi. 2018. Bidirectional Attention Flow for Machine Comprehension.

[6] B. Xu, D. Ye, Z. Xing, X. Xia, G. Chen, and S. Li. 2016. Predicting semantically linkable knowledge in developer online forums via convolutional neural network.

[7]  N. Reimers and I. Gurevych. 2019. Sentence-BERT: Sentence embeddings using Siamese BERT-networks.
