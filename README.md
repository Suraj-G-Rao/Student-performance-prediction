# 🎓 Student Performance Prediction Project

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange.svg)](https://scikit-learn.org/)
[![Docker](https://img.shields.io/badge/Docker-Supported-blue.svg)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Project Overview

This project aims to predict student performance based on various features such as gender, race/ethnicity, parental level of education, lunch type, test preparation course, and scores in reading and writing. The project involves building a machine learning pipeline to process and analyze the data, and deploying the model using a Flask application.

## ✨ Features

- **Automated Data Pipeline**: End-to-end ML pipeline with data ingestion, transformation, and model training
- **Multiple Model Evaluation**: Trains and compares multiple regression models to select the best performer
- **Docker Support**: Containerized deployment for easy setup and reproducibility
- **Scalable Architecture**: Modular design for easy maintenance and extension
- **Production Ready**: Includes prediction pipeline for real-time inference

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Docker (optional, for containerized deployment)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Student-performance-prediction.git
   cd Student-performance-prediction
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the pipeline**
   ```bash
   python main.py
   ```

## 📁 Project Structure

```
.
├── data/                      # Raw and processed data
├── artifacts/                 # Trained models and preprocessing objects
├── src/
│   ├── components/
│   │   ├── data_ingestion.py      # Data loading and splitting
│   │   ├── data_transformation.py # Data preprocessing
│   │   ├── model_trainer.py       # Model training and evaluation
│   │   └── predict_pipeline.py    # Prediction pipeline
│   └── pipeline/
│       └── predict_pipeline.py    # Main prediction interface
├── app.py                     # Flask application
├── main.py                    # Main entry point
├── requirements.txt           # Python dependencies
├── Dockerfile                # Docker configuration
└── README.md                 # Project documentation
```

## 🔧 Components

### 1. Data Ingestion

The `data_ingestion.py` script reads the dataset, splits it into training and test sets, and saves them to the artifacts directory. It performs the following tasks:

- ✅ Reads the raw dataset
- ✅ Splits the data into training and test sets
- ✅ Saves the datasets for further processing

### 2. Data Transformation

The `data_transformation.py` script preprocesses the data by handling missing values, encoding categorical features, and scaling numerical features. It utilizes:

- `ColumnTransformer` for applying different preprocessing pipelines to numerical and categorical data
- Saves the preprocessing object to be used in the prediction pipeline

### 3. Model Trainer

The `model_trainer.py` script trains multiple regression models and selects the best one based on performance metrics. It includes:

- **Models Trained**: Random Forest, Decision Tree, Gradient Boosting, XGBRegressor, CatBoostRegressor, and AdaBoost Regressor
- **Evaluation Metrics**: R2 score, MSE, MAE
- **Best Model Selection**: Automatically selects and saves the best performing model

### 4. Prediction Pipeline

The `predict_pipeline.py` script handles the prediction process. It includes:

- ✅ Loading the trained model and preprocessing object
- ✅ Making predictions based on new input data
- ✅ Real-time inference capabilities

## 🐳 Docker Deployment

To simplify the deployment and management of the Student Performance Prediction project, a Docker image has been created. You can use this image to quickly run the project in a containerized environment.

### Pull and Run

```bash
# Pull the Docker image
docker pull suraj0203/student_performance_prediction:latest

# Run the container
docker run -p 5000:5000 suraj0203/student_performance_prediction:latest
```

### Docker Image Details

- **Image Name**: `suraj0203/student_performance_prediction:latest`
- **Repository Link**: [Docker Hub Repository](https://hub.docker.com/repository/docker/suraj0203/student_performance_prediction/general)

### Build from Source

```bash
# Build the Docker image
docker build -t student-performance-prediction .

# Run the container
docker run -p 5000:5000 student-performance-prediction
```

## 📊 Model Performance

The project evaluates multiple regression models and selects the best one based on R2 score. The following models are compared:

| Model | Description |
|-------|-------------|
| Random Forest | Ensemble learning method using multiple decision trees |
| Decision Tree | Simple tree-based regression model |
| Gradient Boosting | Boosting algorithm that builds models sequentially |
| XGBRegressor | Extreme Gradient Boosting implementation |
| CatBoostRegressor | Gradient boosting with categorical feature support |
| AdaBoost Regressor | Adaptive boosting algorithm |

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Suraj G Rao**

- GitHub: [@suraj0203](https://github.com/suraj0203)

## 🙏 Acknowledgments

- Scikit-learn for the machine learning framework
- Flask for the web application framework
- Docker for containerization support

