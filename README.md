# HPI KI Service Centre - Fine-Tuning Large Language Models for Video Game Localization


## Overview

This research project investigates whether Large Language Models (LLMs) can improve machine translation quality for creative content, specifically video game localization. Traditional machine translation systems often produce literal translations that fail to capture stylistic nuances, humor, idioms, and wordplay, resulting in substantial post-editing effort by professional translators.

The project evaluates whether domain-specific fine-tuning of open-source LLMs can bridge this gap and achieve translation quality comparable to professional human translators.

---

## Research Goals

The project focused on three main objectives:

- Evaluate the translation capabilities of modern LLMs for English-to-German video game localization.
- Determine whether fine-tuned open-source models can outperform commercial translation systems and proprietary LLMs.
- Develop a scalable approach for adapting translation models to new domains and language pairs.

---

## Background

While recent advances in machine translation have significantly improved translation accuracy, creative domains remain challenging. Video games frequently contain:

- Idioms and colloquial expressions
- Humor and puns
- Character-specific writing styles
- Context-dependent language

Conventional machine translation systems often translate such content literally, preserving grammatical correctness while losing intended meaning and tone.

Large Language Models have demonstrated strong zero-shot translation abilities, motivating an investigation into whether domain-specific fine-tuning can further improve performance.

---

## Dataset

The research was conducted using a large-scale professional localization corpus consisting of more than **144 million words** of parallel translation data.

During this project, fine-tuning experiments were successfully scaled to:

- Up to **1 million translation segments**
- Approximately **12 million words** of training data

This represents a substantial increase over previous experiments and helped overcome earlier issues with catastrophic forgetting during fine-tuning.

---

## Methodology

The study compared:

- ChatGPT-4
- ChatGPT-5-mini
- Base Gemma-3 27B-it
- Multiple fine-tuned Gemma-3 27B-it variants

The base Gemma model was fine-tuned on progressively larger datasets ranging from 5,000 to 1,000,000 translation segments. 
Models were evaluated on professionally curated test sets containing stylistically challenging text, puns and creative language.
Translation quality was assessed using BLEU, chrF, TER metrics

Additionally, translations were reviewed by professional in-house translators.

---

## Key Findings



| Model            |    BLEU ↑ |    chrF ↑ |     TER ↓ |
| ---------------- | --------: | --------: | --------: |
| Gemma-3 27B      |     73.46 |     76.15 |     43.20 |
| Fine-Tuning 5k   |     76.71 |     79.58 |     37.08 |
| Fine-Tuning 50k  |     80.51 |     82.93 |     28.40 |
| Fine-Tuning 100k |     79.31 |     82.33 |     29.98 |
| Fine-Tuning 500k |     82.64 |     84.86 |     24.06 |
| Fine-Tuning 1M   | **83.41** | **86.91** | **23.67** |
| ChatGPT-4        |     71.85 |     75.12 |     47.14 |
| ChatGPT-5 Mini   |     72.39 |     73.02 |     45.76 |

| Model            |    BLEU ↑ |    chrF ↑ |     TER ↓ |
| ---------------- | --------: | --------: | --------: |
| Gemma-3 27B      |     78.59 |     77.50 |     44.13 |
| Fine-Tuning 5k   |     82.90 |     83.59 |     31.01 |
| Fine-Tuning 50k  |     82.84 |     83.74 |     30.17 |
| Fine-Tuning 100k |     84.53 |     85.49 |     25.14 |
| Fine-Tuning 500k |     86.42 |     87.77 |     24.30 |
| Fine-Tuning 1M   | **87.93** | **89.10** | **20.95** |
| ChatGPT-4        |     79.09 |     77.08 |     41.34 |
| ChatGPT-5 Mini   |     78.69 |     75.69 |     44.97 |

**Metrics:** Higher BLEU and chrF scores indicate better translation quality. Lower TER scores indicate fewer edits required to match the reference translation.

**Training Data:** The number following each fine-tuning model indicates the number of translation segments used during training (e.g., 5k = 5,000 segments, 100k = 100,000 segments, 1M = 1,000,000 segments).

### Fine-Tuning Significantly Improves Translation Quality

Fine-tuned models consistently outperformed their base counterparts across all evaluation metrics.

### More Training Data Led to Better Results

Translation quality improved as the size of the fine-tuning dataset increased. The best-performing model was trained on the largest dataset evaluated.

### Open-Source Models Can Compete with Commercial Systems

After domain-specific fine-tuning, the open-source Gemma-3 model surpassed:

- ChatGPT-4
- ChatGPT-5-mini
- DeepL

on all evaluated benchmark datasets.

### Near-Human Translation Quality

Professional translators rated the best-performing model's output as **near human quality**.

---


## Future Research

Planned future work includes:

- Expanding evaluation to 12 language pairs
- Testing additional video game franchises
- Evaluating newer open-weight models such as Gemma 4 and Qwen 3
- Further improving translation quality through larger fine-tuning datasets

---

## Acknowledgements

This project was funded by the German Federal Ministry of Research, Technology and Space through the **KI-Servicezentrum Berlin-Brandenburg** initiative (Funding Code: 16IS22092).

The responsibility for the content of the research lies with the authors.
