# Tiny-GPT

A small, educational GPT-style language model implemented in PyTorch. It learns to predict the next word in a short, handcrafted text corpus and generates text one token at a time.

This project is intended to make the core building blocks of a transformer easier to explore in a compact codebase.

## Features

- Word-level tokenization and vocabulary built from the sample corpus
- Learned token and positional embeddings
- Causal, masked self-attention with multiple attention heads
- Feed-forward layers, residual connections, and layer normalization
- Next-token training with cross-entropy loss
- Autoregressive text generation by sampling predicted tokens

## Project files

- `demo.py` — defines the TinyGPT model, trains it, and generates a sample
- `transformer_blocks.py` — implements attention, feed-forward, and transformer block modules

## Requirements

- Python 3
- PyTorch

Install PyTorch using the instructions for your platform at [pytorch.org](https://pytorch.org/get-started/locally/). For many environments, this also works:

```bash
pip install torch
```

## Run

From the project directory, run:

```bash
python demo.py
```

The script prints the PyTorch/CUDA environment, trains the model for 1,500 steps, reports periodic loss values, and generates a short sequence starting from `hello`.

## Configuration

Training and model settings—including the context length, embedding size, number of attention heads and layers, learning rate, and number of training steps—are defined near the top of `demo.py`.

The training corpus is a small list of example sentences in `demo.py`. Because the dataset and model are intentionally tiny, generated text is experimental and may not be coherent.

## Learning note

This is a minimal learning project, not a production language model. It uses a small word-level vocabulary and a tiny hardcoded dataset; it does not include a tokenizer package, pretrained weights, checkpointing, or a full training/data pipeline.