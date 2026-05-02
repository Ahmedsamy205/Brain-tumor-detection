# 🧠 Brain Tumor Detection using Deep Learning

A Computer Vision project that detects the presence of brain tumors in MRI scans using Convolutional Neural Networks (CNN) and Transfer Learning with MobileNetV2.

---

## 📌 Problem Statement

Brain tumor detection from MRI images is a critical medical task that requires expert radiologists and is time-consuming. This project automates the detection process using deep learning, classifying MRI scans as either **Tumor** or **No Tumor**.

---

## 📊 Dataset

- **Source:** [Brain MRI Images for Brain Tumor Detection – Kaggle](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)
- **Classes:** `yes` (tumor detected) / `no` (no tumor)
- **Format:** MRI images (JPG/PNG)

> Dataset is not included in this repo. Download it directly from Kaggle using the notebook setup instructions.

---

## 🧠 Models Used

Two approaches were explored and compared:

| Model | Architecture | Val Accuracy |
|-------|-------------|--------------|
| Custom CNN | Conv2D + MaxPooling + Dense | ~82% |
| MobileNetV2 (Transfer Learning) | Pretrained ImageNet + Fine-tuning | **~92%** |

---

## 🔧 Tech Stack

- **Language:** Python 3
- **Deep Learning:** TensorFlow / Keras
- **Pretrained Model:** MobileNetV2 (ImageNet weights)
- **Data Handling:** ImageDataGenerator
- **Platform:** Google Colab

---

## ⚙️ How It Works

1. **Data Loading** – MRI images are loaded from Kaggle and split into train/validation sets using `ImageDataGenerator`
2. **Preprocessing** – Images resized to `128x128`, normalized, and augmented
3. **Model 1: Custom CNN** – Built from scratch using Conv2D, MaxPooling, Dropout, and Dense layers
4. **Model 2: MobileNetV2** – Pretrained base frozen, custom classification head added (GlobalAveragePooling → Dense 128 → Dropout 0.5 → Sigmoid output)
5. **Training** – Adam optimizer, Binary Crossentropy loss, EarlyStopping callback
6. **Evaluation** – Compared accuracy and loss curves between both models

---

## 🚀 Getting Started

### 1. Open in Google Colab
Click the notebook file `Untitled49.ipynb` and open it in Colab.

### 2. Setup Kaggle API
Upload your `kaggle.json` file when prompted to download the dataset automatically.

### 3. Run All Cells
The notebook will:
- Download and extract the dataset
- Train the Custom CNN
- Train MobileNetV2 with Transfer Learning
- Display accuracy/loss results

---

## 📁 Project Structure

```
brain-tumor-detection/
│
├── Brain_Tumor_Detection.ipynb   # Main notebook
└── README.md                     # Project documentation
```

---

## 📈 Results

- **MobileNetV2** outperformed the custom CNN, reaching **~92% validation accuracy**
- Transfer Learning proved significantly more effective on this small medical dataset
- EarlyStopping prevented overfitting and selected the best model weights

---

## 🔮 Future Improvements

- Try other architectures (EfficientNetB0, ResNet50)
- Add Grad-CAM visualization to highlight tumor regions
- Deploy as a Flask or Streamlit web app
- Expand dataset for better generalization

---

## 👨‍💻 Author

**Ahmed Samy Sobhi**  
AI & Machine Learning Engineering Student – Menofia National University  
📧 ahmedsamyy224@gmail.com

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).
