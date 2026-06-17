# Image Handling and Processing

A comprehensive repository showcasing various data science and machine learning projects including image processing, email spam detection, stock analysis, and emotion detection.

## 📋 Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Projects](#projects)
- [Installation](#installation)
- [Usage](#usage)
- [Technologies](#technologies)
- [Project Details](#project-details)

## Overview

This repository contains multiple data science and machine learning projects that demonstrate various techniques in:
- Image processing and computer vision (OpenCV)
- Machine learning classification (spam detection)
- Time series analysis (stock market data)
- Text processing and emotion detection

## Repository Structure

```
image-handling-and-processing/
├── README.md                           # This file
├── Spam_Email_Detection_System.ipynb   # Email spam classification project
├── Stock-Analysis.ipynb                # Stock market analysis project
├── open-cv.ipynb                       # Computer vision and image processing
├── main.py                             # Main Python script
├── emotion_details.txt                 # Emotion detection data/notes
├── spam.csv                            # Dataset for spam detection
├── sample.png                          # Sample image for processing
└── .idea/                              # IDE configuration files
```

## Projects

### 1. **Spam Email Detection System** (`Spam_Email_Detection_System.ipynb`)

A machine learning project that classifies emails as spam or ham (legitimate).

**Key Features:**
- Data loading and exploration using Pandas
- Text feature extraction using CountVectorizer
- Handles class imbalance with SMOTE (Synthetic Minority Over-sampling Technique)
- Random Forest Classifier with 500 estimators
- Model training and evaluation
- Accuracy scoring for performance metrics

**Dataset:** `spam.csv` containing labeled email data with:
- **Label**: Binary classification (spam/ham)
- **EmailText**: Email content
- **Class Distribution**: 4,825 ham emails vs 747 spam emails

**Libraries Used:**
- `pandas` - Data manipulation
- `scikit-learn` - Machine learning algorithms
- `imblearn` - Handling imbalanced datasets

---

### 2. **Stock Analysis** (`Stock-Analysis.ipynb`)

Time series analysis and visualization of stock market data.

**Key Features:**
- Historical stock data loading and processing
- Time series visualization
- Technical analysis indicators
- Statistical analysis
- Trend analysis

---

### 3. **OpenCV Computer Vision** (`open-cv.ipynb`)

Comprehensive computer vision project demonstrating image processing techniques.

**Key Features:**
- Image loading and preprocessing
- Edge detection
- Feature extraction
- Image transformations
- Real-time processing capabilities
- Sample image: `sample.png`

**Libraries Used:**
- `opencv-cv2` - Computer vision library
- `numpy` - Numerical computations
- `matplotlib` - Visualization

---

### 4. **Emotion Detection** (`emotion_details.txt`)

Supporting data and details for emotion detection analysis from text or images.

---

### 5. **Main Script** (`main.py`)

Entry point Python script for orchestrating various analyses.

## Installation

### Prerequisites
- Python 3.7 or higher
- pip or conda package manager

### Setup

1. Clone the repository:
```bash
git clone https://github.com/namal1230/image-handling-and-processing.git
cd image-handling-and-processing
```

2. Create a virtual environment (optional but recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install -r requirements.txt
```

Or install packages individually:
```bash
pip install pandas scikit-learn imbalanced-learn opencv-python matplotlib numpy jupyter
```

## Usage

### Running Jupyter Notebooks

```bash
jupyter notebook
```

Then open any of the `.ipynb` files:
- `Spam_Email_Detection_System.ipynb`
- `Stock-Analysis.ipynb`
- `open-cv.ipynb`

### Running Python Scripts

```bash
python main.py
```

### Spam Detection Example

```python
import pandas as pd
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.ensemble import RandomForestClassifier
from imblearn.over_sampling import SMOTE

# Load data
data = pd.read_csv("spam.csv")

# Feature extraction
cvec = CountVectorizer()
cx = cvec.fit_transform(data["EmailText"])

# Handle imbalance
smt = SMOTE()
x_sm, y_sm = smt.fit_resample(cx, data["Label"])

# Train model
model = RandomForestClassifier(n_estimators=500)
model.fit(x_sm, y_sm)

# Make predictions
predictions = model.predict(cx_test)
```

## Technologies

### Core Libraries
| Library | Version | Purpose |
|---------|---------|---------|
| Python | 3.7+ | Programming language |
| Pandas | Latest | Data manipulation & analysis |
| NumPy | Latest | Numerical computing |
| Scikit-learn | Latest | Machine learning |
| Imbalanced-learn | Latest | Handling imbalanced datasets |
| OpenCV | Latest | Computer vision |
| Matplotlib | Latest | Data visualization |
| Jupyter | Latest | Interactive notebooks |

### Machine Learning Models Used
- **Random Forest Classifier** - Spam detection
- **SMOTE** - Class imbalance handling
- **CountVectorizer** - Text feature extraction

## Project Details

### Spam Detection Model Architecture

1. **Data Loading**: Load CSV with email labels and text
2. **Feature Engineering**: Convert text to numerical features using CountVectorizer
3. **Data Split**: Train-test split (80-20)
4. **Imbalance Handling**: SMOTE to balance classes
5. **Model Training**: Random Forest with 500 trees
6. **Evaluation**: Accuracy score and performance metrics

**Performance Metrics:**
- Training set: 5,572 samples (4,825 ham, 747 spam)
- Feature dimensionality: 8,679 features

### Stock Analysis Features
- Historical price tracking
- Technical indicators
- Trend analysis
- Visualization and reporting

### Computer Vision Capabilities
- Image loading and preprocessing
- Edge detection (Canny, Sobel)
- Feature detection
- Image transformations and filtering
- Real-time video processing support

## Dataset Information

### spam.csv
- **Size**: 481,792 bytes
- **Format**: CSV
- **Columns**: Label, EmailText
- **Total Records**: 5,572
- **Classes**: 2 (ham, spam)
- **Class Distribution**: Imbalanced (4,825 vs 747)

### sample.png
- **Size**: 1,986,448 bytes
- **Format**: PNG image
- **Purpose**: Sample image for OpenCV processing demonstrations

## Contributing

Feel free to fork this repository and submit pull requests with improvements, bug fixes, or new features.

## License

This project is open source and available for educational and commercial use.

## Contact

**Author**: namal1230  
**GitHub**: [github.com/namal1230](https://github.com/namal1230)  
**Repository**: [image-handling-and-processing](https://github.com/namal1230/image-handling-and-processing)

## Acknowledgments

- Scikit-learn community for excellent ML libraries
- OpenCV project for computer vision tools
- Pandas developers for data manipulation tools
- Jupyter for interactive computing environment

## Future Improvements

- [ ] Add more advanced NLP techniques for spam detection
- [ ] Implement deep learning models
- [ ] Add real-time email filtering
- [ ] Expand stock analysis with predictive models
- [ ] Enhance emotion detection with neural networks
- [ ] Add API endpoint for real-time predictions
- [ ] Create web interface for model interaction
- [ ] Add comprehensive unit tests

---

**Last Updated**: June 2026  
**Repository Status**: Active Development
