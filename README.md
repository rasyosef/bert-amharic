# BERT Amharic

This repo contains 4 BERT transformer models pretrained on `290 million tokens` of Amharic text. All four models have a context length of `512` tokens and the same tokenizer with a vocabulary size of `28672` tokens.

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
- **Named Entity Recognition**
  - Dataset: [amharic-named-entity-recognition](https://huggingface.co/datasets/rasyosef/amharic-named-entity-recognition)
  - Code: https://github.com/rasyosef/amharic-named-entity-recognition
- **News Category Classification**
  - Dataset: [amharic-news-category-classification](https://huggingface.co/datasets/rasyosef/amharic-news-category-classification)
  - Code: https://github.com/rasyosef/amharic-news-category-classification