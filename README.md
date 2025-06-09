# BARTX: Fast, Data-Efficient Text Line Recognition with Transformer LM

## 🧠 Overview

**BARTX** is a lightweight, modular system for post-OCR correction in noisy or low-resource document scenarios. Instead of relying on massive autoregressive OCR models like TrOCR or DTrOCR, BARTX combines a parallel, detection-based pipeline with a fine-tuned **BART** language model to enhance raw OCR outputs—dramatically improving both accuracy and speed.

This research targets a common bottleneck in document intelligence: the **fragility of OCR outputs in handwritten, historical, or degraded texts**. With just ~16K synthetic training lines, BARTX demonstrates that smart architecture—not scale—can drive performance.

---

## 🔍 Why It Matters

OCR failures are often the weak link in downstream NLP tasks like entity extraction, summarization, or classification. Rather than build an end-to-end model, BARTX **surgically improves OCR text post hoc** using a Transformer LM—yielding higher text fidelity, faster inference, and edge-readiness without retraining detection models.

---

## 🚀 Key Highlights

- ⚡ **76% Faster than TrOCR**  
  → *67 ms per line* (A6000, batch=1) vs *284 ms for TrOCR*

- 📉 **Competitive CER/WER** on noisy real-world handwriting

- 🧠 **Compact Architecture**  
  → ~139M parameters (Detector + BART-base)

- 📦 **Edge-Deployable**  
  → Parallel, modular, low memory footprint

---

## 📊 Comparison with SOTA

| Metric                | TrOCR             | DTrOCR         | **BARTX (Ours)**              |
|-----------------------|-------------------|----------------|-------------------------------|
| **Training Data**     | 684M–1B+ lines     | Billions       | ~16K lines (IAM synthetic)    |
| **Inference Speed**   | 284 ms/line       | 70–150 ms (est)| 69 ms/line (batch=1)          |
| **Model Size**        | 558M (TrOCR-Large)| 105M           | 139M (BART-base + lightweight detector) |
| **Deployment**        | Limited           | Moderate       | ✔ High (parallel + modular)   |

---

## 📌 Status

**Ongoing thesis-linked research** — architectural details and full results will be released post-publication.

---

## 🏷 Keywords

`OCR correction`, `sequence-to-sequence`, `BART`, `document intelligence`, `low-resource NLP`, `inference optimization`, `edge deployment`


