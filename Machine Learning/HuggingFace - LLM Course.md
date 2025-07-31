---
title: "HuggingFace: LLM Course"
tags:
  - HuggingFace
  - LLMs
  - Course
---
## 0. SETUP

### Commonly used libraries

- transformers
- datasets
- torch

## 1. TRANSFORMER MODELS

### Pipeline() Function

The `pipeline()` function in the 🤗 Transformers library simplifies using models by integrating preprocessing and postprocessing steps.

```python
from transformers import pipeline

text = "Huggingface is awesome!"

# sentiment analysis:
e2e_model = pipeline("sentiment-analysis")
e2e_model(text)
```

> [!TIP] 
> We can pass several sentences in one go!

```python
e2e_model([
	"I've been waiting for a HuggingFace course my whole life.", 
	"I hate this so much!"
])
```

### Tasks and Pipeline() Compatibility

- **NLP Pipelines**

| **Task**                 | **Description**                                                      | **Pipeline()** |
| ------------------------ | -------------------------------------------------------------------- | -------------- |
| feature-extraction       | Extract vector representations of text.                              | &check;        |
| fill-mask                | Fills masked text data.                                              | &check;        |
| question-answering       | Retrieve the answer to a question from a given text.                 | &check;        |
| sentence-similarity      | Determine how similar two texts are.                                 | &cross;        |
| summarization            | Create a shorter version of a text while preserving key information. | &check;        |
| table-question-answering | Answering a question about an information on a given table.          | &check;        |
| text-classification      | Classify text into predefined categories.                            | &check;        |
| text-generation          | Generate text from a prompt.                                         | &check;        |
| text-ranking             | Rank a set of texts based on their relevance to a query.             | &cross;        |
| token-classification     | NLU task in which a label is assigned to some tokens in a text.      | &check;        |
| translation              | Convert text from one language to another.                           | &check;        |
| zero-shot-classification | Classify text without prior training on specific labels.             | &check;        |

- **Vision pipelines**

| **Task**                       | **Description**                                                                                     | Pipeline() |
| ------------------------------ | --------------------------------------------------------------------------------------------------- | ---------- |
| depth-estimation               | Estimate the depth of different objects present in an image.                                        | &check;    |
| image-classification           | Identify objects in an image.                                                                       | &check;    |
| image-feature-extraction       | Extract semantically meaningful features given an image.                                            | &check;    |
| image-segmentation             | Divides an image into segments where each pixel in the image is mapped to an object                 | &check;    |
| image-to-image                 | Transform image. (eg. inpainting, colorization, Super Resolution)                                   | &check;    |
| image-to-text                  | Generate text descriptions of images.                                                               | &check;    |
| image-to-video                 | Generate a video influenced by text prompts.                                                        | &cross;    |
| keypoint-detection             | Identify meaningful distinctive points or features in an image.                                     | &cross;    |
| mask-generation                | Generate masks that identify a specific object or region of interest in a given image.              | &check;    |
| object-detection               | Locate and identify objects in images.                                                              | &check;    |
| video-classification           | Assign a label or class to an entire video.                                                         | &check;    |
| text-to-image                  | Generating images from input text.                                                                  | &cross;    |
| text-to-video                  | Generating consistent sequence of images from text.                                                 | &cross;    |
| unconditional-image-generation | Generating images with no condition in any context.                                                 | &cross;    |
| video-to-video                 | Transform input video into a new video with altered visual styles, motion, or content.              | &cross;    |
| zero-shot-image-classification | Classify previously unseen classes during training of a model.                                      | &check;    |
| zero-shot-object-detection     | Detect objects and their classes in images, without any prior training or knowledge of the classes. | &check;    |
| text-to-3d                     | Text-to-3D models take in text input and produce 3D output.                                         | &cross;    |
| image-to-3d                    | Image-to-3D models take in image input and produce 3D output.                                       | &cross;    |

- **Audio pipelines**

| **Task**                     | **Description**                                                                                                                                     | **Pipeline()** |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| audio-classification         | Classify audio into categories.                                                                                                                     | &check;        |
| audio-to-audio               | family of tasks in which the input is an audio and the output is one or multiple generated audios. (eg. speech enhancement, source separation, ...) | &cross;        |
| automatic-speech-recognition | Convert speech to text.                                                                                                                             | &check;        |
| text-to-audio                | Convert text to spoken audio.                                                                                                                       | &check;        |

- **Multimodal pipelines**

