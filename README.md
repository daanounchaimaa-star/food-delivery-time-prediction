# Food Delivery Time Prediction

A Machine Learning regression project that predicts food delivery duration in minutes based on order details, delivery conditions, traffic, weather, location, and other relevant features.

This project covers the complete Machine Learning workflow, from raw data cleaning and exploratory analysis to model comparison, hyperparameter tuning, and model saving for inference.

## Results

Four regression models were trained and evaluated on the test set. **Tuned XGBoost achieved the best overall performance**, with an \(R^2\) score of 0.83 and an RMSE of 3.91 minutes.

| Model | Test R² | Test RMSE (min) | Train R² |
|:--|--:|--:|--:|
| Linear Regression | 0.57 | 6.21 | 0.58 |
| Decision Tree | 0.67 | 5.46 | 1.00 |
| Random Forest | 0.82 | 4.03 | 0.97 |
| **XGBoost (Tuned)** | **0.83** | **3.91** | **0.85** |

### Key Findings

- **Best performance:** Tuned XGBoost achieved the highest test \(R^2\) and lowest RMSE.
- **Prediction accuracy:** An RMSE of 3.91 minutes indicates a typical error scale of around four minutes, although RMSE is not the same as average absolute error.
- **Overfitting:** The Decision Tree achieved a training \(R^2\) of 1.00 but performed less well on unseen data.
- **Generalization:** Tuned XGBoost showed a smaller gap between training and test performance.

## Project Workflow

### 1. Data Loading and Cleaning
- Inspected the raw dataset and its structure.
- Handled missing values and inconsistent text formats.
- Standardized values such as weather descriptions and delivery-time entries.

### 2. Exploratory Data Analysis (EDA)
- Explored feature distributions and relationships.
- Investigated how weather, traffic, and other factors relate to delivery duration.

### 3. Feature Engineering
- **Delivery distance:** Calculated the distance between restaurant and customer coordinates using the Haversine formula.
- **Order hour:** Extracted the hour from the order timestamp to capture time-of-day effects.

### 4. Data Preprocessing
- Applied ordinal encoding to traffic density.
- Used one-hot encoding for other categorical features.
- Scaled numerical features where appropriate.

### 5. Model Training and Comparison
Trained and compared four regression algorithms:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor

### 6. Hyperparameter Tuning
Used `RandomizedSearchCV` to optimize XGBoost hyperparameters and improve predictive performance.

### 7. Model Evaluation and Saving
Evaluated the models using regression metrics, including:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score
- Adjusted R² Score

Saved the selected model for future inference using `joblib`.

The notebook contains the detailed code, analysis, and reasoning behind each step.

## Dataset

The dataset contains historical food delivery records with features such as:

- Delivery person's age and rating
- Restaurant and delivery coordinates
- Weather conditions and road-traffic density
- Vehicle type and order type
- Festival indicator and city type

**Target variable:** `Time_taken(min)`

## Tech Stack

| Category | Technologies |
|:--|:--|
| Language | Python |
| Data manipulation | pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | scikit-learn, XGBoost |
| Model persistence | joblib |
| Development environment | Google Colab, Jupyter Notebook |

## Project Structure

```text
food-delivery-time-prediction/
├── Food_Delivery_Time_Prediction.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── models/
│   └── [saved model file, if included]
└── data/
    └── [dataset, if redistribution is permitted]

## Getting Started

### Prerequisites

- Python 3.10 or a compatible version for the installed dependencies
- pip
- Jupyter Notebook

### 1. Clone the Repository

```bash
git clone https://github.com/daanounchaimaa-star/food-delivery-time-prediction.git
cd food-delivery-time-prediction
```


### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Notebook

```bash
jupyter notebook Food_Delivery_Time_Prediction.ipynb
```

Open the notebook and update the dataset path in the data-loading cell to match your local CSV file.

## Future Improvements

- Build an interactive interface for delivery-time predictions.
- Evaluate the model on additional or more recent delivery data.
- Explore further feature engineering and model optimization.

## Author

**Chaimaa Daanoun**

Engineering Student | Digital & Industrial Transformation

[GitHub](https://github.com/daanounchaimaa-star) 
