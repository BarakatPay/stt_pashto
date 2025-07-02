# Speech-to-Text Finetuned Model



---

## 🎯 Task

We fine-tuned a **Wav2Vec2-XLS-R-300M-Pashto** model on a custom Pashto Voice subset. The goal is to build a robust end-to-end ASR system for Pashto, suitable for both read and conversational speech.

---

## 📈 Baseline Results

We evaluated on a held-out test set (see `data/test.json`) and achieved:

| Metric                       | Score           |
|------------------------------|-----------------|
| **Word Error Rate (WER)**    | 31.19 %         |
| **Character Error Rate (CER)** | 9.43 %         |



## 🚀 Ongoing Improvements (We Are Considering)

To push our Pashto ASR even further, we are actively exploring:

1. **Orthographic Normalization**  
   Ensuring a consistent treatment of zero-width non-joiners (ZWNJ) and spacing in both reference transcripts and model outputs to eliminate trivial word-boundary mismatches.

2. **Lexicon & Name-List Augmentation**  
   Incorporating a small, curated lexicon of proper nouns (e.g., “جېمز دارمستتر”, “ډاکټر براون”) into a post-processing step that corrects or rescues rare names and loan-word spellings.

3. **External Language-Model Rescoring**  
   Integrating a Pashto n-gram or lightweight Transformer LM during beam-search to re-score CTC hypotheses, favoring linguistically valid sequences and reducing letter-swap errors.

4. **Data Augmentation**  
   Expanding our training set with noise injection, speed perturbation, and targeted examples of challenging tokens (especially proper names and orthographically ambiguous words) to improve robustness.


---

## 📚 References

- [Wav2Vec2 Documentation](https://huggingface.co/docs/transformers/model_doc/wav2vec2)  
---
