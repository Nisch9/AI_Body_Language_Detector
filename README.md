# 🧠 AI Body Language Detector

An end-to-end computer vision and machine learning system that detects human body language in real time using webcam input. The model classifies body language into four categories:

* 😊 Happy
* 😢 Sad
* 🏆 Victorious
* 🥊 Fight

The project demonstrates the full pipeline from data collection with MediaPipe to model deployment via a Streamlit web application.

---

## 📌 Project Overview

This project builds a real-time body language recognition system by extracting pose, face, and hand landmarks using MediaPipe and training machine learning classifiers on the generated landmark dataset. The goal is to interpret non-verbal cues and classify emotional/behavioral states. 

---

## 🚀 Key Features

* Real-time webcam-based detection
* MediaPipe holistic landmark extraction
* Custom dataset generation
* Multi-model training pipeline
* Best-model selection
* Live prediction with confidence score
* Streamlit web interface

---

## 🧠 Models Implemented

The training pipeline evaluates multiple classifiers:

* Logistic Regression
* Ridge Classifier
* Random Forest Classifier
* Gradient Boosting Classifier

The best-performing model is saved as a `.pkl` file for deployment.

---

## 📂 Project Structure

```
AI_Body_Language_Detector/
│
├── Dataset/
│   └── coords.csv
│
├── Training/
│   └── training.ipynb
│
├── Model/
│   └── body_language.pkl
│
├── web.py
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone <your-repo-url>
cd AI_Body_Language_Detector
```

---

### 2️⃣ Create virtual environment (recommended)

**macOS / Linux**

```bash
python -m venv venv
source venv/bin/activate
```

**Windows**

```bash
python -m venv venv
venv\Scripts\activate
```

---

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

If needed:

```bash
pip install streamlit mediapipe opencv-python
```

---

## 📊 Data Collection Workflow

The dataset is created using MediaPipe Holistic:

1. Activate webcam
2. Detect face, hands, and pose landmarks
3. Record landmark coordinates
4. Save to CSV with class label

Data is collected separately for each class (Happy, Sad, Victorious, Fight). The webcam captures 10–15 seconds per class to build the dataset. 

---

## 🧪 Model Training

Open the notebook:

```bash
jupyter notebook Training/training.ipynb
```

Training steps include:

* Data preprocessing
* Train/test split (80:20)
* Pipeline creation
* Multi-model training
* Accuracy comparison
* Best model export

---

## 🌐 Run the Streamlit App

From project root:

```bash
streamlit run web.py
```

Then open:

```
http://localhost:8501
```

---

## 🖥️ Application Workflow

1. User clicks **Run** in the Streamlit UI
2. Webcam feed starts
3. MediaPipe extracts body landmarks
4. Model predicts body language
5. Prediction + confidence displayed live

This follows the architecture: **User → Landmark Extraction → ML Model → UI Output**. 

---

## 📈 Evaluation

Models are evaluated using classification accuracy, and the best-performing algorithm is persisted for inference.

---

## 💡 Use Cases

* Emotion-aware interfaces
* Customer interaction analytics
* Public speaking feedback
* Behavioral research
* Human-computer interaction systems
* Smart surveillance (research context)

---

## 🛠️ Tech Stack

* Python
* OpenCV
* MediaPipe Holistic
* Scikit-learn
* Pandas & NumPy
* Streamlit
* Pickle

