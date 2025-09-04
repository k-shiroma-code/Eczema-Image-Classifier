# Eczema Multimodal Assistant

This project develops a multimodal deep learning assistant for **eczema (atopic dermatitis) assessment**.  
It combines **image classification** of skin lesions with **NLP analysis** of symptom descriptions to provide a joint prediction and interpretability outputs.  

> **Note:** This project is for educational and research purposes only and is **not intended for medical diagnosis**. Always consult a qualified healthcare professional for medical concerns.

---

## Project Overview

The assistant uses two complementary inputs:

1. **Image of the skin lesion**  
   - Uses transfer learning with **EfficientNet / Vision Transformer** models.  
   - Outputs probability of eczema vs non-eczema.  
   - Provides **Grad-CAM heatmaps** for interpretability.

2. **Text description of symptoms**  
   - Fine-tuned **BERT / ClinicalBERT** model classifies symptom text.  
   - Labels can include condition consistency (eczema / other / unclear) or severity levels (mild / moderate / severe).  
   - Extracts key symptom cues for explainability.

A **fusion layer** combines embeddings from both modalities to produce a final joint prediction, improving accuracy when either input is ambiguous.

---

## Features

- **Multimodal fusion:** Combines image and text for a holistic assessment.  
- **Interpretability:** Heatmaps highlight lesion areas; key symptom phrases provide context.  
- **Evaluation metrics:** AUROC, F1-score, sensitivity/specificity for both modalities and the fusion model.  
- **Robust preprocessing:**  
  - Image: resizing, color normalization, augmentation  
  - Text: tokenization, cleaning, padding/truncation  

---

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/eczema-multimodal-assistant.git
cd eczema-multimodal-assistant

# Create virtual environment
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

# Install dependencies
pip install -r requirements.txt
