# BERT Amharic

This repo contains 4 BERT transformer models pretrained on `290 million tokens` of Amharic text. All four models have a context length of `512` tokens and the same tokenizer with a vocabulary size of `28672` tokens. The size of these models ranges from 4 Million to 40 Million parameters.

|Model|Size (# params)| Perplexity|Sentiment (F1)| Named Entity Recognition (F1)|
|-----|---------------|-----------|--------------|------------------------------|
|bert-medium-amharic|40.5M|13.74|0.83|0.68|
|bert-small-amharic|27.8M|15.96|0.83|0.68|
|bert-mini-amharic|10.7M|22.42|0.81|0.64|
|bert-tiny-amharic|4.18M|71.52|0.79|0.54|
|xlm-roberta-base|279M||0.83|0.73|
|am-roberta|443M||0.82|0.69|

### Models
You can download and load the models from HuggingFace using the transformers library.

- bert-medium-amharic : https://huggingface.co/rasyosef/bert-medium-amharic
- bert-small-amharic : https://huggingface.co/rasyosef/bert-small-amharic
- bert-mini-amharic : https://huggingface.co/rasyosef/bert-mini-amharic
- bert-tiny-amharic : https://huggingface.co/rasyosef/bert-tiny-amharic
- Amharic BERT collection : https://huggingface.co/collections/rasyosef/amharic-bert-6661e9a087ef60c3445e7939

### Finetuning Code
- **Sentiment Classification**
  - Dataset: [amharic-sentiment](https://huggingface.co/datasets/rasyosef/amharic-sentiment)
  - Code: https://github.com/rasyosef/amharic-sentiment-classification
  - Finetuned Model: [bert-medium-amharic-finetuned-sentiment](https://huggingface.co/rasyosef/bert-medium-amharic-finetuned-sentiment)
- **Named Entity Recognition**
  - Dataset: [amharic-named-entity-recognition](https://huggingface.co/datasets/rasyosef/amharic-named-entity-recognition)
  - Code: https://github.com/rasyosef/amharic-named-entity-recognition
  - Finetuned Model: [bert-medium-amharic-finetuned-ner](https://huggingface.co/rasyosef/bert-medium-amharic-finetuned-ner)
- **News Category Classification**
  - Dataset: [amharic-news-category-classification](https://huggingface.co/datasets/rasyosef/amharic-news-category-classification)
  - Code: https://github.com/rasyosef/amharic-news-category-classification

# How to use
In addition to finetuning, you can use these models directly with a pipeline for masked language modeling:

```python
>>> from transformers import pipeline
>>> unmasker = pipeline('fill-mask', model='rasyosef/bert-medium-amharic')
>>> unmasker("ከሀገራቸው ከኢትዮጵያ ከወጡ ግማሽ ምዕተ [MASK] ተቆጥሯል።")

[{'score': 0.5135582089424133,
  'token': 9345,
  'token_str': 'ዓመት',
  'sequence': 'ከሀገራቸው ከኢትዮጵያ ከወጡ ግማሽ ምዕተ ዓመት ተቆጥሯል ።'},
 {'score': 0.2923661470413208,
  'token': 9617,
  'token_str': 'ዓመታት',
  'sequence': 'ከሀገራቸው ከኢትዮጵያ ከወጡ ግማሽ ምዕተ ዓመታት ተቆጥሯል ።'},
 {'score': 0.09527599066495895,
  'token': 9913,
  'token_str': 'አመት',
  'sequence': 'ከሀገራቸው ከኢትዮጵያ ከወጡ ግማሽ ምዕተ አመት ተቆጥሯል ።'},
 {'score': 0.06960058212280273,
  'token': 10898,
  'token_str': 'አመታት',
  'sequence': 'ከሀገራቸው ከኢትዮጵያ ከወጡ ግማሽ ምዕተ አመታት ተቆጥሯል ።'},
 {'score': 0.019061630591750145,
  'token': 28157,
  'token_str': '##ዓመት',
  'sequence': 'ከሀገራቸው ከኢትዮጵያ ከወጡ ግማሽ ምዕተዓመት ተቆጥሯል ።'}]
```