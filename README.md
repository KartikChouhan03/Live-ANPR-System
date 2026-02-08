# 🎥 Live ANPR System (Automatic Number Plate Recognition)

An end-to-end, real-time **Automatic Number Plate Recognition (ANPR)** system built using **YOLOv8**, **OpenCV**, and **Tesseract OCR**. This system captures live video, detects license plates, extracts text, and logs the results automatically.



---

## 📌 Project Overview
The **Live-ANPR-System** is designed to bridge the gap between computer vision and real-world utility. By combining deep learning for object detection with optical character recognition (OCR), it provides a robust solution for:
* 🚗 **Smart Parking Systems**
* 🚦 **Traffic Monitoring**
* 🛡️ **Security & Access Control**

---

## ⚙️ Key Features
* **Real-Time Detection:** High-speed license plate detection using a custom YOLOv8 model.
* **Automated OCR:** Plate text extraction with Tesseract OCR.
* **Image Preprocessing:** Uses Grayscale, Gaussian Blur, and OTSU Thresholding to improve accuracy.
* **Smart Logging:** Saves cropped plate images and logs detected text with timestamps.
* **Interactive Controls:** Simple keyboard-based triggers for frame capture.

---

## 📁 Folder Structure
```text
Live-ANPR-System/
├── cropped_plates/        # Processed images of detected plates
├── detected_texts/        # Log files
│   └── plates.txt         # History of detected numbers
├── anpr_model/
│   └── weights/
│       └── best.pt        # Trained YOLOv8 model
├── live_capture.py        # Main execution script
├── .gitignore             # Files to exclude from Git
└── README.md              # Project documentation

```

## 🧠 Technologies Used

| Technology | Purpose |
| :--- | :--- |
| **Python 3.8+** | Core Programming Language |
| **OpenCV** | Image processing & Camera handling |
| **YOLOv8** | Deep Learning object detection |
| **Tesseract OCR** | Optical Character Recognition |
| **NumPy** | Numerical operations |

---

## 🔧 Installation

1️⃣ Clone the Repository
```bash
git clone [https://github.com/KartikChouhan03/Live-ANPR-System.git](https://github.com/KartikChouhan03/Live-ANPR-System.git)
cd Live-ANPR-System
```

2️⃣ Set Up Virtual Environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```
3️⃣ Install Dependencies
```Bash
pip install opencv-python ultralytics pytesseract numpy
```
4️⃣ Install Tesseract OCR Engine
Windows: Download from UB-Mannheim. Default path: C:\Program Files\Tesseract-OCR\tesseract.exe.
Linux: sudo apt install tesseract-ocr

## 🧪 Model Setup

This system requires a **custom-trained YOLOv8 model** for license plate detection.

### Steps:
1. Navigate to the following directory:
anpr_model/weights/

2. Place your trained YOLOv8 model file named:
best.pt


> ⚠️ **IMPORTANT**  
> The `best.pt` file is **not included** in this repository due to file size constraints.

---

## ▶️ Usage

Run the main script to start the live ANPR system:

```bash
python live_capture.py
```

GitHub: @KartikChouhan03
