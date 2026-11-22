# French Liaison Detection

Automatic detection of French liaisons in read speech, at the phoneme level.

**Live page:** https://yasineert.github.io/french-liaison-detection/

## Overview

The system compares the phonemes a reader *should* produce with the phonemes they *actually* produce, then labels each liaison as realised (VL) or omitted (XL).

1. **Reference**: eSpeak NG phonemization plus liaison rules
2. **Recognition**: fine-tuned CTC model (WavLM Base Plus) predicts phonemes from audio
3. **Alignment**: reference and prediction are aligned around each liaison site
4. **Decision**: realised / omitted, with learner feedback

## Applications

| Application | Purpose | Stack |
|---|---|---|
| LiaisonCheck | Corpus annotation, audio analysis, model benchmarking | React · Express · PostgreSQL · FFmpeg |
| Liaison et Moi | Pronunciation trainer with per-liaison feedback | React · Node.js · WavLM · SQLite |
| Model comparator | Side-by-side checkpoint comparison | Python · PyTorch · Transformers |

## Results (phoneme error rate)

| Model | First run (3 epochs) | Final run | Epochs |
|---|---|---|---|
| WavLM Base → Base Plus | 15.69% | **7.247%** | 10 |
| Wav2Vec2 Base | 14.02% | 7.813% | 10 |
| HuBERT Base LS-960 | 18.35% | 9.757% | 5.5 |

## Source code

This is a research project. The source code, corpus, audio recordings and trained checkpoints are private. This repository hosts the public presentation page.
