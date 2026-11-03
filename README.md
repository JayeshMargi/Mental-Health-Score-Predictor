# 🧠 Mental Health Score Predictor

A Machine Learning-based web application that predicts a student's mental health score based on demographic, academic, social media usage, and lifestyle information.

This project uses a trained Machine Learning model, a FastAPI backend, and a responsive frontend built with HTML, CSS, and JavaScript.

> **Disclaimer:** This project is developed for educational purposes only. Predictions are not medical diagnoses or professional mental-health assessments.

## 🚀 Features

- Predicts mental health scores using Machine Learning.
- Collects demographic information such as age, gender, and country.
- Analyzes social media usage and digital habits.
- Considers academic and lifestyle factors.
- Evaluates study hours, sleep hours, and physical activity.
- Includes stress-level information.
- Provides real-time predictions through a FastAPI API.
- Displays prediction results using an interactive score gauge.
- Responsive and user-friendly interface.
- Input validation and error handling.

## 🛠️ Tech Stack

### Frontend
- HTML5
- CSS3
- JavaScript (Vanilla JavaScript)

### Backend
- Python
- FastAPI
- Pydantic
- Uvicorn

### Machine Learning
- Pandas
- NumPy
- Scikit-learn
- Joblib
- Random Forest Regression
- Linear Regression
- RandomizedSearchCV

### Tools
- VS Code
- Jupyter Notebook
- Git & GitHub

## 📂 Project Structure

```text
Mental-Health-Score-Predictor/
│
├── ML_Project.ipynb
│
├── Mental_Health_Model.pkl
│
├── Student Social Media And Mental Health Impact.csv
│
├── main.py
│
├── requirements.txt
│
├── index.html
│
├── style.css
│
└── script.js
```

### File Description

| File | Description |
|---|---|
| `ML_Project.ipynb` | Jupyter Notebook containing data analysis, preprocessing, model training, and evaluation. |
| `Mental_Health_Model.pkl` | Trained Machine Learning model saved using Joblib. |
| `Student Social Media And Mental Health Impact.csv` | Dataset used for training the model. |
| `main.py` | FastAPI backend responsible for handling prediction requests. |
| `requirements.txt` | Contains all required Python libraries. |
| `index.html` | Frontend structure and prediction form. |
| `style.css` | Styling and responsive design. |
| `script.js` | Handles form validation, API requests, and displaying predictions. |

## ⚙️ How the Project Works

The project follows these steps:

1. **User Input:** The user enters personal, academic, social media, and lifestyle information.
2. **Input Validation:** JavaScript validates the entered information.
3. **API Request:** The frontend sends the input data to the FastAPI backend in JSON format.
4. **Backend Processing:** FastAPI validates the incoming data using Pydantic.
5. **Data Preprocessing:** The backend prepares the input features in the format expected by the trained model.
6. **Machine Learning Prediction:** The trained Random Forest regression pipeline predicts the mental health score.
7. **Result Display:** The predicted score is returned to the frontend and displayed using a visual score gauge.

## 🤖 Machine Learning Workflow

The Machine Learning model is developed using the following workflow:

### 1. Data Collection
The project uses a Student Social Media and Mental Health dataset.

### 2. Exploratory Data Analysis (EDA)
- Understanding the dataset.
- Checking missing values.
- Analyzing numerical and categorical features.
- Understanding relationships between variables.
- Visualizing data distributions.

### 3. Data Preprocessing
- Handling numerical features.
- Encoding categorical features.
- Scaling numerical data.
- Preparing training and testing datasets.

### 4. Model Training

The project explores regression algorithms including:

- Linear Regression
- Random Forest Regression

### 5. Hyperparameter Tuning

RandomizedSearchCV is used to search for suitable Random Forest hyperparameters.

### 6. Model Evaluation

The trained models are evaluated using regression evaluation techniques.

### 7. Model Saving

The selected preprocessing and prediction pipeline is saved as:

`Mental_Health_Model.pkl`

