# License Plate Detection using YOLOv11

This project implements a **custom-trained YOLOv11n** model for **vehicle license plate detection**.  
It focuses on **object detection** and achieves high accuracy on a real-world dataset.

---

## 📌 Project Overview

This project demonstrates how **YOLOv11n** can accurately **detect license plates** in varied scenarios,  
forming the foundation for **Automatic Number Plate Recognition (ANPR)** systems.

---

## 📂 Dataset

- **Source**: Roboflow – License Plate Recognition Dataset
- **Images**: 10,125 (Annotated)
- **Split**:
  - Train: 7,057
  - Validation: 2,048
  - Test: 1,020
- **Preprocessing**:
  - Resized to `640x640`
  - Normalized to `[0,1]`
  - Converted to **YOLOv11 format**

---

## 🛠️ Tech Stack

- Python
- YOLOv11 (Ultralytics)
- OpenCV
- Pandas & Matplotlib
- Google Colab for Training

---

## 📈 Model Training

- Model: **YOLOv11n** (lightweight & real-time)
- Epochs: 50
- Batch Size: 16
- Image Size: 640x640

```bash
# Training in Colab
!yolo task=detect mode=train model=yolo11n.pt \
     data=/content/License-Plate-Recognition-11/data.yaml \
     epochs=50 batch=16 imgsz=640 plots=True
```

---

## 📊 Results

| Metric    | Score |
| --------- | ----- |
| Precision | 0.983 |
| Recall    | 0.947 |
| mAP50     | 0.975 |
| mAP50-95  | 0.717 |

## 📥 Installation & Usage

1. Clone this repository:

```bash
git clone https://github.com/YOUR_USERNAME/number-plate-recognition.git
cd number-plate-recognition
```

2. Install dependencies:

```bash
pip install ultralytics opencv-python pandas
```

3. Run inference on an image:

```python
from ultralytics import YOLO
model = YOLO("models/best.pt")
results = model.predict(source="sample_image.jpg", conf=0.5)
results[0].show()
```

---

## 🚀 Future Work

- Integrate **OCR (Tesseract / CRNN / PaddleOCR)** for full ANPR
- Add **multi-frame vehicle tracking and logging**
- Develop **real-time parking or traffic analytics dashboard**
