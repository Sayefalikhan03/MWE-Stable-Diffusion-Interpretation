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

This section includes visual examples of the model's outputs for selected MWEs.

#### Example:
1. **Generated Image for "Spill the Beans"**:
   ![Generated Image for "Spill the Beans"](images/spill_the_beans_image.png)

2. **DAAM Heatmap Overlay**:
   ![DAAM Heatmap for "Spill the Beans"](images/spill_the_beans_heatmap.png)

---

## Setup and Usage

### Clone the Repository

```bash
git clone https://github.com/your-username/MWE-Stable-Diffusion-Interpretation.git
cd MWE-Stable-Diffusion-Interpretation
