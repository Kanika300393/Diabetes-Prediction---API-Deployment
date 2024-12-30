# Diabetes Prediction Model and API Deployment

## Overview
This project is a machine learning-based solution to predict whether a person is diabetic or not based on certain medical parameters. It includes the following steps:

1. **Model Training**: Training a Support Vector Machine (SVM) classifier on the PIMA Diabetes dataset.
2. **API Development**: Creating a REST API using FastAPI to serve predictions.
3. **API Consumption**: Demonstrating how to interact with the API using a Python script.

This project is ideal for demonstrating an end-to-end machine learning pipeline, including model deployment and API integration.

---

## Features
- **Machine Learning Model**: Predicts diabetes based on medical inputs such as glucose levels, BMI, and age.
- **FastAPI Integration**: Provides a REST API endpoint for real-time predictions.
- **Client-Side Interaction**: Python script to send data to the API and receive predictions.
- **User-Friendly Visualizations**: Includes exploratory data analysis (EDA) for insights into the dataset.

---

## Dataset
- **Source**: PIMA Diabetes Dataset
- **Description**: Contains 768 records with 8 input features:
  - Pregnancies
  - Glucose
  - Blood Pressure
  - Skin Thickness
  - Insulin
  - BMI
  - Diabetes Pedigree Function
  - Age
  
- **Target**: Outcome (0 = Non-Diabetic, 1 = Diabetic)

---

## Project Structure
```
Diabetes-Prediction-Model
├── diabetes_model.py               # Model training and EDA
├── ml_api.py                       # API implementation using FastAPI
├── api_implementation.py           # Client-side script to interact with the API
├── requirements.txt                # Python dependencies
├── README.md                       # Project documentation
├── trained_model.sav               # Serialized machine learning model
└── diabetes.csv                    # Dataset file
```

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Kanika300393/Diabetes-Prediction-Model-Web-Application-Deployment.git
   cd Diabetes-Prediction-Model-Web-Application-Deployment
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## How It Works
### Step 1: Model Training
- **Script**: `diabetes_model.py`
- **Purpose**: Preprocesses the data, trains the model, and saves the trained model as `trained_model.sav`.
- **EDA**: Includes visualizations like pairplots, heatmaps, and histograms to explore relationships and distributions in the dataset.

### Step 2: API Development
- **Script**: `ml_api.py`
- **Framework**: FastAPI
- **Endpoint**: `/diabetes_prediction`
  - Accepts POST requests with medical inputs in JSON format.
  - Uses the trained model to predict diabetes status.

### Step 3: API Consumption
- **Script**: `api_implementation.py`
- **Purpose**: Sends a POST request to the `/diabetes_prediction` endpoint with sample data and prints the result.

---

## Running the Project

### 1. Train the Model
Run the following command to train the model and save it:
```bash
python diabetes_model.py
```

### 2. Start the API Server
Run the API server locally using:
```bash
uvicorn ml_api:app --reload
```
- The API will be accessible at: `http://127.0.0.1:8000`
- Test the API by visiting `http://127.0.0.1:8000/docs` for the interactive Swagger UI.

### 3. Test the API
Run the client script to send a POST request:
```bash
python api_implementation.py
```
- Expected output:
  ```
  "The person is Diabetic" or "The person is not Diabetic"
  ```

---

## Example Input and Output
### Input
Sample JSON data sent to the API:
```json
{
    "Pregnancies": 6,
    "Glucose": 148,
    "BloodPressure": 72,
    "SkinThickness": 35,
    "Insulin": 0,
    "BMI": 33.6,
    "DiabetesPedigreeFunction": 0.627,
    "Age": 50
}
```

### Output
Response from the API:
```
"The person is Diabetic"
```

---

## Visualizations
The project includes exploratory data analysis (EDA):
- **Pairplot**: Displays relationships between features grouped by diabetes outcome.
- 
  ![Pair Plot](https://github.com/user-attachments/assets/ea61b40c-875e-4f4d-9681-cc574f5eeab9)

- **Heatmap**: Visualizes feature correlations.
  ![Heat Map](https://github.com/user-attachments/assets/07805540-9777-4562-8785-b47ee38cbc32)

- **Histograms**: Shows distributions for features like glucose and BMI.

  ![Distribution of BMI](https://github.com/user-attachments/assets/df084e3b-f135-4783-8909-9f2b5f67725c)

![Distribution of Glucose Level](https://github.com/user-attachments/assets/52c8dfb0-0d87-41b7-bdab-0f7ca6974359)


---

## Technologies Used
- **Python**: Core language for scripting and development.
- **Libraries**: pandas, numpy, seaborn, matplotlib, sklearn, pickle.
- **Frameworks**: FastAPI for API development.
- **Tools**: Uvicorn for running the API server.

---

## Future Enhancements
- Deploy the API to a cloud service like AWS or Azure.
- Create a web interface for non-technical users.
- Add more features to the model and API for better insights.

---
