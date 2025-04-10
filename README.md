
# ✍️ Handwritten Word Recognition using CRNN + CTC

## 🔍 Overview
This project focuses on recognizing handwritten English words using a **Convolutional Recurrent Neural Network (CRNN)** architecture combined with **Connectionist Temporal Classification (CTC)** loss. The model is trained on the **IAM Handwriting Database**, which provides a rich set of handwritten word images and corresponding labels.

---

## 📚 Dataset
- **Name**: IAM Handwriting Database
- **Link**: [IAM Dataset](https://fki.tic.heia-fr.ch/databases/iam-handwriting-database)
- **Files Used**:
  - `words.tgz`: Contains word images
  - `words.txt`: Contains image-label mappings
- **Split**: Train (90%) | Validation (5%) | Test (5%)

---

## 🛠️ Preprocessing Steps
- Extracted and cleaned metadata from `words.txt`
- Filtered invalid or unreadable images
- Resized images to **128x32** and normalized
- Mapped characters to indices using `StringLookup`
- Created batched TensorFlow datasets for training/validation

---

## 🧠 Model Architecture
- **Input**: Grayscale image (128x32)
- **Layers**:
  - Convolutional layers + MaxPooling
  - Reshape layer
  - Dense Layer
  - 2x Bidirectional LSTM
  - Dense (num_chars) layer
- **Loss Function**: Connectionist Temporal Classification (CTC)

---

## 🏋️ Training Details
- **Epochs**: Configurable
- **Batch Size**: 64
- **Optimizer**: Adam
- **Callbacks**: Early stopping, model checkpointing
- **Evaluation Metric**: Edit Distance

---

## ✅ Results
| Sample Word | Ground Truth | Prediction |
|-------------|---------------|------------|
| Image 1     | "because"     | "becaus"   |
| Image 2     | "management"  | "management"|
| Image 3     | "reaction"    | "reation"  |

---

## 🎯 Challenges
- Variability in handwriting styles
- Alignment without segmentation
- Convergence of the CTC loss


---

## 🛠️ Tech Stack
- Python
- TensorFlow / Keras
- IAM Dataset
- NumPy, Matplotlib

---

