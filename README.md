# AutoVerify

### OCR-Based Automatic License Plate Recognition and Vehicle Verification System

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green.svg)](https://opencv.org/)
[![Tesseract OCR](https://img.shields.io/badge/Tesseract-OCR-yellow.svg)](https://github.com/tesseract-ocr/tesseract)

---

## Project Overview

**AutoVerify** is an end-to-end Computer Vision project designed to automatically detect vehicle license plates, extract registration numbers using Optical Character Recognition (OCR), and verify vehicle information through a custom vehicle database.

The project combines Image Processing, Computer Vision, OCR, and Database Management techniques to automate vehicle identification and retrieve ownership and penalty information in real time.

The primary objective is to assist traffic management systems, parking facilities, toll collection systems, and law enforcement agencies in identifying vehicles and validating their registration details automatically.

---

## Detection & Verification Showcase

![License Plate Detection](Screenshot%202026-03-22%20232814.png)

![Database Verification Result](Screenshot%202026-03-22%20233444.png)

---

## Dataset & Vehicle Registry

* **Database File:** `database.txt` (included in repository)
* **Records:** 100+ Vehicle Registry Records
* **Data Fields:**
  - Registration Number (License Plate)
  - Owner Name
  - Vehicle Model
  - Registration Status (`Valid`, `Penalty`, etc.)
  - Fine / Penalty Amount

### Sample Record
```
Vehicle Number: DL3CAY9324
Owner Name:     Priya Verma
Vehicle Model:  Maruti Swift
Status:         Penalty
Fine Amount:    Rs. 1200
```

---

## Tools & Technologies

### Programming & Libraries
* **Python 3**
* **OpenCV:** Haar Cascade Object Detection, Image Preprocessing (Grayscale, Resize, Otsu Thresholding)
* **Pytesseract:** Optical Character Recognition (OCR) with PSM 7 optimization and alphanumeric whitelisting
* **Regex:** Text cleaning and sanitization
* **OS Module:** File validation and database ingestion

### Architectural Highlights
* **Haar Cascade Classifier:** `haarcascade_russian_plate_number.xml` for license plate localization
* **$O(1)$ Hash Map Lookup:** Fast in-memory dictionary-based registry matching

---

## System Architecture

```
Input Vehicle Image
        │
        ▼
License Plate Detection (OpenCV Haar Cascade)
        │
        ▼
Region of Interest (ROI) Extraction & Preprocessing
(Cubic Interpolation 2x + Otsu Thresholding)
        │
        ▼
OCR Text Recognition (Pytesseract - PSM 7)
        │
        ▼
Regex Standardization & Sanitization
        │
        ▼
Database Verification (O(1) Registry Lookup)
        │
        ▼
Vehicle & Penalty Status Output
```

---

## How to Run Locally

### 1. Prerequisites
Install Tesseract OCR on your system:
* Windows: [Tesseract at UB-Mannheim](https://github.com/UB-Mannheim/tesseract/wiki)
* Linux: `sudo apt install tesseract-ocr`

### 2. Install Python Dependencies
```bash
pip install opencv-python numpy pytesseract
```

### 3. Run Pipeline
```bash
git clone https://github.com/SuyashMathur-bit/AutoVerify.git
cd AutoVerify
python Plate.py
```

---

## Repository Structure

```
AutoVerify/
├── database.txt                            # Vehicle registry database
├── haarcascade_russian_plate_number.xml   # Pre-trained Haar Cascade detector
├── Plate.py                                # Main detection & OCR verification pipeline
├── Plate_1711623405530_1711623405684.png   # Sample test image
├── README.md                               # Project documentation
├── Screenshot 2026-03-22 232814.png       # Detection demonstration
└── Screenshot 2026-03-22 233444.png       # Verification demonstration
```

---

## Author

* **Suyash Mathur** - [SuyashMathur-bit](https://github.com/SuyashMathur-bit)
