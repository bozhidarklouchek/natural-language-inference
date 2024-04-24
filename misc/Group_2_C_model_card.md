---
{}
---
language: en
license: cc-by-4.0
tags:
- text-classification
repo: https://github.com/bozhidarklouchek/natural-language-inference

---

# Model Card for x17727bk-x61715mm-NLI

<!-- Provide a quick summary of what the model is/does. -->

This is a classification model that was trained to
      detect natural language inference between two texts.


## Model Details

### Model Description

<!-- Provide a longer summary of what this model is. -->

This model is based upon a DeBERTav3 model that was fine-tuned
      on 26K pairs of texts.

- **Developed by:** Bozhidar Klouchek and Martin Marinov
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Transformers
- **Finetuned from model [optional]:** deberta-v3-base

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** https://huggingface.co/microsoft/deberta-v3-base
- **Paper or documentation:** https://arxiv.org/pdf/2111.09543.pdf

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

26K pairs of texts

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - learning_rate: 2e-05
      - weight_decay: 0.006
      - warmup_ratio: 0.1
      - train_batch_size: 16
      - eval_batch_size: 16
      - seed: 42
      - num_epochs: 1

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 10 minutes
      - duration per training epoch: 10 minutes
      - model size: 715MB

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

A subset of the development set provided, amounting to 3K pairs.

#### Metrics

<!-- These are the evaluation metrics being used. -->
      - Accuracy

### Results

The model obtained a validation accuracy score of 90.78%.

## Technical Specifications

### Hardware


      - RAM: at least 16 GB
      - Storage: at least 2GB,
      - GPU: V100

### Software


      - Datasets 2.19.0
      - Pandas 2.0.3
      - Transformers 4.38.2

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->

Any inputs (concatenation of two sequences) longer than
      512 subwords will be truncated by the model.

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters were determined by conducting gridspace search defined by 3 values for
    learning rate and weight decay each, for 6 epochs, repeated 3 times and averaged to stabilise values.
