# MemoSen-Multimodal-Sentiment-Analysis
This repository presents a multimodal sentiment analysis framework for Bengali memes, integrating visual and textual representations through deep vision–language fusion. The system is designed to address the cultural, linguistic, and stylistic challenges of sentiment understanding in low-resource Bengali meme content.

The proposed model is evaluated on the MemoSen dataset and demonstrates significant improvements over pretrained vision–language baselines.

---

## 🔍 Overview

Bengali memes often contain:
- Embedded stylized text  
- Cultural references  
- Code-mixed language  
- Sarcastic or implicit sentiment cues  

To effectively capture these characteristics, we propose a **hybrid multimodal architecture** combining:
- **ResNet18** for image feature extraction  
- **BERT / BanglaBERT** for textual understanding  
- **Attention-based feature fusion** for cross-modal interaction  

---

## 🧠 Model Architecture

The system consists of the following components:

- **Image Encoder**  
  ResNet18 pretrained on ImageNet for extracting visual features.

- **Text Encoder**  
  BERT / BanglaBERT for modeling Bengali, English, and code-mixed captions.

- **OCR Module**  
  Extracts embedded Bengali text from memes using font-robust OCR.

- **Multimodal Fusion**  
  Concatenation and attention-based fusion of image and text embeddings.

- **Classification Head**  
  Fully connected layers with softmax activation for sentiment prediction.

- **Optimizer**  
  AdmW optimizer applied to enhance the performance.


  
**Sentiment Classes:**  
Positive · Neutral · Negative

---

## 📊 Dataset: MemoSen

The MemoSen dataset is a curated Bengali meme sentiment dataset containing visual content and textual captions.

### Dataset Statistics

| Category | Count |
|--------|-------|
| Total memes | 4,369 |
| Positive | 1,348 |
| Neutral | 291 |
| Negative | 2,730 |
| Bengali captions | 2,545 |
| English captions | 467 |
| Code-mixed captions | 1,357 |

---

## ⚙️ Experimental Setup

- **Backbones:** ResNet18 + BERT / BanglaBERT  
- **Fusion Strategy:** Attention-based and concatenation  
- **Loss Function:** Cross-entropy loss  
- **Optimizer:** AdamW  
- **Training:** Mixed precision, memory-aware batching  
- **Evaluation Metrics:** Accuracy, Macro-F1, Confusion Matrix  

---

## 📈 Results Summary

The proposed model outperforms:
- BLIP  
- CLIP  
- ViLT  
- Vision-only and Text-only baselines  

**Best Performance:**
- **Accuracy:** 86%  
- **Macro-F1:** 0.88  

Ablation studies confirm the importance of:
- Language-aware tokenization  
- Sequential text modeling  
- Attention-based multimodal fusion  

---

## 🧪 Ablation Studies

We analyze the contribution of each modality:
- Text-only  
- Image-only  
- Image + Text (no attention)  
- Full multimodal model  

Results are visualized using:
- Ablation bar plots  
- Modality contribution analysis  

---

## 📁 Repository Structure

```text
.
├── data/                   # Dataset splits and metadata
├── models/                 # ResNet18, BERT, fusion modules
├── ocr/                    # OCR processing utilities
├── training/               # Training and evaluation scripts
├── figures/                # Generated plots and diagrams
├── utils/                  # Helper functions
├── README.md
└── requirements.txt
```

---

## 🚀 Getting Started
### Installation
```bash
pip install -r requirements.txt
```
### Training
```bash
jupyter-notebook
```

## 📝 Paper

This repository accompanies the research paper:

Multimodal Sentiment Analysis of Bengali Memes Using Vision–Language Fusion
(Manuscript under submission)

## 🤝 Acknowledgements

- MemoSen dataset contributors
- Open-source communities behind PyTorch and Hugging Face
- Authors of ResNet and BERT

## 📜 License

This project is intended for academic and research use.
Please cite the paper if you use this code or dataset.

## 📌 Citation
```bibtex
@article{memosen_multimodal,
  title={Multimodal Sentiment Analysis of Bengali Memes Using Vision–Language Fusion},
  author={Souvik Pramanik, S.M. Riaz Rahman Antu, Atikul Munna, Md. Ibrahim Khalil, Shak Mohammad Abyad},
  journal={Under Review},
  year={2025}
}
```
