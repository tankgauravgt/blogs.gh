---
title: "HuggingFace: LLM Course"
tags:
  - HuggingFace
  - LLMs
  - Course
---
# HuggingFace - LLM Course

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

## Tasks and Pipeline() Compatibility

- **NLP Pipelines**

| **Task**                 | **Description**                                                      | **Pipeline()** |
| ------------------------ | -------------------------------------------------------------------- | -------------- |
| feature-extraction       | Extract vector representations of text.                              | `[ yes ]`      |
| fill-mask                | Fills masked text data.                                              | `[ yes ]`      |
| question-answering       | Retrieve the answer to a question from a given text.                 | `[ yes ]`      |
| sentence-similarity      | Determine how similar two texts are.                                 | `[ no ]`       |
| summarization            | Create a shorter version of a text while preserving key information. | `[ yes ]`      |
| table-question-answering | Answering a question about an information on a given table.          | `[ yes ]`      |
| text-classification      | Classify text into predefined categories.                            | `[ yes ]`      |
| text-generation          | Generate text from a prompt.                                         | `[ yes ]`      |
| text-ranking             | Rank a set of texts based on their relevance to a query.             | `[ no ]`       |
| token-classification     | NLU task in which a label is assigned to some tokens in a text.      | `[ yes ]`      |
| translation              | Convert text from one language to another.                           | `[ yes ]`      |
| zero-shot-classification | Classify text without prior training on specific labels.             | `[ yes ]`      |

- **Vision pipelines**

| **Task**                       | **Description**                                                                                     | Pipeline() |
| ------------------------------ | --------------------------------------------------------------------------------------------------- | ---------- |
| depth-estimation               | Estimate the depth of different objects present in an image.                                        | `[ yes ]`  |
| image-classification           | Identify objects in an image.                                                                       | `[ yes ]`  |
| image-feature-extraction       | Extract semantically meaningful features given an image.                                            | `[ yes ]`  |
| image-segmentation             | Divides an image into segments where each pixel in the image is mapped to an object                 | `[ yes ]`  |
| image-to-image                 | Transform image. (eg. inpainting, colorization, Super Resolution)                                   | `[ yes ]`  |
| image-to-text                  | Generate text descriptions of images.                                                               | `[ yes ]`  |
| image-to-video                 | Generate a video influenced by text prompts.                                                        | `[ no ]`   |
| keypoint-detection             | Identify meaningful distinctive points or features in an image.                                     | `[ no ]`   |
| mask-generation                | Generate masks that identify a specific object or region of interest in a given image.              | `[ yes ]`  |
| object-detection               | Locate and identify objects in images.                                                              | `[ yes ]`  |
| video-classification           | Assign a label or class to an entire video.                                                         | `[ yes ]`  |
| text-to-image                  | Generating images from input text.                                                                  | `[ no ]`   |
| text-to-video                  | Generating consistent sequence of images from text.                                                 | `[ no ]`   |
| unconditional-image-generation | Generating images with no condition in any context.                                                 | `[ no ]`   |
| video-to-video                 | Transform input video into a new video with altered visual styles, motion, or content.              | `[ no ]`   |
| zero-shot-image-classification | Classify previously unseen classes during training of a model.                                      | `[ yes ]`  |
| zero-shot-object-detection     | Detect objects and their classes in images, without any prior training or knowledge of the classes. | `[ yes ]`  |
| text-to-3d                     | Text-to-3D models take in text input and produce 3D output.                                         | `[ no ]`   |
| image-to-3d                    | Image-to-3D models take in image input and produce 3D output.                                       | `[ no ]`   |

- **Audio pipelines**

| **Task**                     | **Description**                 |
| ---------------------------- | ------------------------------- |
| automatic-speech-recognition | Convert speech to text.         |
| audio-classification         | Classify audio into categories. |
| text-to-speech               | Convert text to spoken audio.   |

- **Multimodal pipelines**

| **Task**           | **Description**                             |
| ------------------ | ------------------------------------------- |
| image-text-to-text | Respond to an image based on a text prompt. |

- **Other Pipelines**

| **Task**           | **Description**                     |
| ------------------ | ----------------------------------- |
| feature-extraction | Extract features learnt in a model. |
