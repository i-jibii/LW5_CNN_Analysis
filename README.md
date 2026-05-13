# 🌿 LW5: Comparative Analysis of Pre-trained CNN Models
### **20-Species Moss Classifier Performance Study**

## 📌 Project Overview
This project performs a rigorous comparative study of three deep learning architectures—**VGG16**, **ResNet50**, and **MobileNetV2**—applied to a custom dataset of 20 moss species. By utilizing **Transfer Learning**, we evaluated which pre-trained "brain" is most effective for biological image classification.

---

## 📊 PART 12: Performance Comparison Table

| Model Architecture | Train Acc | Test Acc | Test Loss | Precision | Recall | F1-score | AUC Score |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **VGG16** | 29.35% | 36.14% | 2.34 | 0.39 | 0.36 | 0.33 | 0.870 |
| **ResNet50** | 8.79% | 12.15% | 2.92 | 0.04 | 0.12 | 0.05 | 0.650 |
| **MobileNetV2** | **80.48%** | **91.74%** | **0.58** | **0.92** | **0.92** | **0.92** | **0.994** |

### **🏆 Evolutionary Comparison (The Journey)**
| Stage | Model Description | Accuracy |
| :--- | :--- | :--- |
| **Lab 2** | Teachable Machine (Initial) | ~30.00% |
| **Lab 3** | Custom CNN Baseline | 74.00% |
| **Lab 4** | EfficientNetB0 (Advanced) | 88.40% |
| **Lab 5** | **MobileNetV2 (Winner)** | **91.74%** |

---

## 🖼️ Visualizations
*(Note: Replace these placeholders with your actual exported images from Colab)*

1. **Confusion Matrix (MobileNetV2)**: Shows a strong diagonal line, indicating high precision across all 20 classes.
2. **ROC Curves**: MobileNetV2 achieved multiple AUC scores of 1.00.
3. **Grad-CAM**: Visual proof that the model identifies moss by focusing on leaf-tip textures.

---

## 🧠 GUIDE QUESTIONS (Final Reflection)

### **A. Model Performance**
1. **Highest Accuracy**: **MobileNetV2 (91.74%)**. Its use of "Depthwise Separable Convolutions" makes it highly efficient at learning texture features with fewer parameters, preventing the "vanishing gradient" problem seen in deeper models.
2. **Lowest Performance**: **ResNet50 (12.15%)**. Despite being a powerful model, its deep residual blocks often require longer training schedules (more epochs) or specific learning rate tuning to converge on specialized botanical datasets.
3. **Loss Comparison**: MobileNetV2 reached a low of **0.58**, while ResNet50 stayed high at **2.92**, indicating that MobileNetV2 successfully "minimized" its errors during the 10-epoch race.

### **B. Evaluation Metrics**
4. **Accuracy is not enough**: Because a model can have high accuracy by just guessing the "easiest" classes. F1-score and Precision ensure the model is reliable for *every* species, not just the common ones.
5. **Best F1-score**: **MobileNetV2 (0.92)**. This indicates that the model has high "Reliability" and "Completeness"—it rarely gives a false positive and rarely misses a true specimen.

### **C. Confusion Matrix Analysis**
7. **Misclassified**: Delicate fern moss and Cypress-leaved plait moss were sometimes swapped due to their similar feathery branching patterns.
8. **Patterns**: ResNet50 showed a "Vertical Bar" pattern, which is a sign of **Model Collapse**, where the model learns to ignore most classes and only predicts a few.

### **D. ROC and AUC**
9. **Highest AUC**: **MobileNetV2 (0.994)**.
10. **AUC meaning**: It measures the "Separability." An AUC of 0.99 means there is a 99% chance the model will correctly distinguish between a Broom Moss and a Peat Moss.

### **E. Explainability (Grad-CAM)**
11. **Revelation**: It revealed that MobileNetV2 focuses on **leaf density**, while weaker models were distracted by the background soil or the edges of the image.
13. **Meaningful Heatmaps**: MobileNetV2. Its heatmaps were sharp and perfectly aligned with the biological structure of the moss.

### **F. Model Comparison & Improvement**
14. **Recommendation**: **MobileNetV2**. It is the most "Deployment Ready" because it is lightweight, fast, and extremely accurate.
15. **Improvement**: Applying **Fine-Tuning** by unfreezing the top 20 layers of MobileNetV2 would likely push the accuracy above 95%.

### **G. Real-World Application**
16. **Application**: A mobile app for ecologists to identify moss species in real-time in protected forests.
17. **Risks**: Deploying an inaccurate model could lead to the misidentification of endangered species, potentially damaging environmental conservation efforts.
18. **Integration**: The model can be converted to **TensorFlow Lite (.tflite)** to run locally on an Android or iOS device without needing internet access.

