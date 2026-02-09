# Assignment 1: Bigram Language Model with Beam Search

## Overview

This project implements a **Bigram Language Model** with **Beam Search** for sentence generation, as part of an Artificial Intelligence course assignment.

## Features

- **Bigram Graph Extraction**: Constructs a probability graph from a corpus of sentences
- **Beam Search V1**: Basic beam search algorithm for finding high-probability sentences
- **Beam Search V2**: Enhanced beam search with **length normalization** to address brevity bias

## Project Structure

```
├── src/
│   ├── Assignment1Main.py  # Main entry point and testing
│   ├── BeamSearch.py       # Beam search implementations (V1 & V2)
│   ├── ExtractGraph.py     # Bigram graph extraction from corpus
│   └── StringDouble.py     # Data structure for (sentence, score) pairs
├── output.txt              # Sample output from running the program
└── task3.txt               # Analysis of length-normalization effects
```

## How It Works

1. **Graph Extraction**: Reads sentences from a corpus and builds a bigram probability model where each edge represents P(next_word | current_word)

2. **Beam Search V1**: Standard beam search that maintains top-k candidates at each step, selecting sentences with highest log-probability

3. **Beam Search V2**: Introduces a lambda parameter for length normalization:
   ```
   score = log P(y|x) / |y|^λ
   ```
   This counteracts the brevity bias inherent in basic beam search

## Key Findings (Task 3)

- **Low λ (0.7-0.9)**: Produces concise, coherent sentences
- **High λ (1.5-3.0)**: Encourages longer sentences, but may cause repetitive patterns
- **Optimal balance**: λ ≈ 0.7 provides good balance between length and coherence

## Requirements

- Python 3.x
- No external dependencies required

## Usage

```bash
cd src
python Assignment1Main.py
```

## License

This project is created for educational purposes.
