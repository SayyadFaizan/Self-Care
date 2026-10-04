# Dermatology Condition Predictor

A Flask-based web application that uses a Machine Learning model (Random Forest Classifier) to predict dermatology conditions based on clinical input features such as erythema, scaling, definite borders, itching, Koebner phenomenon, and family history.

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [How to Run the Application](#how-to-run-the-application)
- [Project Structure](#project-structure)
- [Retraining the Model (Optional)](#retraining-the-model-optional)

---

## Overview
The application takes user inputs regarding skin condition symptoms, feeds them into a trained Random Forest model (`dermatology_model.pkl`), and displays the predicted dermatology condition along with a detailed description.

---

## Prerequisites

To run this application, you need to have the following installed on your system:

1. **Python** (version 3.8 or higher recommended)
   - Check if Python is installed:
     ```bash
     python --version
     # or
     python3 --version
     ```
   - If not installed, download and install Python from [python.org](https://www.python.org/).

2. **pip** (Python package installer)
   - Usually included automatically with Python installations.
   - Verify installation:
     ```bash
     pip --version
     # or
     python -m pip --version
     ```

---

## Installation

1. **Clone or Download the Repository**
   Ensure all files (including `app.py`, `dermatology_model.pkl`, `label_encoder.pkl`, `templates/`, etc.) are in your project directory.

2. **(Optional) Create and Activate a Virtual Environment**
   It is recommended to use a virtual environment to manage dependencies.

   - On Windows:
     ```cmd
     python -m venv venv
     venv\Scripts\activate
     ```
   - On macOS / Linux:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Install Required Packages**

   - **Option A (using pip with requirements.txt):**
     ```bash
     pip install -r requirements.txt
     ```

   - **Option B (Windows batch file):**
     Double-click `Mlsetup.bat` or run it in Command Prompt:
     ```cmd
     Mlsetup.bat
     ```

   - **Option C (Manual installation):**
     ```bash
     pip install Flask pandas joblib scikit-learn
     ```

---

## How to Run the Application

1. Open your terminal / command prompt in the project root directory.

2. Ensure your virtual environment (if used) is activated.

3. Start the Flask application by running:
   ```bash
   python app.py
   ```
   *(On some macOS/Linux systems, use `python3 app.py`)*

4. You will see output indicating that the development server is running, for example:
   ```text
    * Running on http://127.0.0.1:5000
   ```

5. Open your web browser and navigate to `http://127.0.0.1:5000` to interact with the web application.

---

## Project Structure

```text
├── app.py                      # Flask web application entry point
├── dermatologydata.csv         # Raw dataset
├── dermatology_processed.csv   # Preprocessed dataset
├── dermatology_model.pkl       # Trained Random Forest model file
├── label_encoder.pkl           # Trained LabelEncoder file
├── preprocessing.py            # Data preprocessing script
├── training.py                 # Script to train and save the model
├── Mlsetup.bat                 # Windows batch script to install dependencies
├── requirements.txt            # Python dependencies file
├── static/                     # CSS styles and image assets
│   ├── styles.css
│   └── images/
└── templates/                  # HTML templates for Flask
    ├── Analyze.html
    └── result.html
```

---

## Retraining the Model (Optional)

If you modify `dermatologydata.csv` or want to re-train the model:

1. **Run Preprocessing:**
   ```bash
   python preprocessing.py
   ```
   This processes raw data and saves `dermatology_processed.csv`.

2. **Train the Model:**
   ```bash
   python training.py
   ```
   This trains the Random Forest model and updates `dermatology_model.pkl` and `label_encoder.pkl`.
