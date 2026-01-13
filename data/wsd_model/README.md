---
license: mit
language:
- fr
metrics:
- f1
base_model:
- almanach/camembert-base
pipeline_tag: text2text-generation
library_name: transformers
tags:
- Transformer
- disambiguation
---

# wsd-camembert-base-semcor-wngt-fr : almanach/camembert-base fine-tuned on Semcor+WNGT fr for Word Sense Disambiguation

<!-- Provide a quick summary of what the model is/does. -->

*wsd-camembert-base-semcor-wngt-fr* is a Word Sense Disambiguation (WSD) model fine-tuned on the French version of Semcor and WNGT datasets with *almanach/camembert-base* as the pretrained BERT embeddings.

The fine-tuned model achieves the following performance on SemEval 2013 - fr:
| Test F1 (%) | GPUs | Epochs |
|:-------------:|:--------------:|:--------------:|
| 51.28 | 1xV100 32GB | 40 |

## 📝 Model Details

The WSD model is a **Transformer encoder-decoder** architecture, consisting of 6 layers in both the encoder and decoder, and leveraging pretrained BERT embeddings for enhanced semantic representation.

## 💻 How to disambiguate a sentence

To disambiguate a sentence, please refer to the official [NWSD](https://github.com/macairececile/nwsd?tab=readme-ov-file#disambiguate-a-text) repository.

## ⚙️ Training Details

### Training and Test Data

We use [Semcor.fr](https://frsemcor.github.io/FrSemCor/) and [WNGT.fr](https://github.com/getalp/UFSAC) annotated with WordNet 3.0 sense keys IDs for the train/valid sets:
| | Train | Valid |
|:-------------:|:-------------:|:--------------:|
| # utterances | 143,597 | 4,000 |

The semeval2013task12.fr.xml test data is the French version of the [SemEval-2013 Task 12](https://aclanthology.org/S13-2040/) test set, with:
| | Test | 
|:-------------:|:-------------:|
| # utterances | 306 |

### Training Procedure and Hyperparameters

We follow the training procedure provided in the [NWSD](https://github.com/macairececile/nwsd) github repository.

#### Training time

With 1xV100 32GB, the training took ~ 4 hours.

#### Libraries

[Disambiguate](https://github.com/macairececile/nwsd):
```bibtex
  @inproceedings{vial-etal-2019-sense,
    title = "Sense Vocabulary Compression through the Semantic Knowledge of {W}ord{N}et for Neural Word Sense Disambiguation",
    author = {Vial, Lo{\"i}c  and
      Lecouteux, Benjamin  and
      Schwab, Didier},
    editor = "Vossen, Piek  and
      Fellbaum, Christiane",
    booktitle = "Proceedings of the 10th Global Wordnet Conference",
    month = jul,
    year = "2019",
    address = "Wroclaw, Poland",
    publisher = "Global Wordnet Association",
    url = "https://aclanthology.org/2019.gwc-1.14/",
    pages = "108--117",
}
```

## 💡 Information

- **Developed by:** Cécile Macaire
- **Funded by [optional]:** GENCI-IDRIS (Grant 2023-AD011013625R1)
PROPICTO ANR-20-CE93-0005
- **Language(s) (NLP):** French
- **License:** MIT
- **Finetuned from model:** almanach/camembert-base