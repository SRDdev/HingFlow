# English to Hindi Translation Model

This repository contains a Translation model for English to Hindi using existing Language Models (LLMs). The purpose of this document is to provide an overview of potential challenges in the translation process and suggest an evaluation setup for iterative model improvements.

## Quick Start Guide

To use the English to Hindi Translation Model, follow these steps:

1. Install the required dependencies:
   
   ```shell
   pip install torch
   pip install transformers
   pip install sentencepiece
   ```

2. Import the necessary libraries in your Python script:

   ```python
   import torch
   from transformers import AutoTokenizer, AutoModelForSeq2SeqLM
   ```

3. Load the pre-trained model and tokenizer:

   ```python
   tokenizer = AutoTokenizer.from_pretrained("SRDdev/HingFlow")

   model = AutoModelForSeq2SeqLM.from_pretrained("SRDdev/HingFlow")
   ```

4. Provide English text as input and generate Hindi translation:

   ```python
   from transformers import pipeline

   translate = pipeline('translation', tokenizer=tokenizer, model=model)
   translate("My name is Shreyas")[0]['translation_text']
   ```

### Translation Challenges:

1. Idiomatic Expressions: Translating idioms and expressions from English to Hindi while preserving their intended meaning and cultural context can be challenging.

2. Tone and Style Adaptation: Capturing the tone and style of the original English text during translation is important to maintain the author's intended voice, humor, or formality. This requires careful attention to nuances, which can be complex in cross-language translation.

3. Domain-specific Terminology: Translating content that contains technical or specialized terms specific to a particular field may require finding suitable alternatives or adapting the terminology for the Hindi target audience.

4. Word Sense Disambiguation: English words often have multiple meanings depending on the context. Accurately identifying the intended sense of a word and providing the appropriate translation in Hindi is crucial for accurate comprehension of the translated content.

### Other Improvement Iterations

In addition to the evaluation setup, the following improvement iterations can be considered:

1. Augmented Data: Increasing the diversity and quantity of training data by augmenting the parallel corpus with additional high-quality translations from reputable sources can improve coverage of domain-specific terminology and idiomatic expressions.

2. Fine-grained Control: Developing mechanisms to allow users or translators to provide guidance to the translation models, such as specifying the desired tone, style, or cultural adaptation, can enable more customized translations.

### Evaluation Setup

To evaluate the translation model, the following evaluation setup was implemented using the **`sacrebleu`** metric and custom prompts:

1. Loading the Metric:

   ```python
   metric = load_metric("sacrebleu")
   ```

   The **`sacrebleu`** metric is a widely used evaluation metric for machine translation that computes the BLEU score. It measures the similarity between the translated output and reference translations.

2. Custom Prompts:

   The translation models were evaluated on a set of custom prompts, which are representative sentences. These prompts cover a diverse range of topics, styles, and complexities to assess the models' performance comprehensively.

3. Model Accuracy:

   The model's accuracy was assessed based on the evaluation output, which included the following information:

   | Metric                      | Value                   |
   | --------------------------- | ----------------------- |
   | Global Step                 | 2000                    |
   | Training Loss               | 0.1282172145843506      |
   | Train Runtime               | 1498.4139 seconds       |
   | Train Samples per Second    | 21.356                  |
   | Train Steps per Second      |1.335                    |
   | Train Loss                  | 0.1282172145843506      |
   
  