| **Task**                    | **Description**                                                                        | **Pipeline()** |
| --------------------------- | -------------------------------------------------------------------------------------- | -------------- |
| any-to-any                  | Understand two or more modalities and output two or more modalities.                   | &cross;        |
| audio-text-to-text          | Generate textual responses or summaries based on both audio input and text prompts.    | &cross;        |
| document-question-answering | Take a (document, question) pair as input and return an answer in natural language.    | &cross;        |
| visual-document-retrieval   | Searching for relevant image-based documents, such as PDFs based on input text prompt. | &check;        |
| image-text-to-text          | Take in an image and text prompt and output text.                                      | &check;        |
| video-text-to-text          | Take in a video and a text prompt and output text.                                     | &cross;        |
| visual-question-answering   | Answering open-ended questions based on an image depending on text prompt.             | &check;        |

### Classification of LLM Models

#### 1: Encoder Based (Auto-Encoding Transformers)
- **Focus:** Understanding context, generating embeddings.
- **Mechanism:** Bidirectional attention (sees past & future tokens).
- **Training:** Masked Language Modeling (MLM).
- **Use Cases:** Text classification, sentiment analysis, Named Entity Recognition (NER), question answering (understanding).
- **Examples:** BERT, RoBERTa.
#### 2: Decoder Based (Auto-Regressive Transformers)
- **Focus:** Generating new text, predicting next token.
- **Mechanism:** Unidirectional attention (sees only past tokens).
- **Training:** Predicts next word in a sequence.
- **Use Cases:** Text generation, summarization, chatbots, code generation.
- **Examples:** GPT series, LLaMA, Claude.
#### 3: Encoder + Decoder Based Transformers
- **Focus:** Transforming one sequence into another.
- **Mechanism:** Encoder-Decoder architecture. Encoder processes input, Decoder generates output having influenced by input.
- **Training:** Maps input sequence to output sequence.
- **Use Cases:** Machine translation, abstractive summarization, text style transfer.
- **Examples:** T5, BART, NMT models.

### Auto-Encoding Models

#### Model: BaseAutoEncodingModel

