# DS-4002-Project3
# ASL Alphabet Interpretation with a Convolutional Neural Network

This repository contains all files and documentation for our **DS 4002 Project 3**, which explores the use of a **Convolutional Neural Network (CNN)** to classify American Sign Language (ASL) hand signs from static images.  
Our goal is to evaluate whether a CNN can accurately identify ASL alphabet letters based on image input.

---

## Section 1: Software and Platform

**Programming Language:** Python (v3.10+)

**Primary Libraries Used:**
- `numpy`, `pandas` – data handling and preprocessing  
- `matplotlib`, `seaborn` – visualization  
- `tensorflow`, `keras` or `torch`, `torchvision` – deep learning  
- `scikit-learn` – model evaluation and metrics  
- `opencv-python` – image preprocessing  
- `Pillow` – image loading/resizing  
- `tqdm` – progress tracking  
- `os`, `pathlib`, `glob` – file management utilities  

**Platform(s) Used:**
- macOS Sonoma (development)
- Windows 11 (testing)
- Linux/Ubuntu (Google Colab & compatibility verification)

To install the required dependencies:
```bash
pip install -r requirements.txt

DS-4002-Project3/
│
├── 📄 README.md                  <- Orientation file (this document)
├── 📄 LICENSE.md                 <- License information
├── 📄 requirements.txt           <- Python dependencies
│
├── 📁 data/                      <- Dataset (not uploaded to GitHub)
│   ├── train/                    <- Training images by class
│   ├── val/                      <- Validation images
│   └── test/                     <- Testing images
│
├── 📁 src/                       <- Source code
│   ├── train_model.py            <- Training script
│   ├── eval_model.py             <- Evaluation script
│   ├── preprocess_data.py        <- Preprocessing and augmentation
│   └── utils.py                  <- Helper functions
│
├── 📁 notebooks/                 <- Jupyter notebooks
│   ├── EDA.ipynb                 <- Exploratory Data Analysis
│   ├── ModelTraining.ipynb       <- CNN development
│   └── ResultsSummary.ipynb      <- Evaluation and visualization
│
├── 📁 output/                    <- Saved outputs
│   ├── model_checkpoints/        <- Saved model weights (.h5 / .pt)
│   ├── plots/                    <- Accuracy/loss plots, confusion matrices
│   └── metrics.json              <- Final metrics summary
│
└── 📁 docs/                      <- Additional writeups (e.g., Analysis Plan)
    ├── AnalysisPlan.md
    └── PresentationSlides.pptx

