# README: English-Persian Subtitle Translation System with NLP

![NLP](https://img.shields.io/badge/NLP-Transformers-blue) 
![License](https://img.shields.io/badge/License-MIT-green)

## 🌟 Project Overview
**Goal**: Build a high-quality English-Persian machine translation system optimized for **subtitle generation**, leveraging NLP and transformer models (mT5, mBART50). Designed to translate multimedia dialogues accurately and fluently.

**Impact**: Enhances accessibility for education, commerce, customer service, and media/entertainment.

---

## 📂 Dataset
**Source**: [parsinlu_translation_en_fa](https://huggingface.co/datasets/persiannlp/parsinlu_translation_en_fa) (Hugging Face)  
- Bilingual sentence pairs (English-Persian)
- Curated for machine translation tasks
- Prevents issues faced with noisy YouTube mono-lingual subtitles

---

## 🛠️ Technical Implementation
### Key Steps:
1. **Model Exploration**:
   - Tested RNNs, LSTMs, Seq2Seq (with Attention), and Transformers.
   - **Final Choice**: Fine-tuned **mBART50** (outperformed mT5 due to architecture advantages).

2. **Fine-Tuning**:
   - **mT5-small**: Tested freezing encoder layers (3–6 epochs, batch size 16).  
     *Best config*: Unfreezing last 6 encoder layers + 150K dataset.
   - **mBART50**: Full fine-tuning (all 12 encoder/decoder layers unfrozen, 100K dataset).

3. **Challenges**:
   - Limited computational resources (optimized with gradient checkpointing).
   - Overfitting mitigated via dropout, early stopping, and regularization.

---

## 📊 Results
- **mBART50** achieved **BLEU score** improvements of **15%** over baseline models.
- Generated subtitles preserved context and idiomatic expressions (e.g., translating "It's raining cats and dogs" → "باران شدیدی میبارد").

---

## 🚀 Installation
```bash
pip install transformers datasets torch sentencepiece
