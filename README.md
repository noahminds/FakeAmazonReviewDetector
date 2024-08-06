# Amazon Fake Product Review Detection

## Overview
This project tackles the challenge of detecting fake reviews on Amazon, differentiating between genuine reviews written by humans and those generated by a GPT-2 model. This task not only addresses a significant issue impacting consumer trust and business ethics on online platforms but also explores the capabilities of generative models in both crafting and identifying synthetic text. Inspired by the GROVER model's self-detection premise, this work expands upon prior research by Salminen et al., 2022, which utilized GPT-2 for the generation and RoBERTa for the detection of synthetic reviews.

## Dataset
The dataset comprises 40,000 reviews, balanced between original human-written and fake computer-generated entries, and was created from the work of Salminen et al., 2021. These reviews span various product categories, providing a rich basis for training and evaluating the model's performance. The data includes:

- Text: The review text.
- Label: Binary labels indicating whether a review is original ('OR') or computer-generated ('CG').

## Model
The model architecture employed is a fine-tuned GPT-2, originally used for generating fake reviews, which has been repurposed for classification tasks. This project specifically investigates the effectiveness of using a generative model as a discriminator, hypothesizing that it can effectively identify nuances in text it is trained to generate.

## Methodology
1. Data Preprocessing: Standard text preprocessing alongside specialized tokenization for the GPT-2 model.
2. Model Adaptation: The GPT-2 model, fine-tuned for generation of reviews belonging to a particular product category (e.g. Books), is adapted to perform binary classification.
3. Training and Evaluation: The model is trained on a labeled dataset and evaluated based on accuracy, precision, recall, and F1-score metrics against a test set and various unseen product categories to assess generalizability.

## Results
The model demonstrated excellent capability in distinguishing between genuine and generated reviews, achieving an accuracy of 97.26% on the test set. Moreover, it showed promising generalizability across different product categories not included in the training data.

## Usage
The repository includes Jupyter notebooks that detail the entire process from data loading, model training, and evaluation. Users can replicate the study or use the methodology as a framework for related tasks in fake detection.

## Credits
- Original Paper on Creating and Detecting Fake Reviews: [Joni Salminen et al., 2021](https://doi.org/10.1016/j.jretconser.2021.102771)
- Original Datasets and Pre-trained Models: [Joni Salminen et al., 2021](https://drive.google.com/drive/folders/1aadnypFL_aLiP6Z61VAW4_gYibGXLV2x?usp=sharing)
- Inspiration and Conceptual Framework: [Zellers et al., 2020](https://doi.org/10.48550/arXiv.1905.12616), on defending against neural fake news using the generator model itself as a discriminator.
- Development: This project was developed by Noah Meurer, building on the foundational models and datasets provided by prior researchers.
