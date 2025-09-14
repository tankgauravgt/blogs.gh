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
