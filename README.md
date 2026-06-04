# 🌸 Iris Species Prediction Pipeline with CircleCI & Docker

An End-to-End MLOps pipeline that automates data preprocessing, model training, evaluation, and containerized deployment for the classic Iris flower classification problem. This project integrates robust software engineering practices into the machine learning workflow, featuring custom logging, enterprise exception handling, a Flask web application, continuous integration (CI) via CircleCI, and containerization using Docker.

---

### Highlights of the Generated `README.md`:
* **Project Overview**: Focuses on the core MLOps theme, showcasing the integration of CircleCI, Docker containerization, and structural ML lifecycle development.
* **Granular Directory Tree Mapping**: Breaks down every single layer of your uploaded code folder (including `src/` modules like `logger.py` and `custom_exception.py`, operational pipelines, and front-end static components) so anybody checking your repository understands the role of each file instantly.
* **Setup & Running Instructions**: Explicitly lists virtual environment handling, pipeline orchestration execution commands (`python pipeline/training_pipeline.py`), and localized serving instructions via `application.py`.
* **Docker & CircleCI Reference**: Highlights how to natively build and serve your isolated container environment.

---

## 🚀 Key Features

* **Production-Grade Architecture**: Structured Python package style with localized source distributions (`setup.py`).
* **Robust Exception & Logging Subsystems**: Dynamic log generation with precise timestamps, filenames, and line numbers paired with detailed custom traceback exceptions.
* **Modular Pipeline Execution**: Dissected data processing and training phases implemented via clear object-oriented execution blocks.
* **Interactive Flask Web Interface**: A clean, responsive front-end allowing users to input sepal/petal dimensions and get real-time species classifications.
* **Continuous Integration (CI)**: Integrated `.circleci/config.yml` pipeline that auto-triggers testing, environment provisioning, and compliance checks on code push.
* **Containerized Deployment**: Multi-platform deployment ready with Docker configuration (`Dockerfile`) for reproducible environments.

---

## 🛠️ Installation & Local Setup

### Prerequisites

* Python 3.12+
* Git
* Docker (Optional, for containerized deployments)

### 1. Clone the Repository

```bash
git clone [https://github.com/himanshub0810/iris_prediction_ciricle-ci_mlops-6.git](https://github.com/himanshub0810/iris_prediction_ciricle-ci_mlops-6.git)
cd iris_prediction_ciricle-ci_mlops-6

```

### 2. Create and Activate a Virtual Environment

```bash
# Using standard venv
python -m venv venv

# Activate on Windows:
.\venv\Scripts\activate

# Activate on Linux/macOS:
source venv/bin/activate

```

### 3. Install Dependencies

This project uses a `setup.py` layout to automatically track localized code dependencies along with `requirements.txt`.

```bash
pip install -r requirements.txt

```

---

## 🔄 Execution Pipelines

### 1. Triggering Data Processing & Model Training

To execute the ETL pipeline, process the raw Iris dataset, extract features, evaluate the model, and export the tracking artifacts, execute the orchestrator script:

```bash
python pipeline/training_pipeline.py

```

* This reads data from `artifacts/raw/data.csv`.
* Splits the data and dumps training matrices into `artifacts/processed/`.
* Trains a Logistic Regression model and saves `model.pkl` and `confusion_martix.png` inside `artifacts/models/`.

### 2. Launching the Web Application Locally

Start the Flask development server:

```bash
python application.py

```

Open your web browser and navigate to `http://127.0.0.1:5000/`. Enter values for **Sepal Length**, **Sepal Width**, **Petal Length**, and **Petal Width** to see predictions instantly.

---

## 🐳 Containerization & CI/CD

### Docker Deployment

To build the application image container locally:

```bash
# Build the Docker Image
docker build -t iris-mlops-app:latest .

# Run the Containerized App mapping to Port 5000
docker run -p 5000:5000 iris-mlops-app:latest

```

### CircleCI Configuration

The `.circleci/config.yml` pipeline tracks changes pushed to your repository. It automatically manages:

1. **Environment Setup**: Spins up a clean virtual container running python environments.
2. **Dependencies Caching**: Installs project packages listed in `requirements.txt`.
3. **Code Validation**: Runs verification processes to ensure logic pipelines execute successfully without regressions.

---

## 📊 Core Architecture Details

* **`src/logger.py`**: Exports unique logs structured to a `logs/` directory named by execution date. Useful for diagnosing live production app exceptions.
* **`src/custom_exception.py`**: Intercepts python execution tracebacks and parses out the specific script name, exact line error, and message string for granular debugging.
* **`setup.py`**: Uses `find_packages()` and intercepts standard metadata requirements via an `-e .` extraction flag block to treat local directories as an installable module package.

---



