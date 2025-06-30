---
title: "HuggingFace: LLM Course"
tags:
  - HuggingFace
  - LLMs
  - Course
---
# HuggingFace - LLM Course

# CH-0 SETUP
## Commonly used libraries

- transformers
- datasets
- torch

# CH-1 TRANSFORMER MODELS
## Pipeline() Function

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
from transformers import pipeline

text = "In this course, we will teach you how to"

# generate text based on prompt text:
e2e_generator = pipeline(
	task="text-generation",
	model="gpt2"
)
e2e_generator(text, num_return_sequences=5)
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
