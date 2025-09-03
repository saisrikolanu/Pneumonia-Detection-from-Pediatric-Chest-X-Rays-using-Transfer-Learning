# Pneumonia Detection from Pediatric Chest X-Rays using Transfer Learning

**Course Project**  
**Author:** Sai Sri Kolanu (50594437)  
**University at Buffalo**  

---

## 📖 Overview
This project investigates **deep learning methods for pneumonia detection** in pediatric chest X-rays. We evaluate two pretrained convolutional neural network (CNN) architectures, **DenseNet121** and **Inception v3**, using transfer learning. Both models are fine-tuned on a curated pediatric dataset, and their performance is compared using **accuracy** and **ROC-AUC**.

---

## 📊 Dataset
- **Source:** [Pediatric Chest X-ray Dataset (Kermany et al., Guangzhou Women & Children’s Medical Center)](https://data.mendeley.com/datasets/rscbjbr9sj/2)  
- **Classes:** NORMAL, PNEUMONIA (bacterial + viral)  
- **Train/Validation/Test Split:**
  - Training: 5,216 images  
  - Validation: 10% of training set  
  - Test: 624 images  
- **Image Sizes:** Resized to 224×224 (DenseNet121) and 299×299 (Inception v3)  
- **Preprocessing:**
  - Normalization using ImageNet mean/std  
  - Random horizontal flip (training only)  
  - No rotations/crops to preserve anatomy  

---

## ⚙️ Methods
- **Transfer Learning**
  - DenseNet121 (7.98M parameters)  
  - Inception v3 (23.85M parameters)  
- **Framework:** PyTorch  
- **Optimizer:** Adam  
- **Loss:** Cross-entropy  
- **Batch Size:** 32  
- **Epochs:** 10  
- **Evaluation Metrics:** Accuracy, ROC-AUC, Confusion Matrix  

---

## 📈 Results
| Model        | Test Accuracy | ROC-AUC |
|--------------|--------------|---------|
| DenseNet121  | 69.4%        | 0.916   |
| Inception v3 | 75.8%        | 0.967   |

- **Inception v3** consistently outperformed DenseNet121, especially in ROC-AUC.  
- Inception had fewer false negatives — crucial in clinical settings where missed pneumonia cases are dangerous.  

---

## 🔬 Insights
- **DenseNet121**: Efficient with fewer parameters, but struggled with subtle high-resolution features.  
- **Inception v3**: Larger input size and multi-scale convolutions captured richer features → better generalization.  
- **Class imbalance** impacted performance; ROC-AUC provided a fairer evaluation.  

---

## 🛠️ Tech Stack
- **Python 3.x**
- **PyTorch**
- **Torchvision**
- **NumPy, Pandas**
- **Matplotlib, Seaborn**

---

## ▶️ How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/saisrikolanu/Pneumonia-Detection-from-Pediatric-Chest-X-Rays-using-Transfer-Learning.git
   cd saisrikolanu/Pneumonia-Detection-from-Pediatric-Chest-X-Rays-using-Transfer-Learning
