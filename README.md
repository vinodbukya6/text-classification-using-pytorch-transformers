# text-classification-using-pytorch-transformers

Transformers library by HuggingFace.Transformers (formerly known as pytorch-transformers) provides general purpose architectures(BERT, GPT-2, RoBERTa, XLM, DistilBert, XLNet…)

## DistilBERT Model
DistilBERT(a distilled version of BERT: smaller, faster, cheaper and lighter) model for Binary Text Classification.

# Model Configurations
Transformers, each model architecture is associated with 3 main types of classes:

1. Model class- to load a particular pre-train model

2. Tokenizer class- to pre-process the data and make it comptible with a particular model

3. Configuration class- to load the configuration of a particular moel
these classes share a common class method from_pretrained()

# Example: 
Bert architecture for text classification, 
model class - BertForSequenceClassification, tokenizer class- BertTokenizer, configuration class- BertConfig


# Data pre-processing

To match pretraining model, we have to format the model input sequence in a specific format, to do we have to tokenize the texts correctly

Add Special Tokens
Token [CLS] means the start of a sentence, stands for class [SEP] is for separating sentences for the next sentence prediction task.

The first token of every input sequence is the special classification token – [CLS]. This token is used in classification tasks as an aggregate of the entire sequence representation. It is ignored in non-classification tasks

BERT: [CLS] + tokens + [SEP] + padding, 
DistilBERT: [CLS] + tokens + [SEP] + padding, RoBERTa: [CLS] + prefix_space + tokens + [SEP] + padding, XLM: [CLS] + tokens + [SEP] + padding, 
XLNet: padding + [CLS] + tokens + [SEP]
