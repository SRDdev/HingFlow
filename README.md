
# 🎧 DubverseAI

DubverseAI is a technology company that specializes in audio translation services (dubing). The company uses advanced machine learning algorithms to provide accurate and efficient translations of audio content from one language to another.

## English-Hindi Translator
This repository contains a Translation model to translate English sentence to Hindi.We used Neural Machine Translation using Transformers approach to solve this problem. The model has been trained on a English and Hindi text corpus.

The data set used for training includes English sentences and the Hindi text for corresponding english sentence.

## Requirements
To run the code, the following libraries are required:
- TensorFlow
- NumPy
- pandas

```bash
pip install -r requirements.txt
```

## Model Overview 
<img src="https://github.com/SRDdev/DubverseAI/blob/97391e08e7b3f11b2751ad9f02b2c261f019190c/translator.png">

## How it works
**Input representation**: The NMT transformer takes the English sentence as input and first converts it into a sequence of tokens using a tokenizer. Each token represents a word or a subword of the sentence. These tokens are then converted into a vector representation using an embedding layer.

**Encoder**: The embedded tokens are then passed through the encoder layer, which is a stack of multiple self-attention layers. In each self-attention layer, the model learns to attend to different parts of the input sequence and assigns weights to each token based on its importance for the translation. The encoder outputs a sequence of encoded vectors that represent the input sentence.

**Decoder**: The decoder layer is also a stack of self-attention layers, but it also includes a multi-head attention layer that attends to the encoded input sequence. The decoder takes the encoded vectors and generates the corresponding Hindi sentence one token at a time. At each step, the decoder predicts the next token in the output sequence by attending to the encoded input and previously generated tokens.

**Output generation**: The decoder generates the Hindi sentence token by token until it produces the end-of-sequence token or reaches a predefined maximum length. The final output is then converted back into a human-readable sentence using a detokenizer.

**Training**: During training, the model is fed with a large corpus of parallel English-Hindi sentences, and the model parameters are adjusted using backpropagation to minimize the difference between the predicted and target Hindi sentences.

**Inference**: During inference, the model takes a single English sentence as input and generates the corresponding Hindi translation using the learned parameters. The generated output can be further refined using post-processing techniques to improve the fluency and coherence of the translation.

## Inference
```python 
output = decode_sequence("Action is the foundational key to all success.")
print(output)
```