Joblib is used to save and load the trained pipeline.

## 📋 Input Features

The application accepts the following information:

| Feature | Description |
|---|---|
| Age | User's age |
| Gender | Male or Female |
| Country | User's country |
| Academic Level | Undergraduate, Graduate, or High School |
| Most Used Platform | Frequently used social media platform |
| Purpose of Use | Education, Entertainment, Networking, or News |
| Average Daily Usage Hours | Daily social media usage |
| Daily Unlocks | Number of times the phone is unlocked |
| Study Hours | Daily study hours |
| Physical Activity Hours | Daily physical activity |
| Sleep Hours Per Night | Average sleeping hours |
| Stress Level | Low, Medium, High, or Very High |

## 🔧 Installation and Setup

Follow these steps to run the project locally.

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
```

### Step 2: Navigate to Project Directory

```bash
cd Mental-Health-Score-Predictor
```

### Step 3: Create Virtual Environment

```bash
python -m venv venv
```

Activate the virtual environment.

**Windows:**

```bash
venv\Scripts\activate
```

**macOS/Linux:**

```bash
source venv/bin/activate
```

### Step 4: Install Dependencies

```bash
pip install -r requirements.txt
```

Make sure the installed scikit-learn version is compatible with the version used to create the saved model.

### Step 5: Run the Backend

```bash
uvicorn main:app --reload
```

The backend will start at:

```text
http://127.0.0.1:8000
```

### Step 6: Open API Documentation

FastAPI automatically provides interactive API documentation.

```text
http://127.0.0.1:8000/docs
```

### Step 7: Run the Frontend

Open `index.html` in your browser.

For local development, update the API URL inside `script.js`:

```javascript
const API_BASE = "http://127.0.0.1:8000";
```

The frontend can now communicate with the locally running backend.

## 🔗 API Endpoints

The project uses FastAPI to handle prediction requests.

### 1. Home Endpoint

**Method:** GET

```text
/
```

Checks whether the backend API is running.

### 2. Prediction Endpoint

**Method:** POST

```text
/predict
```

Accepts student information and returns the predicted mental health score.

### Example JSON Request

```json
{
  "age": 21,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Entertainment",
  "avg_daily_usage_hours": 4.5,
  "daily_unlocks": 60,
  "study_hours": 5,
  "physical_activity_hours": 1,
  "sleep_hours_per_night": 7,
  "stress_level": "Medium"
}
```

### Example JSON Response

```json
{
  "predicted_mental_health_score": 6.42
}
```

*Note: The response value is illustrative. Actual predictions depend on the trained model and submitted input.*

## 🌐 Deployment

The frontend is configured to communicate with the deployed backend:

```javascript
const API_BASE =
"https://mental-health-score-predictor-krzb.onrender.com";
```

For deployment:

1. Deploy the FastAPI backend.
2. Include the trained model file in the backend environment.
3. Install all required dependencies.
4. Configure the frontend API URL.
5. Configure CORS to allow your frontend domain.
6. Test the prediction API after deployment.

**Security Note:** Configure CORS with trusted frontend origins instead of allowing every origin in a production environment.

## 📈 Future Improvements

- Improve prediction performance through additional model experimentation.
- Add more relevant datasets.
- Improve model evaluation and explainability.
- Add user authentication.
- Create prediction history and dashboard features.
- Improve frontend accessibility.
- Add automated backend testing.
- Implement model monitoring and versioning.

## ⚠️ Limitations and Responsible Use

- Predictions depend on the quality and representativeness of the training dataset.
- User-provided information may be inaccurate or incomplete.
- Machine Learning predictions may contain errors or bias.
- The predicted score is not a clinical diagnosis.
- This application should not be used to make healthcare, educational, or employment decisions.

For mental-health concerns, consult a qualified mental-health professional.

## 👨‍💻 Author

**Jayesh Margi**

GitHub: [JayeshMargi](https://github.com/JayeshMargi)


---

⭐ If you find this project useful, consider giving it a star on GitHub!
