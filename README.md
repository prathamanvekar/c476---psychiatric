# Psychiatric Disorder Prediction from fMRI

A deep learning application for predicting psychiatric disorders using resting-state functional MRI (rfMRI) data. This project uses multiple neural network models (Keras/TensorFlow) and XGBoost for classification.

## Project Overview

This application analyzes functional connectome data from resting-state fMRI scans to predict psychiatric conditions. It includes:

- **Deep Learning Models**: VGG-based and custom Keras models for neuroimaging analysis
- **Gradient Boosting**: XGBoost model for comparison
- **Web Interface**: Flask-based application for predictions
- **Data Pipeline**: Support for both `.npy` and `.mat` file formats

## Setup Instructions

### Prerequisites

- Python 3.8 or higher
- pip package manager

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd psychiatric
```

### 2. Create Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Dataset Setup

Download the rfMRI dataset from Kaggle:

1. Go to [Kaggle Datasets](https://www.kaggle.com/datasets)
2. Search for "rfMRI" or "psychiatric" related datasets
3. Download and extract the dataset
4. Place the data in the `data/` folder:
   ```
   data/
   ├── train/
   │   ├── sub001/
   │   ├── sub002/
   │   └── ...
   └── test/
       ├── sub001/
       ├── sub002/
       └── ...
   ```

### 5. Run the Application

```bash
python app.py
```

The Flask app will start on `http://localhost:5000`

## Model Performance

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 72.5% |
| Precision | 68.2% |
| AUC       | 0.648 |
| F1 Score  | 0.65  |

## Project Structure

```
psychiatric/
├── app.py                    # Flask application
├── best_model.keras          # Primary Keras model
├── best_model_vgg.keras      # VGG-based model
├── best_model_xgboost.json   # XGBoost model
├── requirements.txt          # Python dependencies
├── data/                     # Dataset directory (excluded from git)
│   ├── train/
│   └── test/
├── static/                   # Static files (CSS, images)
├── templates/                # HTML templates
└── README.md                 # This file
```

## Usage

The web interface accepts fMRI data files (`.npy` or `.mat` format) and returns predictions with confidence scores.

## Notes

- The `data/` folder is not included in the repository. Please download the dataset from Kaggle as described above.
- Model predictions are based on functional connectome analysis from resting-state fMRI.
- For questions or issues, please refer to the dataset documentation on Kaggle.
