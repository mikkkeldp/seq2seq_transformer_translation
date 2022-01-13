# Seq2Seq transformer for translation
Seq2Seq model for German to English translation using a simple transformer architecture. 

Uses [Multi30k](https://www.statmt.org/wmt16/multimodal-task.html#task1) dataset to train a German to English translation model. 

The transformer architecture was first introducted in ["Attention is all you need"](https://papers.nips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf) and was used as a sequence to sequence model (Seq2Seq) for machine translation tasks. This network consists of three parts:

- **Embedding layer**: Layer that converts tensors of input indices into corresponding tensor of input embeddings. These embedding are further augmented with positional encodings to provide position information of input tokens to the model.
- **Transformer**: Network consisting of an encoder and decoder, each consisting of stacked self-attention and point-wise fully connected layers.
- **Linear layer**: Output of transformer is passed through a linear layer that gives un-normalized probabilities (logits) for each token in the target language. 

During training, we mask out subsequent words that prevents the model to look into the future when making prediction. We also hide source and target padding tokens. We use cross-entropy loss and Adam as the optimizer. 


## Run this project 
```
python3 main.py
```

## Example translation

**input**: Eine Gruppe von Menschen steht vor einem Iglu  
**Our model output**:  A group of people in front of an igloo   
**Google translate output**:  A group of people stands in front of an igloo  


