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

### 1️⃣ Clone the Repository
```bash
git clone [https://github.com/KartikChouhan03/Live-ANPR-System.git](https://github.com/KartikChouhan03/Live-ANPR-System.git)
cd Live-ANPR-System
```

###2️⃣ Set Up Virtual Environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```
###3️⃣ Install Dependencies
```Bash
pip install opencv-python ultralytics pytesseract numpy
```
###4️⃣ Install Tesseract OCR Engine
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
⌨️ Keyboard Controls
Key	Action
C	Capture current frame, detect license plate, and save results
Q	Quit the application safely
📸 How It Works
Detection
YOLOv8 scans the live camera frame to detect license plate bounding boxes.

Extraction
The detected license plate region is cropped from the original frame.

Preprocessing

Grayscale Conversion – Simplifies image data

Gaussian Blur – Removes high-frequency noise

OTSU Thresholding – Binarizes the image for better OCR accuracy

OCR
Tesseract OCR extracts alphanumeric characters from the processed image.

Storage

Detected plate text is appended to plates.txt

Cropped plate images are saved in cropped_plates/

📄 Output Format
1️⃣ Cropped Images (cropped_plates/)
Images are saved using the format:

YYYYMMDD_HHMMSS.jpg
2️⃣ Text Log (detected_texts/plates.txt)
Plain text format:

20260208_161522 - ABC1234
20260208_161845 - XYZ7890
🚧 Troubleshooting
📷 Camera Not Opening
Try changing the camera index in live_capture.py:

cv2.VideoCapture(0)  →  cv2.VideoCapture(1)
🔠 Low OCR Accuracy
Ensure the license plate is well-lit and facing the camera

Adjust Tesseract PSM (Page Segmentation Mode) settings if needed

🤖 Model Errors
Verify that best.pt exists exactly in:

anpr_model/weights/
🔮 Future Improvements
 Multi-plate support for multi-lane traffic scenes

 Database integration (SQL / Firebase)

 Mobile & IP camera support via RTSP streams

 FPS optimization using CUDA / OpenVINO

👨‍💻 Author
Kartık Chouhan
GitHub: @KartikChouhan03
