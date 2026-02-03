# Custom Text Augmentation Library

This project implements a custom text augmentation library designed for
Natural Language Processing (NLP) and AI training pipelines.

The library provides multiple classical text augmentation techniques
implemented from scratch using linguistic and rule-based approaches.

---

## 🚀 Project Overview

Text augmentation is commonly used to increase dataset diversity and
improve model robustness when training NLP models.

This project focuses on:
- Understanding how augmentation techniques work internally
- Implementing them with clean, configurable, and reproducible code
- Handling real-world edge cases such as acronyms and proper nouns

---

## 🧠 Implemented Augmentation Techniques

- **Synonym Replacement** (WordNet-based)
- **Random Deletion** (noise simulation)
- **Random Insertion**
- **Random Swap**
- **Back Translation** (via Google Translate)

Each method supports:
- Configurable parameters
- Random seed control for reproducibility
- Safe handling of punctuation and edge cases

---

## Example Usage

```python
from textaugmentor import TextAugmentor

augmentor = TextAugmentor()

augmentations = augmentor.augment(
    "The movie was really good and entertaining.",
    num_aug=3,
    seed=42
)

for text in augmentations:
    print(text)

---

## Known Limitations

- **WordNet synonyms:** May produce archaic/unnatural words
- **Best for:** Classification, sentiment analysis, low-data NLP
- **Not for:** Creative writing, grammar-perfect generation
- **Random Swap**
