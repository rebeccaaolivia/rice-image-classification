# Rice Image Classification Project
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.18.0-orange)](https://www.tensorflow.org/)
[![Python](https://img.shields.io/badge/Python-3.11+-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Accuracy](https://img.shields.io/badge/Accuracy-99.57%25-brightgreen)]()

## 📌 Project Overview
A deep learning project for classifying 5 types of rice grains using Convolutional Neural Network (CNN). Developed as part of Dicoding's **"Belajar Fundamental Deep Learning"** certification. Achieves **99.57% test accuracy** using TensorFlow/Keras and supports deployment across multiple platforms including SavedModel, TF-Lite, and TensorFlow.js.

## 🌾 Dataset
**Rice Image Dataset - Kaggle**  
[![Dataset](https://img.shields.io/badge/Dataset-Kaggle-blue)](https://www.kaggle.com/datasets/muratkokludataset/rice-image-dataset)

| Split        | Images | Classes |
|--------------|--------|---------|
| **Training** | 52,500 | 5       |
| **Validation** | 11,245 | 5       |
| **Test**     | 11,255 | 5       |

**Classes:** `'Basmati'`, `'Jasmine'`, `'Arborio'`, `'Ipsala'`, `'Karacadag'`

## 🧠 Model Architecture
```
model = Sequential([
    Conv2D(32, (3, 3), activation='relu', input_shape=(150, 150, 3)), # Changed input_shape
    MaxPooling2D(2, 2),
    Conv2D(64, (3, 3), activation='relu'),
    MaxPooling2D(2, 2),
    Conv2D(128, (3, 3), activation='relu'),
    MaxPooling2D(2, 2),
    Conv2D(256, (3, 3), activation='relu'), 
    MaxPooling2D(2, 2),
    Flatten(),
    Dense(512, activation='relu'), 
    Dropout(0.5),  
    Dense(5, activation='softmax')  
])
```

## 🏆 Performance Metrics
| Metric              | Score  |
| ------------------- | ------ |
| Training Accuracy   | 99.65% |
| Validation Accuracy | 99.63% |
| Test Accuracy       | 99.57% |
| Test Loss           | 0.0134 |

🔍 Explanation:
* Training Accuracy (99.65%): Indicates the model learned the training data extremely well.
* Validation Accuracy (99.63%): Shows that the model also performs consistently on unseen validation data during training, suggesting no overfitting.
* Test Accuracy (99.57%): The final evaluation metric on a fully unseen test set. This confirms the model's ability to generalize well to new data.
* Test Loss (0.0134): A very low loss value, indicating the model makes predictions that are very close to the true labels.

✅ Conclusion: These metrics demonstrate a highly accurate and robust model suitable for deployment across platforms.


## 📊 Training & Validation Visualization
<p align="center"> <img src="https://github.com/user-attachments/assets/05b69189-00ca-4d71-95f6-ab206be1b28d" width="600" alt="Training and Validation Metrics"> </p> <p align="center"> <em>Figure 1. Training and validation accuracy and loss over 9 epochs</em> </p>

🔍 Explanation:
* The left plot shows model accuracy on both training and validation datasets.
   * Accuracy increases rapidly and stabilizes near 99%, indicating strong performance without signs of overfitting.

* The right plot shows the loss values, which steadily decrease for both training and validation.
   * Low and stable validation loss suggests good generalization to unseen data.

✅ Conclusion: The model learns effectively and consistently, with no sign of overfitting or underfitting.

## 🔍 Inference Examples (TF-Lite)
<p align="center"> <img src="https://github.com/user-attachments/assets/a5fde310-ddf2-423f-bac2-805af5dd18ae" width="800" alt="Inference Results"> </p> <p align="center"> <em>Figure 2. Example predictions using the converted TF-Lite model</em> </p>

🔍 Explanation:
* The model was exported to TensorFlow Lite (TF-Lite) and used for inference on 10 unseen test images.
* All predictions are labeled as “Basmati”, matching the visual characteristics of the test samples.
* The predicted class is shown above each image: "Prediction: Basmati".

✅ Conclusion: The converted TF-Lite model performs accurately and reliably, demonstrating successful deployment and compatibility with lightweight platforms like mobile.

## 🛠️ Requirements
To run this project, you'll need:
- Python 3.7+
- TensorFlow 2.13+
- Kaggle API
- Other dependencies listed in [requirements.txt](https://github.com/rebeccaaolivia/rice-image-classification/blob/main/requirements.txt)

Install requirements with:
```
!pip freeze > requirements.txt
print("requirements.txt generated!")
```

## ✅ Dicoding Submission Checklist
1. \>1000 images dataset ✔️
2. Original dataset ✔️
3. Proper train/val/test split ✔️
4. Sequential + Conv2D model ✔️
5. \>85% accuracy (Achieved 96.97%) ✔️
6. Accuracy/loss plots ✔️
7. SavedModel/TFLite/TFJS exports ✔️

## Future Improvements
1. Implement data augmentation to improve generalization
2. Experiment with transfer learning using pre-trained models
3. Add more vegetable classes
4. Develop a web/mobile interface for easy classification

## 👩‍💻 Author  
**Rebecca Olivia Javenka Br. Manurung**  
📧 Email: [rebeccaolivia1601@gmail.com](mailto:rebeccaolivia1601@gmail.com)  
👤 Dicoding ID: [rebeccaolivia](https://www.dicoding.com/users/rebeccaolivia)
