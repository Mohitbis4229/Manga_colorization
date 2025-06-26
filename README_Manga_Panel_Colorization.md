
# 🖌️ Manga Panel Colorization

This project uses AI to colorize grayscale manga panels (pixel range 0–255), generating realistic colored images with approximately 75% accuracy. It maintains color consistency across panels and supports batch processing using a trained U-Net model.

---

## 🔑 Features

- ✅ **Batch Processing**: Colorizes multiple grayscale manga panels at once.
- 🎨 **Consistent Coloring**: Maintains consistent color schemes across all panels in a chapter.

---

## 🧰 Tech Stack

- **Python** (Google Colab & local scripts)
- **TensorFlow / Keras** – U-Net model
- **OpenCV (cv2)** – image processing
- **Matplotlib** – image visualization
- **colorgram.py** – for color extraction
- **PyMuPDF (fitz)** – for PDF image extraction
- **Pillow (PIL)** – image conversion and PDF generation

---

## ⚙️ Setup & Installation

This project is designed to run in **Google Colab** and locally (Python script).  
Datasets must be uploaded to Google Drive.

### 📁 Required Structure
- `RGB_Images/` — Colored manga panels
- `Grayscale_Images/` — Corresponding grayscale panels
- `Validation/` — Optional validation data
- `colorgram_data.json` — Pre-extracted color reference file

📦 [Download the `.tar` model file](https://drive.google.com/file/d/1tWF2IyMcfzQUnoLiHmUYaSIuqjsEg_IC/view?usp=sharing)

---

## 🧪 Training in Google Colab

1. Open the notebook `COMIC-AI.ipynb` in Colab.
2. Mount your Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Point paths to the dataset folder.
4. Train and export the model as `.keras` file.

---

## 🧑‍💻 Usage

Use the Python script provided to run local inference on test images or PDFs.

### Update the paths:
```python
INPUT_PDF = None  # or path to a manga PDF
OUTPUT_PDF = "path/to/final_output.pdf"
EXTRACTED_IMAGES_DIR = "path/to/grayscale/images"
PROCESSED_IMAGES_DIR = "path/to/save/colored/images"
AI_MODEL_PATH = "path/to/saved/colorization_Model.keras"
```

### How It Works:
- Optionally extracts grayscale images from PDF
- Splits them into 256×256 patches
- Feeds them to the U-Net model for color prediction
- Reconstructs the full image
- Saves results and converts them into a compiled PDF

---

## 🔮 Future Improvements

- 🖥️ GUI interface for user-friendly use
- 🎯 Improve colorization accuracy beyond 75%
- 🧠 Object and character-level extraction before coloring
- 🌍 Input real-world colors or styles for references
- 🖌️ Automatic style transfer from sample colored panels
- 📈 Further model tuning and training loops

---

## 🤝 Contributing

Contributions are welcome!  
Please feel free to open issues or submit pull requests.  
Make sure your code follows PEP8 guidelines and is well-documented.

---

## 📜 License

⚠️ **No license specified.**  
This means all rights are reserved by the author.  
Do not reuse, distribute, or modify the code without explicit permission.