![Transformer Basic Block](https://raw.githubusercontent.com/tankgauravgt/blogs.gh/refs/heads/images/auto-encoding-transformer-architecture.svg)

```python
# Model: BaseAutoEncodingModel
BaseAutoEncodingModel(
	'embedder': BaseAutoEncodingModelEmbedderModule(...),
	'encoder': BaseAutoEncodingModelEncoderModule(...),
	'pooler': BaseAutoEncodingModelPoolerModule(...)
)
```

#### Module: BaseAutoEncodingModelEmbedder

```python
# Module: BaseAutoEncodingModelEmbedder
BaseAutoEncodingModelEmbedder(
    'word_emb': WordEmbedder(...), 
    'pos_emb': PositionEmbedder(...), 
    'tok_type_emb': TokenTypeEmbedder(...), 
    'layer_norm': LayerNorm(...), 
    'dropout': Dropout(...)
)
```

#### Module: BaseAutoEncodingModelEncoder

```python
# Module: BaseAutoEncodingModelEncoder
BaseAutoEncodingModelEncoder(
    'layers': ModuleList(
		'layer': N x BaseAutoEncodingModelEncoderLayer(
		    'attention': BaseAutoEncodingModelAttention(...), 
	        'intermediate': BaseAutoEncodingModelIntermediate(...), 
	        'output': BaseAutoEncodingModelOutput(...)
		)
	)
)

# SubModule: BaseAutoEncodingModelAttention
BaseAutoEncodingModelAttention(
	'self_attention': BaseAutoEncodingModelSelfAttention(
		'Q': Linear(...), 
		'K': Linear(...), 
		'V': Linear(...), 
		'dropout': Dropout(...)
	),
	'self_output': BaseAutoEncodingModelSelfOutput(
		'dense': Linear(...), 
		'layer_norm': LayerNorm(...), 
		'dropout': Dropout(...)
	),
)

# SubModule: BaseAutoEncodingModelIntermediate
BaseAutoEncodingModelIntermediate(
	'dense': Linear(...), 
	'activation': Activation(...)
)

# SubModule: BaseAutoEncodingModelOutput
BaseAutoEncodingModelOutput(
	'dense': Linear(...), 
	'layer_norm': LayerNorm(...), 
	'dropout': Dropout(...) 
)
```

#### Module: BaseAutoEncodingModelPooler

```python
BaseAutoEncodingModelPooler(
	'dense': Linear(...), 
	'activation': Activation(...)
)
```

## Train Sequence to Sequence Model

```python
import torch.functional as F
import torch.nn as nn
import transformers
import tokenizers
import torch
import os
import math
from torch.utils.data import TensorDataset, DataLoader
from tqdm import tqdm
import glob

if os.path.exists("tokenizer.json"):
    tokenizer = tokenizers.Tokenizer.from_file("tokenizer.json")
else:
    tokenizer = tokenizers.SentencePieceUnigramTokenizer()

    tokenizer.train(
        files=['./notebooks/processed.hi', './notebooks/processed.en'],
        vocab_size=8000,
        show_progress=True,
        special_tokens=["[UNK]", "[PAD]", "[CLS]", "[SEP]", "[MASK]"]
    )
    tokenizer.save("tokenizer.json")

unk_token_id = tokenizer.token_to_id("[UNK]")
pad_token_id = tokenizer.token_to_id("[PAD]")
cls_token_id = tokenizer.token_to_id("[CLS]")
sep_token_id = tokenizer.token_to_id("[SEP]")
mask_token_id = tokenizer.token_to_id("[MASK]")

class TranslationModelConfig(transformers.PretrainedConfig):
    model_type = "translation-hi2en"

    def __init__(
            self,
            vocab_size=8000,
            d_model=512,
            num_encoder_layers=6,
            num_decoder_layers=6,
            num_heads=8,
            dim_feedforward=512,
            dropout=0.1,
            pad_token_id=pad_token_id,
            eos_token_id=sep_token_id,
            decoder_start_token_id=cls_token_id,
            initializer_range=0.02,
            max_position_embeddings=512,
            **kwargs):
        super().__init__(pad_token_id=pad_token_id, eos_token_id=eos_token_id, **kwargs)
        self.vocab_size = vocab_size
        self.d_model = d_model
        self.num_encoder_layers = num_encoder_layers
        self.num_decoder_layers = num_decoder_layers
        self.num_heads = num_heads
        self.dim_feedforward = dim_feedforward
        self.dropout = dropout
        self.decoder_start_token_id = decoder_start_token_id
        self.initializer_range = initializer_range
        self.max_position_embeddings = max_position_embeddings


class PositionalEncoding(nn.Module):
    def __init__(self, d_model, dropout = 0.1, max_len = 5000):
        super().__init__()
        self.dropout = nn.Dropout(p=dropout)

        position = torch.arange(max_len).unsqueeze(1)
        div_term = torch.exp(torch.arange(0, d_model, 2) * (-math.log(10000.0) / d_model))

        pe = torch.zeros(max_len, d_model)
        pe[:, 0::2] = torch.sin(position * div_term)
        pe[:, 1::2] = torch.cos(position * div_term)

        self.register_buffer('pe', pe.unsqueeze(0))

    def forward(self, x):
        seq_len = x.size(1)
        x = x + self.pe[:, :seq_len]
        return self.dropout(x)


class TranslationModel(transformers.PreTrainedModel):

    def __init__(self, config):
        super().__init__(config)

        self.cfg = config

        self.src_embedding = nn.Embedding(config.vocab_size, config.d_model, padding_idx=config.pad_token_id)
        self.tgt_embedding = nn.Embedding(config.vocab_size, config.d_model, padding_idx=config.pad_token_id)

        self.positional_encoding = PositionalEncoding(config.d_model, config.dropout, config.max_position_embeddings)

        encoder_layer = nn.TransformerEncoderLayer(
            d_model=config.d_model,
            nhead=config.num_heads,
            dim_feedforward=config.dim_feedforward,
            dropout=config.dropout,
            batch_first=True
        )
        self.encoder = nn.TransformerEncoder(encoder_layer, num_layers=config.num_encoder_layers)

        decoder_layer = nn.TransformerDecoderLayer(
            d_model=config.d_model,
            nhead=config.num_heads,
            dim_feedforward=config.dim_feedforward,
            dropout=config.dropout,
            batch_first=True
        )
        self.decoder = nn.TransformerDecoder(decoder_layer, num_layers=config.num_decoder_layers)

        self.output_layer = nn.Linear(config.d_model, config.vocab_size)

        self.apply(self._init_weights)

    def _init_weights(self, module):
        if isinstance(module, nn.Linear):
            module.weight.data.normal_(mean=0.0, std=self.cfg.initializer_range)
            if module.bias is not None:
                module.bias.data.zero_()
        elif isinstance(module, nn.Embedding):
            module.weight.data.normal_(mean=0.0, std=self.cfg.initializer_range)
            if module.padding_idx is not None:
                module.weight.data[module.padding_idx].zero_()
        elif isinstance(module, nn.LayerNorm):
            module.bias.data.zero_()
            module.weight.data.fill_(1.0)

    def forward(self, src, tgt, src_mask=None, tgt_mask=None):
        max_len = self.cfg.max_position_embeddings
        if src.size(1) > max_len:
            src = src[:, :max_len]
            if src_mask is not None:
                src_mask = src_mask[:, :max_len]
        if tgt.size(1) > max_len:
            tgt = tgt[:, :max_len]
            if tgt_mask is not None and tgt_mask.size(0) > max_len:
                tgt_mask = tgt_mask[:max_len, :max_len]

        src_emb = self.positional_encoding(self.src_embedding(src) * math.sqrt(self.cfg.d_model))
        tgt_emb = self.positional_encoding(self.tgt_embedding(tgt) * math.sqrt(self.cfg.d_model))

        memory = self.encoder(src_emb, src_key_padding_mask=src_mask)

        output = self.decoder(tgt_emb, memory, tgt_mask=tgt_mask, memory_key_padding_mask=src_mask)

        logits = self.output_layer(output)

        return logits

model = TranslationModel(TranslationModelConfig())

device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
print(f"Using device: {device}")
model.to(device)

optimizer = torch.optim.Adam(model.parameters(), lr=1e-4)

criterion = nn.CrossEntropyLoss(ignore_index=pad_token_id)

batch_size = 32
seq_len = 256

class PairedDataset(torch.utils.data.Dataset):
    def __init__(self, src_data, tgt_data):
        self.tokenizer = tokenizer
        assert len(src_data) == len(tgt_data), "Source and target data must have the same length."
        self.src_data = src_data
        self.tgt_data = tgt_data
        self.max_len = 512

    def __len__(self):
        return len(self.src_data)

    def __getitem__(self, idx):
        src_ids = tokenizer.encode(self.src_data[idx]).ids
        tgt_ids = tokenizer.encode(self.tgt_data[idx]).ids
        if len(src_ids) > self.max_len:
            src_ids = src_ids[:self.max_len]
        if len(tgt_ids) > self.max_len:
            tgt_ids = tgt_ids[:self.max_len]
        return src_ids, tgt_ids

dataset = PairedDataset(
    open('./notebooks/processed.hi', 'r').readlines(),
    open('./notebooks/processed.en', 'r').readlines()
)

train_size = int(0.8 * len(dataset))
val_size = int(0.1 * len(dataset))
test_size = len(dataset) - train_size - val_size
train_dataset, val_dataset, test_dataset = torch.utils.data.random_split(dataset, [train_size, val_size, test_size])

train_dataloader = DataLoader(train_dataset, batch_size=batch_size, shuffle=True, collate_fn=lambda batch: (
    torch.nn.utils.rnn.pad_sequence([torch.tensor(item[0])[:512] for item in batch], batch_first=True, padding_value=pad_token_id),
    torch.nn.utils.rnn.pad_sequence([torch.tensor(item[1])[:512] for item in batch], batch_first=True, padding_value=pad_token_id)
))

num_epochs = 500

checkpoint_dir = "checkpoints"
os.makedirs(checkpoint_dir, exist_ok=True)

latest_checkpoint = None
checkpoints = sorted(glob.glob(os.path.join(checkpoint_dir, "checkpoint_epoch_*.pt")))
if checkpoints:
    latest_checkpoint = checkpoints[-1]

start_epoch = 0
if latest_checkpoint is not None:
    print(f"Loading checkpoint from {latest_checkpoint} to resume training...")
    checkpoint = torch.load(latest_checkpoint, map_location=device)
    model.load_state_dict(checkpoint['model_state_dict'])
    optimizer.load_state_dict(checkpoint['optimizer_state_dict'])
    start_epoch = checkpoint['epoch']
    print(f"Resuming from epoch {start_epoch}")

print("\nStarting training loop on actual data...")
for epoch in range(start_epoch, num_epochs):
    model.train()
    total_loss = 0

    for batch_idx, (src_batch, tgt_batch) in enumerate(tqdm(train_dataloader, ncols=80)):
        src_batch, tgt_batch = src_batch.to(device), tgt_batch.to(device)

        src_mask = (src_batch == pad_token_id).to(device)

        decoder_input = tgt_batch[:, :-1]
        target_labels = tgt_batch[:, 1:]

        decoder_input_seq_len = decoder_input.size(1)
        causal_tgt_mask = torch.triu(torch.ones(decoder_input_seq_len, decoder_input_seq_len), diagonal=1).bool().to(device)

        output_logits = model(src_batch, decoder_input, src_mask=src_mask, tgt_mask=causal_tgt_mask)

        loss = criterion(output_logits.view(-1, model.cfg.vocab_size), target_labels.reshape(-1))

        optimizer.zero_grad()
        loss.backward()
        optimizer.step()

        total_loss += loss.item()

    avg_loss = total_loss / len(train_dataloader)
    print(f"Epoch {epoch+1}/{num_epochs}, Average Loss: {avg_loss:.4f}")

    checkpoint_path = os.path.join(checkpoint_dir, f"checkpoint_epoch_{epoch+1}.pt")
    torch.save({
        'epoch': epoch + 1,
        'model_state_dict': model.state_dict(),
        'optimizer_state_dict': optimizer.state_dict(),
        'loss': avg_loss
    }, checkpoint_path)

    checkpoints = sorted(glob.glob(os.path.join(checkpoint_dir, "checkpoint_epoch_*.pt")))
    if len(checkpoints) > 2:
        os.remove(checkpoints[0])

print("\nTraining loop on actual data finished.")
print("If the 'Average Loss' is decreasing over epochs, your model is training!")
```
