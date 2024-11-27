# MWE-Stable-Diffusion-Interpretation

This repository contains the source code, dataset, and implementation details for the research titled:  
**"Interpreting Multi-Word Expressions in Text-to-Image Generation: A Cross-Attention Approach Using Stable Diffusion."**

The project explores the challenges and methodologies of generating meaningful visual representations for Multi-Word Expressions (MWEs) using Stable Diffusion 2.1 and Diffusion Attention Attribution Maps (DAAM).

---

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Code Overview](#code-overview)
4. [Results](#results)
5. [Usage](#usage)
6. [Dependencies](#dependencies)
7. [Acknowledgments](#acknowledgments)
8. [License](#license)

---

## Introduction

Multi-Word Expressions (MWEs) often carry complex, idiomatic, or abstract meanings, making their interpretation challenging for generative AI models. This project aims to evaluate how Stable Diffusion handles MWEs through:
- Prompt engineering techniques.
- Visualization using DAAM to interpret cross-attention mechanisms.
- Quantitative evaluation using Intersection over Union (IoU) and coverage metrics.

The findings shed light on the limitations and potential improvements for generative AI systems in handling linguistically complex expressions.

---

## Dataset

The dataset used in this study is based on the publicly available **[MWE-CWI dataset](https://github.com/ekochmar/MWE-CWI/blob/master/final_MWE_dataset.tsv)**. It has been extended to include structured prompts for text-to-image generation.

### Files Included:
1. **`final_MWE_dataset_with_prompts.xlsx`**: 
   - Contains the MWEs, contexts, and corresponding prompts used in the study.
   - Includes additional annotations for complexity scores and supersenses.
   
2. **Link to the Original Dataset**: [MWE-CWI Dataset](https://github.com/ekochmar/MWE-CWI/blob/master/final_MWE_dataset.tsv)

---

## Code Overview

The repository includes several Colab notebooks and scripts used for the study. Below is a breakdown of the key files:

### 1. **`prompt_engineering.ipynb`**
   - Description: Generates structured prompts for Stable Diffusion based on MWEs and their contexts.
   - Key Features:
     - Token limit handling (< 77 tokens).
     - Incorporates contextual and emotional details for better semantic alignment.

### 2. **`image_generation.ipynb`**
   - Description: Uses Stable Diffusion 2.1 to generate images based on prompts.
   - Workflow:
     - Text embedding via CLIP encoder.
     - Latent diffusion and image decoding.

### 3. **`daam_visualization.ipynb`**
   - Description: Visualizes attention overlays (DAAM) to understand how Stable Diffusion allocates attention during image generation.
   - Outputs: Heatmaps showing attention alignment with MWEs.

### 4. **`iou_evaluation.ipynb`**
   - Description: Quantitatively evaluates alignment using IoU and coverage metrics.
   - Outputs:
     - IoU scores between DAAM overlays and ground-truth annotations.
     - DAAM and ground-truth coverage statistics.

---

## Results

The repository includes sample outputs and visualizations generated during the study:
1. **Generated Images**: Visual representations for MWEs like "take credit" and "spill the beans."
2. **DAAM Overlays**: Heatmaps showcasing attention distributions.
3. **Evaluation Metrics**:
   - IoU scores.
   - DAAM and ground-truth coverage percentages.

---

## Usage

### Running the Code
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/MWE-Stable-Diffusion-Interpretation.git
   cd MWE-Stable-Diffusion-Interpretation
