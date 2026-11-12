# 🚗 License Plate Scanner

A simple Python program that automatically detects a car's license plate from an image, crops it, and extracts the plate number using OCR (Optical Character Recognition).

---

## 📌 Features

- **Automatic Plate Detection**: Locates the license plate using OpenCV edge and contour detection.
- **Plate Cropping**: Automatically isolates and saves the cropped license plate image (`1.png`).
- **Text Recognition**: Extracts the alphanumeric characters from the plate using Tesseract OCR.

---

## 📦 Installation

Open your terminal in the project folder and install the required dependencies:

```bash
pip install opencv-python imutils pytesseract
```

---

## 🚀 How to Use

1. **Add an image**:
   - Place a car image named `car.jpg` inside this project directory.

2. **Check the Tesseract path** (in `app.py`):
   - Ensure line 5 matches where Tesseract is installed on your machine:
     ```python
     pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
     ```

3. **Run the application**:
   ```bash
   python app.py
   ```

4. **Output**:
   - A window will display the image with the detected plate outlined in green.
   - Press any key to cycle through the preview windows.
   - The extracted plate number will be printed in your terminal:
     ```text
     Number is : [Extracted Text]
     ```

---

## ⚙️ How It Works

1. **Resize & Grayscale**: Normalizes the image size and converts it to grayscale for easier processing.
2. **Noise Reduction**: Uses a bilateral filter to smooth the image while keeping plate edges sharp.
3. **Edge Detection**: Applies Canny edge detection to find borders.
4. **Contour Search**: Identifies rectangular contours (4 corner points) representing the license plate.
5. **Crop & OCR**: Crops the plate region and runs Tesseract OCR to read the text.

---

## 💡 Tips for Best Results

- Use clear, well-lit images where the license plate is readable.
- The plate should ideally be horizontal and unobstructed.
