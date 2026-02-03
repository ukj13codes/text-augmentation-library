# Custom Text Augmentation Library

This project implements a custom text augmentation library designed for
Natural Language Processing (NLP) and AI training pipelines.

The library provides multiple classical text augmentation techniques
implemented from scratch using linguistic and rule-based approaches.

---

## Project Overview

Text augmentation is commonly used to increase dataset diversity and
improve model robustness when training NLP models.

This project focuses on:
- Understanding how augmentation techniques work internally
- Implementing them with clean, configurable, and reproducible code
- Handling real-world edge cases such as acronyms and proper nouns

---

## Implemented Augmentation Techniques

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
```

---

## **Known Limitations & Design Decisions**

### **Synonym Quality**
Synonym replacement relies on **NLTK's WordNet**, a dictionary-based lexical database.

**May produce**:
- **Archaic/uncommon synonyms**
- **Technically correct but unnatural** replacements (e.g., "full" → "good")

> **Note**: Inherent to all rule-based WordNet augmentation libraries

### **Augmentation Philosophy**
**Goal**: **Data diversity > perfect fluency**

**Benefits of "slightly unnatural" text**:
- **Improves model robustness**
- **Reduces overfitting** 
- **Simulates noisy real-world text**

### **Applicability**

**Best for**:
- **Text classification**
- **Sentiment analysis**
- **Topic modeling**
- **Low-resource NLP datasets**

**Less suitable**:
- **High-quality text generation**
- **Grammar-sensitive applications**
- **Creative/literary rewriting**

**Production fluency**: Use **BERT/T5/GPT** models

---

## **What I Learned**

- **NLP preprocessing**: Tokenization + POS tagging
- **WordNet-based** lexical augmentation
- **Quality vs diversity** trade-offs
- **Configurable/reproducible** ML utilities
- **Real-world text** edge cases

---

## **Future Improvements**

- **Context-aware** augmentation (transformers)
- **Domain-specific** synonym filtering
- **Hugging Face** pipeline integration
- **Web/GUI** interface (Streamlit/Gradio)

