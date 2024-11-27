# MWE-Stable-Diffusion-Interpretation

## Overview

This repository contains the dataset, code, and outputs related to the thesis **"Interpreting Multi-Word Expressions in Text-to-Image Generation: A Cross-Attention Approach Using Stable Diffusion."** The work explores how generative models like Stable Diffusion 2.1 handle Multi-Word Expressions (MWEs) and uses interpretability tools such as DAAM (Diffusion Attention Attribution Maps) to analyze model attention.

---

## Contents

1. [Introduction](#introduction)
2. [Dataset Description](#dataset-description)
3. [Code Description](#code-description)
4. [Outputs](#outputs)
5. [Setup and Usage](#setup-and-usage)
6. [Dependencies](#dependencies)
7. [Acknowledgments](#acknowledgments)
8. [License](#license)

---

## Introduction

Multi-Word Expressions (MWEs) encompass idioms, collocations, and phrases that convey meanings beyond their literal components. They are central to natural language but pose challenges for generative models due to their context-dependent and often abstract nature. This repository:
- Explores the semantic and visual representation of MWEs.
- Leverages Stable Diffusion 2.1 for generating images from text prompts.
- Uses DAAM to analyze and visualize attention distribution across the generated images.

---

## Dataset Description

### File: `mwe_with_ai_prompts_sorted.xlsx`

This dataset is an extended version of the **[MWE-CWI dataset](https://github.com/ekochmar/MWE-CWI/blob/master/final_MWE_dataset.tsv)**. It includes:
1. **MWEs**: Multi-word expressions such as "spill the beans" and "hard pressed."
2. **Context**: Sentences providing linguistic and situational context for each MWE.
3. **Generated Prompts**: Text prompts crafted for Stable Diffusion to represent each MWE.
4. **Annotations**:
   - Supersenses: High-level semantic categories for the MWEs.
   - Complexity scores: Binary/probabilistic labels indicating difficulty for native and non-native speakers.

This dataset plays a pivotal role in:
- Generating accurate textual prompts.
- Evaluating semantic alignment between MWEs and their visual representations.

---

## Code Description

### File: `working_DAAM_thesis.ipynb`

The Jupyter Notebook contains all the code necessary for:
1. **Prompt Engineering**:
   - Integrates MWEs naturally into descriptive and contextually rich prompts.
   - Ensures prompts stay within Stable Diffusion’s token limit.
   - Example: `"A close-up of a person nervously spilling beans onto the floor, symbolizing the accidental revealing of a secret. The atmosphere is tense, and the background is a modern office."`
   
2. **Image Generation**:
   - Uses Stable Diffusion 2.1 to generate high-quality images based on the crafted prompts.
   - Encodes prompts using CLIP and processes them through latent diffusion steps.

3. **DAAM Visualizations**:
   - Generates heatmaps to visualize cross-attention scores.
   - Maps heatmaps onto the image to highlight the model’s focus areas.
   - Example outputs include heatmaps for "spill the beans" and "hard pressed."

4. **Evaluation Framework**:
   - **Metrics**:
     - Intersection over Union (IoU): Measures alignment between heatmaps and annotated ground-truth masks.
     - Coverage Metrics: Quantifies how much attention is focused on relevant regions.

---

## Outputs

### Generated Images and Visualizations

#### Example 1: President Barack Obama - "Hard Pressed"

The generated image depicts President Barack Obama in a formal setting, reflecting the semantic context of being "hard pressed" in a political scenario.

<img src="https://github.com/Sayefalikhan03/MWE-Stable-Diffusion-Interpretation/blob/main/Generated%20Image.png" alt="President Barack Obama - Generated Image" width="300"/>

#### DAAM Heatmap Overlay for "Hard Pressed"

<img src="https://github.com/Sayefalikhan03/MWE-Stable-Diffusion-Interpretation/blob/main/Attention%20map.png" alt="DAAM Heatmap - Hard Pressed" width="300"/>

---

#### Example 2: "Spill the Beans"

This example captures the idiomatic expression "Spill the Beans." The original image shows a person nervously spilling beans, symbolizing revealing a secret. The DAAM overlay highlights the model’s attention to the beans and the context of the action.

##### Original Image:
<img src="https://github.com/Sayefalikhan03/MWE-Stable-Diffusion-Interpretation/blob/main/original_image.png" alt="Spill the Beans - Original Image" width="300"/>

##### DAAM Heatmap Overlay:
<img src="https://github.com/Sayefalikhan03/MWE-Stable-Diffusion-Interpretation/blob/main/image_with_overlay.png" alt="Spill the Beans - DAAM Overlay" width="300"/>

## Dependencies

### Python Libraries
- **torch**: PyTorch for Stable Diffusion.
- **transformers**: Hugging Face library for model loading.
- **cv2**: OpenCV for image processing.
- **matplotlib**: Visualization of heatmaps and outputs.
- **pandas**: Dataset handling.

### Environment
- **Google Colab (recommended)**: Provides a GPU-powered environment for running the notebook.

## Acknowledgments
This repository relies on the following resources:
- **[MWE-CWI Dataset](https://github.com/ekochmar/MWE-CWI/blob/master/final_MWE_dataset.tsv)**: A publicly available dataset for identifying and evaluating multi-word expressions (MWEs).
- **[Stable Diffusion](https://stability.ai/)**: A cutting-edge latent diffusion model by Stability AI and Hugging Face.
- **DAAM**: A visualization tool for attention attribution in diffusion models.

## License
This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.



## Setup and Usage

### Clone the Repository

```bash
git clone https://github.com/your-username/MWE-Stable-Diffusion-Interpretation.git
cd MWE-Stable-Diffusion-Interpretation
