# FakeDetector: A Flask & ML-Powered Fake News Detector 📰

[![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/Flask-2.x-green)](https://flask.palletsprojects.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue?logo=docker)](https://www.docker.com/)

A simple yet powerful Flask web application that classifies news text as **real** or **fake** using a pre-trained machine learning model. The project includes a clean user interface, a REST API for programmatic access, and Docker support for easy deployment.



---

## ✨ Features

* **Interactive Web UI**: A simple and clean web interface built with Flask and HTML/CSS to enter and classify news text.
* **Ready-to-Use Model**: Comes with a pre-trained `model.pkl` and `vectorizer.pkl`, so you can run it immediately.
* **REST API**: Exposes a `/predict` endpoint to get predictions programmatically.
* **Reproducible Training**: Includes the Jupyter Notebook (`model/fake_news_detector_prepare_model.ipynb`) used for data preprocessing, model training, and artifact generation.
* **Containerized Deployment**: A `Dockerfile` is included for easy, dependency-free deployment using Docker.

---

## 🛠️ Tech Stack

* **Backend**: Flask
* **Machine Learning**: Scikit-learn, Pandas, NLTK
* **Deployment**: Docker, Gunicorn (recommended for production)
* **Data**: Kaggle "Fake News" competition dataset

---

## 🚀 Quickstart

You can get the application running in just a few minutes using either Python locally or Docker.

### Option A: Run Locally with Python

**Prerequisites**:
* Python 3.9+
* Git LFS

  
**Steps**:

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd <your-repository-directory>
    ```

2.  **Fetch large data files:**
    *If the `.csv` files in the repository are just small pointers, you need to pull the actual data using Git LFS.*
    ```bash
    git lfs install
    git lfs pull
    ```

3.  **Create a virtual environment and install dependencies:**
    ```bash
    # For Windows
    python -m venv venv
    venv\Scripts\activate

    # For macOS/Linux
    python3 -m venv venv
    source venv/bin/activate

    pip install -r requirements.txt
    ```

4.  **Start the Flask app:**
    ```bash
    python app.py
    ```

5.  **Access the application** by navigating to `http://127.0.0.1:5000` in your web browser.

### Option B: Run with Docker

**Prerequisites**:
* Docker installed and running.

**Steps**:

1.  **Build the Docker image:**
    ```bash
    docker build -t fakedetector-app:v1 .
    ```

2.  **Run the Docker container:**
    ```bash
    docker run -d -p 5000:5000 fakedetector-app:v1
    ```

3.  **Access the application** by navigating to `http://localhost:5000` in your web browser.

4.  **To stop the container:**
    ```bash
    # Find the container ID
    docker ps

    # Stop it
    docker stop <container_id>
    ```

---
## **Folder Structure**
Of course. Here is the folder structure for the FakeDetector project in the format you requested.

```
FakeDetector/
├── .gitattributes                # Defines attributes for Git LFS
├── app.py                        # Main Flask application file
├── Dockerfile                    # Instructions for building the Docker container
├── LICENSE                       # Project license file
├── model.pkl                     # Pre-trained classifier model
├── README.md                     # Project documentation
├── requirements.txt              # Python dependencies
├── train.csv                     # Training data (via Git LFS)
├── vectorizer.pkl                # Pre-trained text vectorizer
├── model/
│   └── fake_news_detector_prepare_model.ipynb # Jupyter notebook for model training
├── static/
│   ├── css/
│   │   └── style.css             # CSS stylesheets for the UI
│   ├── js/
│   │   └── script.js             # JavaScript for frontend interactivity
│   └── images/
│       └── logo.png              # UI images
├── templates/
│   ├── index.html                # Main page template
│   └── result.html               # Page to display the classification result
└── test_data/
    └── sample_texts.txt          # Example news texts for testing
```
## **Future Roadmap**
 
* **Multimodal Feature Integration**: 
 Add image, video, and audio analysis to detect manipulated visuals or deepfake audio alongside text analysis.

* **Entity and Temporal Bias Mitigation**: 
 Reduce over-reliance on specific entities and adapt to changing news trends using debiasing and temporal adaptation techniques.

* **Graph-Based Learning**: 
 Use Graph Neural Networks to model how news spreads across social platforms for improved detection accuracy.

* **Continual Learning**: 
 Enable the model to update with new data over time without retraining from scratch, maintaining performance on older content.

* **Active Learning**: 
 Select high-value, uncertain samples for manual labeling to improve efficiency when training on limited labeled data.

