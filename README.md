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

```

# **3. Instructions for Reproducing Our Results**

The following steps describe exactly how to reproduce all preprocessing, model training, and evaluation results generated in our project. These instructions assume the user is running the code contained in our repository without modification.

---

## **Step 1 — Clone the Repository**

Open a terminal and run:

```bash
git clone https://github.com/arotwell/DS-4002-Project3.git
cd DS-4002-Project3
```

This will download the full project folder, including scripts, data (or data-access instructions), and output files.

---

## **Step 2 — Install Required Packages**

Install the required Python packages (TensorFlow, NumPy, Matplotlib, scikit-learn, etc.) by running:

```bash
pip install -r requirements.txt
```

If running in Google Colab, upload the repository and run the same command.

---

## **Step 3 — Obtain and Prepare the Dataset**

1. Download the ASL image dataset from Mendeley Data:
   [https://data.mendeley.com/datasets/xs6mvhx6rh/1](https://data.mendeley.com/datasets/xs6mvhx6rh/1)
2. Unzip the dataset.
3. Place the extracted image folders into:

```
/DATA/raw/
```

4. Run the preprocessing script:

```bash
python SCRIPTS/1_preprocess_data.py
```

This script:

* Loads all image files
* Resizes them to the required CNN input size
* Normalizes pixel values
* Splits the dataset into training, validation, and test sets
* Saves final preprocessed arrays into:

```
/DATA/processed/
```

---

## **Step 4 — Create the Base ResNet Model**

Run:

```bash
python SCRIPTS/2_build_basemodel.py
```

This script:

* Imports the TensorFlow ResNet50 model pre-trained on ImageNet
* Removes its classification head
* Freezes all base layers
* Exports the base model for stacking custom layers

---

## **Step 5 — Build the Custom Classification Head**

Run:

```bash
python SCRIPTS/3_build_toplayers.py
```

This script attaches your custom top layers on top of ResNet, including:

* GlobalAveragePooling2D
* Dense layer(s)
* Dropout
* Final softmax classification layer

The script saves the combined model with base layers frozen.

---

## **Step 6 — Configure Callbacks**

Run:

```bash
python SCRIPTS/4_setup_callbacks.py
```

This sets up callbacks used during training:

* **EarlyStopping** (to prevent overfitting)
* **ReduceLROnPlateau** (to lower the learning rate when validation accuracy stalls)
* **ModelCheckpoint** (to save the best model)

---

## **Step 7 — Train Only the Top Layers (Base Frozen)**

Run:

```bash
python SCRIPTS/5_train_toplayers.py
```

This phase:

* Trains only the custom classification head
* Keeps all ResNet base layers frozen
* Uses a higher learning rate to stabilize the new layers
* Generates training and validation graphs in `/OUTPUT/`

---

## **Step 8 — Fine-Tune the Full Model**

Run:

```bash
python SCRIPTS/6_finetune_model.py
```

This script:

* Unfreezes the **top portion** of the ResNet base
* **Keeps all Batch Normalization layers frozen** (to avoid destabilizing the pretrained weights)
* Reduces the learning rate
* Continues training for fine-tuning
* Saves the best fine-tuned model (`best_model.h5`)

---

## **Step 9 — Evaluate the Final Model**

Run:

```bash
python SCRIPTS/7_evaluate_model.py
```

This will:

* Load the test set
* Compute accuracy, precision, recall, and confusion matrix
* Save the evaluation figures to:

```
/OUTPUT/
```

---

## **Step 10 — Generate Final Plots and Tables**

Run:

```bash
python SCRIPTS/8_generate_outputs.py
```

This generates:

* Training/validation accuracy curves
* Training/validation loss curves
* Confusion matrix
* Sample predictions
* EDA plots (q1.png, q2.png)

All output files appear in:

```
/OUTPUT/
```

