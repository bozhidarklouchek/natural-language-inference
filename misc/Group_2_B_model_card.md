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

This model computes BiLSTM sentence embeddings
using iterative refinement encoding, it then combines the embeddings
using a heuristic approach and then finally it classifies using FNN
classifier.

- **Developed by:** Bozhidar Klouchek and Martin Marinov
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Deep Learning Non-Transformers
- **Finetuned from model [optional]:** n/a

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** n/a
- **Paper or documentation:** n/a

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

26K pairs of texts

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


    - num_epochs 3
    - train_batch_size 128 
    - eval_batch_size: 16
    - word_embedding_dim: 300 
    - sentnece_dim 600 
    - dropout 0.1 
    - learning_rate 0.0005 
    - lr_decay 0.99 
    

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 6 minutes
      - duration per training epoch: 2 minutes
      - model size: 128MB

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

The model obtained a validation accuracy score of 72.09%.

## Technical Specifications

### Hardware


      - RAM: at least 8 GB
      - Storage: at least 2GB,
      - GPU: T4

### Software


      - torch 0.3.1
      - mumpy 1.14.3
      - torchtext 0.2.1
      - spacy 2.0.11

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->

n/a

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters were determined by conducting gridspace search defined by 3 values for
    batch size and sentence embedding dimensionality each, for 8 epochs, repeated 3 times and averaged to stabilise values.
