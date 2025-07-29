# Internship Success Analytics

## Project Description

This project aims to analyze student data to predict academic success and identify students who may be at risk. The project involves data cleaning, feature engineering, synthetic data generation, and building a classification model to predict a student's academic status.

## Data

The project utilizes two main data sources:

- `student_data.xlsx`: Raw student data.
- `jcu_student_cleaned.csv`: A partially cleaned version of the student data.

The final cleaned and processed datasets generated during the project are:

- `cleaned_data.csv`
- `realistic_data.csv`
- `synthetic_data.csv`

## Project Plan

The project is structured into a 7-day plan:

### Day 1: Data Inspection and Cleaning

- **Goal:** Load and clean the data to ensure consistency and usability.

- **Tasks:**
  - Load `student_data.xlsx` and `jcu_student_cleaned.csv`.
  - Handle missing values in numerical and categorical columns.
  - Correct inconsistencies and standardize data.
  - Save the cleaned data as `cleaned_data.csv`.

### Day 2: Make Data Realistic

- **Goal:** Adjust the data to reflect realistic patterns.

- **Tasks:**
  - Adjust numerical values (assessment scores, attendance) based on academic status.
  - Align categorical features with performance trends.
  - Save the realistic data as `realistic_data.csv`.

### Day 3: Synthetic Data Generation

- **Goal:** Expand the dataset for modeling.

- **Tasks:**
  - Duplicate rows and add random noise to numerical columns.
  - Balance the dataset for minority classes.
  - Save the synthetic dataset as `synthetic_data.csv`.

### Day 4: Feature Selection and Engineering

- **Goal:** Prepare features and target for modeling.

- **Tasks:**
  - Select key features for modeling.
  - Engineer new features (e.g., averages, totals).
  - Encode categorical variables and map the target variable to numerical labels.
  - Split the data into training and testing sets (80/20 split).

### Day 5: Model Building

- **Goal:** Train and test a classification model.

- **Tasks:**
  - Train a Random Forest classification model.
  - Evaluate the model using accuracy, precision, and recall.
  - Save the trained model.

### Day 6: Model Refinement and Documentation

- **Goal:** Optimize the model and document the process.

- **Tasks:**
  - Tune model hyperparameters.
  - Use cross-validation for robustness.
  - Document the entire workflow in this README.

### Day 7: Final Checks and Wrap-Up

- **Goal:** Validate and finalize the project.

- **Tasks:**
  - Run the full pipeline end-to-end.
  - Verify model performance.
  - Organize project files.

## File Structure

```text
.
├── readme.md
├── data/
│   ├── initial_data/
│   ├── cleaned_data/
│   ├── synthetic_realistic_data/
│   └── refined_data_for_model/
├── src/
│   ├── 1_data_cleaning/
│   ├── 2_data_generation/
│   ├── 3_feature_engineering/
│   └── 4_model_training/
└── venv/
```

## Usage

1. Clone the repository.
2. Create and activate the virtual environment:

    ```bash
    # Create the virtual environment
    python3 -m venv venv

    # Activate the virtual environment
    source venv/bin/activate
    ```

3. Install the required dependencies:

    ```bash
    pip install pandas numpy scikit-learn
    ```

4. Run the scripts within the `src` subdirectories in sequential order.

## Results

The final model performance and key findings will be documented here upon completion of the project.
