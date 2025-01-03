# ML_Project_Group52

## Project Title
To grant or not to grant: deciding on compensation benefits

## Project Overview
This project explores machine learning techniques to predict compensation benefit decisions based on historical data. It evaluates multiple models, including Logistic Regression, Naive Bayes, K-Nearest Neighbors, Neural Networks, Decision Trees, Random Forest, Bagging, XGBoost, and Support Vector Machines. The analysis culminates in comparing XGBoost (the best-performing model) with a stacking ensemble approach.

## Repository Structure
```
ML_Project_Group52/
|
|-- model_input_files/                               # Selected feature datasets for modeling
|-- preprocessed_files/                              # Preprocessed datasets saved from Notebook 02
|-- 01_EDA_g52.ipynb                                 # Exploratory Data Analysis (EDA)
|-- 02_Data_Preprocessing_g52.ipynb                  # Data preprocessing and saving processed files
|-- 03_Encoding_Scaling_Feature_Selection_g52.ipynb  # Encoding, scaling, and feature selection
|-- 04_Model_and_Assessment_g52.ipynb                # Model training, evaluation, and assessment
|-- 05_Model_Deployment                              # Model deployment using streamlit app
   |-- app.py
   |-- trained_pipeline.pkl
|-- README.md                                        # Project overview and instructions
|-- test_data.csv.zip                                # Compressed test dataset
|-- train_data.csv.zip                               # Compressed train dataset
```

## Workflow

### 1. Exploratory Data Analysis (Notebook 01)
- Conducts initial analysis of the dataset.
- Visualizes distributions, correlations, and outliers.

### 2. Data Preprocessing (Notebook 02)
- Handles missing values, outliers, and feature engineering.
- Saves processed files into the `preprocessed_files` folder.

### 3. Feature Engineering & Selection (Notebook 03)
- Applies feature encoding and scaling.
- Selects the most relevant features for modeling.
- Saves selected features into the `model_input_files` folder.

### 4. Model Training & Evaluation (Notebook 04)
- Trains and evaluates multiple models.
- Compares XGBoost against a stacking ensemble.
- Generates performance metrics and visualizations, including confusion matrices and feature importance.

### 5 - Model Deployment: Streamlit App

### Files
- **`app.py`**: 
  - The main Python script that serves as the Streamlit application.
  - Provides an interactive UI to users for inputting data and visualizing model predictions.
  - Loads the trained machine learning pipeline and uses it to generate predictions.
  - Includes functionality for displaying results or visualizations derived from the model.

- **`trained_pipeline.pkl`**: 
  - A serialized file containing the trained machine learning pipeline (preprocessing steps + model).
  - Created during the model training phase using our original pipeline, but with a subset of data and a random forest model, to simulate putting the model into production.

### Workflow
1. **Model Training and Serialization**:
   - A machine learning pipeline was trained and saved as `trained_pipeline.pkl` using `pickle`.
   - The pipeline includes all necessary preprocessing steps and a sample trained model, that later can be updated to a production model.

2. **Streamlit App (`app.py`)**:
   - Loads the `trained_pipeline.pkl` file at runtime.
   - Accepts user inputs (via text boxes).
   - Processes the inputs using the loaded pipeline.
   - Displays predictions and any additional analysis in an easy-to-use web interface.

3. **Running the App**:
   - Start the Streamlit app by running the following command in the terminal:
     ```bash
     streamlit run app.py
     ```
   - The app will open in the browser, where users can interact with it by providing inputs and viewing predictions.

## Key Findings
- **Best Model**: XGBoost outperformed all other models with the highest F1 scores.
- **Stacking Performance**: A stacking ensemble provided comparable performance but required higher computational resources.
- **Challenges**: Class imbalance and poor minority class predictions were consistent across all models.
- **Feature Importance**: Weekly wage and occupation-related features had the highest impact.

## Reproducing the Results
1. Clone the repository:
   ```bash
   git clone https://github.com/LenaHermann/ML_Project_Group52.git
   ```
2. Navigate to the directory:
   ```bash
   cd ML_Project_Group52
   ```
3. Run the notebooks in sequence (01 to 04).
4. Analyze outputs and visualizations in the results folders.
5. See what putting the model into production is by running app.py in the bash or going to this link: https://ml-project-deployment-g52.streamlit.app/

## Dependencies
- Python 3.8+
- Libraries: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, XGBoost, TensorFlow

## Contact
For any queries, feel free to reach out via GitHub issues.


