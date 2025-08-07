# Project 3: Supervised Learning for Text Summarization

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eeleoj62/DS_capstone/blob/main/Project_3_LLM/Project_3_fix_invalid.ipynb)

## Overview

This project applies state-of-the-art transformer models to **automatically summarize multi-turn dialogues** from messaging platforms such as Slack, Microsoft Teams, and WhatsApp. The motivation stems from the need to help users **quickly digest long, informal chat threads** in professional environments.

Two summarization models are developed, fine-tuned, and compared:
- **BERT2BERT** (EncoderDecoderModel using pre-trained BERT)
- **Pegasus** (`seddiktrk/pegasus-samsum` fine-tuned for summarization)

---

## Dataset

**SAMSum**: A publicly available dataset containing 15,000+ multi-speaker chat-style conversations with human-written summaries.

Each sample contains:
- `dialogue`: Multi-speaker informal chat (Slack/WhatsApp style)
- `summary`: Concise summary of the conversation

---

## Project Goals

1. Fine-tune and evaluate transformer-based summarization models.
2. Analyze dialogue and summary lengths, compression ratios, and structure.
3. Benchmark performance using ROUGE-1, ROUGE-2, ROUGE-L.
4. Enable experiment tracking with **MLflow** and ensure reproducibility.
5. Make recommendations for real-world deployment.

---

## Tools & Libraries

- Hugging Face Transformers & Datasets
- PyTorch
- Matplotlib / Seaborn
- `evaluate` (for ROUGE metrics)
- MLflow (for experiment tracking)
- Google Colab + Google Drive (optional for storage)

---

## Results

| Metric    | BERT2BERT | Pegasus |
|-----------|-----------|---------|
| ROUGE-1   | 0.4327    | 0.4789  |
| ROUGE-2   | 0.1885    | 0.2386  |
| ROUGE-L   | 0.3435    | 0.3917  |

**Pegasus** consistently outperformed BERT2BERT across all ROUGE metrics.

---

## 🔍 Key Observations

- BERT2BERT performed well despite not being built for text generation.
- Pegasus generated more fluent, accurate summaries with stronger overlap.
- Beam search and cosine LR scheduler helped improve generation quality.
- Compression ratios aligned closely between generated and human summaries.
- MLflow allowed full parameter and artifact tracking.

---

## Evaluation Strategy

- **Quantitative**: ROUGE-1, ROUGE-2, ROUGE-L
- **Qualitative**: Manual review of generated summaries for fluency, coverage, tone
- **Visual**: Histogram comparisons of dialogue vs. summary lengths, compression statistics

---

## Deployment Considerations

Once deployed, the model should be integrated into messaging platforms as a:

> **“Summarize Chat”** button per conversation thread.

This would allow users to instantly view a summary without reading the full thread.

---

## Future Improvements

- Collect user feedback (thumbs up/down, comments) to guide retraining
- Incorporate semantic metrics like **BERTScore**
- Build real-time summarization pipelines for Slack or Teams
- Add multilingual and personalized summary styles
- Explore fine-tuning dialogue-specific models from scratch

---

## Author

**Joseph Lee**  
Senior Quality Engineer | Aspiring Data Scientist  
jtlee326@gmail.com | [GitHub](https://github.com/eeleoj62)

---

## License

MIT License