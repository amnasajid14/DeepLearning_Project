# Evaluation of AI-based Face Inpainting Models for Forensic Wound Removal and Identity Preservation

## Overview

This project investigates whether existing pretrained face inpainting models can be repurposed as a practical baseline for forensic facial reconstruction in scenarios involving facial injuries, occlusions, or missing regions where conventional face recognition (FR) systems fail.

Due to the absence of publicly available paired injured-to-clean facial datasets and strict ethical constraints on forensic data sharing, this work focuses on **inference-based comparative analysis** rather than supervised training.

The study evaluates both **mask-based** and **prompt-based generative inpainting approaches** under controlled conditions to analyze reconstruction quality and identity preservation behavior.

## Key Contributions

- Systematic evaluation of pretrained inpainting models under forensic-inspired conditions
- Comparative analysis of **mask-guided** versus **prompt-guided** inpainting workflows
- Controlled benchmarking using fixed prompts, masks, random seeds, and inference parameters
- Identification of limitations in applying generic inpainting models to forensic face recovery

## Models Evaluated

- Stable Diffusion 1.5 (Inpainting)
- Stable Diffusion 2 (Inpainting)
- Stable Diffusion XL (Inpainting)
- LaMa (GAN-based baseline with OpenCV fallback)

## Setup Instructions

### Environment Setup

- Python **3.9 or later** is required.

- Create and activate a virtual environment:

  python -m venv venv
  source venv/bin/activate # Linux / macOS
  venv\Scripts\activate # Windows

- Install dependencies:

  pip install -r requirements.txt

## Usage

- Mask-Based Inpainting

  Provide:

  -> An injured facial image
  -> A binary mask (white = inpaint region, black = preserve region)

Run inference:

python inpainting_benchmark.py --image path/to/image.png --mask path/to/mask.png

- Prompt-Based Inpainting

  Provide:

  -> An injured facial image
  -> An identity-preserving textual prompt

Run inference:

python inpainting_benchmark.py --image path/to/image.png --prompt "identity preserving facial reconstruction"

## Evaluation Strategy

- Qualitative Evaluation

  1.Visual inspection of reconstructed facial regions
  2.Analysis of identity consistency, boundary blending, and perceptual realism

- Quantitative Metrics (Baseline Only)

  1.PSNR (Peak Signal-to-Noise Ratio)
  2.SSIM (Structural Similarity Index)

These metrics are reported as supplementary indicators only and do not directly represent identity preservation.

## Limitations

1.Lack of ground-truth healed facial images
2.No identity-specific supervision
3.Results are feasibility-oriented, not forensic-certified

## Future Work

1.Identity-based evaluation using ArcFace embeddings
2.Ethical construction of expert-annotated forensic datasets
3.Development of injury-aware identity-preserving inpainting architectures
4.Human perceptual evaluation studies

## Authors

Amna Sajid
Hareem Fatima
