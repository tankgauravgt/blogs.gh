---
title: "HuggingFace: LLM Course"
tags:
  - HuggingFace
  - LLMs
  - Course
---

# 0. SETUP
## Commonly used libraries

- transformers
- datasets
- torch

# 1. TRANSFORMER MODELS
## Pipeline() Function

The `pipeline()` function in the 🤗 Transformers library simplifies using models by integrating preprocessing and postprocessing steps.

```python
from transformers import pipeline

text = "Huggingface is awesome!"

# sentiment analysis:
classifier = pipeline("sentiment-analysis")
classifier(text)
```

> [!TIP] 
> We can pass several sentences in one go!

```python
classifier([
	"I've been waiting for a HuggingFace course my whole life.", 
	"I hate this so much!"
])
```

## Available Pipelines

### Text pipelines

| **Task**                 | **Description**                                                      |
| ------------------------ | -------------------------------------------------------------------- |
| text-generation          | Generate text from a prompt.                                         |
| text-classification      | Classify text into predefined categories.                            |
| summarization            | Create a shorter version of a text while preserving key information. |
| translation              | Translate text from one language to another.                         |
| zero-shot-classification | Classify text without prior training on specific labels.             |
| feature-extraction       | Extract vector representations of text.                              |
### Image pipelines

| **Task**             | **Description**                        |
| -------------------- | -------------------------------------- |
| image-to-text        | Generate text descriptions of images.  |
| image-classification | Identify objects in an image.          |
| object-detection     | Locate and identify objects in images. |
### Audio pipelines

| **Task**                     | **Description**                 |
| ---------------------------- | ------------------------------- |
| automatic-speech-recognition | Convert speech to text.         |
| audio-classification         | Classify audio into categories. |
| text-to-speech               | Convert text to spoken audio.   |
### Multimodal pipelines

| **Task**           | **Description**                             |
| ------------------ | ------------------------------------------- |
| image-text-to-text | Respond to an image based on a text prompt. |

## Usage of Text Pipelines:

### Text Generation

```python

```

### Text Classification

```python

```

### Text Summarization

```python

```

### Text Translation

```python

```

### Text Zero-Shot Classification

```python

```

### Text Feature Extraction

```python

```
