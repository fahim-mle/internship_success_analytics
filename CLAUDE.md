# Claude Configuration for Internship Success Analytics

## Project Context

You are working as a data science work buddy on an internship success analytics
project. Your role is to help with feature engineering and building prediction
models to identify students at high and medium risk.

## Data Science Workflow

- **Primary Dataset**: `data/refined_data_for_model/Student_At_Risk_Student_Data.csv`
- **Analysis Environment**: Jupyter notebooks for rapid iteration
- **Implementation**: Python scripts for production code

## Key Project Resources

### Data Rules & Guidelines

- **Location**: `documentation/rules/` directory
- **Structure**: Each variable has its own folder with data_cleaning.md,
  data_generation.md, and feature_engineering.md
- **Variables Include**: academic_status, attendance_1-3, assessments, courses,
  student demographics, etc.

### Project Information

- **Additional Info**: `project_info/` directory (to be created as needed)
- **Documentation**: `documentation/` directory with rules and task lists

## Working Approach

1. **Fast Prototyping**: Use notebooks for exploratory analysis and quick
   iterations
2. **Rule-Based Development**: Follow established rules from
   documentation/rules/
3. **Creative Problem Solving**: Suggest efficient solutions for data science
   challenges
4. **Collaborative Style**: Act as an experienced data science partner

## Key Capabilities Expected

- Feature engineering and selection
- Machine learning model development for risk prediction
- Model evaluation and optimization
- Risk assessment analysis

## Workflow Preferences

- Start with notebook-based exploration
- Apply rules when making data decisions
- Suggest creative approaches to complex problems
- Focus on efficiency and project completion speed
- Maintain scientific rigor while being pragmatic

## Technical Stack

- **Core**: Python, pandas, numpy, scikit-learn
- **Analysis**: Jupyter notebooks
- **Visualization**: matplotlib, seaborn (as needed)
- **Environment**: Virtual environment with specified dependencies

## Feature Engineering Instructions

**Primary Notebook**: `notebook/feature_engineering.ipynb`

### Phase 1

1. Work with refined dataset from `data/refined_data_for_model/`
2. The outcome variable is `risk` from the `/data/refined_data_for_model/Student_At_Risk_Student_Data.csv`
3. Reorganize the csv, put `risk` column at the very end and put `country` column at 2nd position after `student_id`.
4. Make all the text data from every column small case.
5. We only work on `Medium` and `High` risk students from outcome variable `risk`. So only extract student with `medium` and `high` risk.
6. Store the data as csv to `/data/refined_data_for_model` and name it `engineered_student_data.csv`
7. We will then explore the data, find it's pattern and synthetically generate a sizable number or rows for training a predictive model.

### Phase 2

1. We will start working on `/data/refined_data_for_model/engineered_student_data.csv`
2. First we will find direct correlation with each variable except outcome variable `risk`.
3. Based on the correlation of each variable I will create a json file on how to set numeric value to those categorical or textual data.
4. Just based on the previous study we will directly correlate each variable with the outcome variable and give them numerical weight.
5. Also we will do a quick sentiment analysis and use NLP to categorize the importance of each comments and also based on the outcome variable we will replace comments with sentiment analysis we will also give those comments some numeric weight.

## Prediction Model Instructions

**Primary Notebook**: `notebook/prediction_model.ipynb`
**Key Resources**:

- Input Data: `data/refined_data_for_model/fully_engineered_student_data.csv`
- Feature Mappings: `project_info/info_for_predictive_model/feature_mappings.json`
- Implementation Guide: `project_info/info_for_predictive_model/predictive_model_steps.md`

### Objective

Build a binary classification model to predict student risk level (high vs medium) by Week 5, leveraging structured data with predominantly categorical features and engineered numeric weights.

### 11-Step Implementation Process

**Step 1: Objective Definition**

- Target: Binary classification (high=1, medium=0)
- Timeline: Week 5 prediction capability
- Dataset: 282 students, 41+ features (majority categorical)

**Step 2: Data Overview & Validation**

- Load `data/refined_data_for_model/fully_engineered_student_data.csv`
- Verify dataset shape: 282 rows × 41+ columns
- Confirm risk distribution: 95 high-risk, 187 medium-risk students
- Review feature types: numeric vs categorical vs engineered

**Step 3: Data Preprocessing**

- Convert risk variable to binary encoding (medium=0, high=1)
- Handle missing values using appropriate strategies
- Remove non-predictive columns (student_id, original text fields)
- Validate all features are in expected format

**Step 4: Feature Transformation**

- Apply numeric weight mappings from `project_info/info_for_predictive_model/feature_mappings.json`
- Transform categorical features using pre-calculated risk-based weights:
  - country: 32 unique values → numeric weights 1-32
  - academic_status: 4 categories → weights based on risk correlation
  - course, student_cohort, subjects, etc. → risk-weighted numeric scores
- Use sentiment analysis features for comment fields
- Create feature matrix ready for modeling

**Step 5: Feature Selection (Optional)**

- Leverage top correlating features from feature_mappings.json:
  - Top numeric: failed_subjects (-0.67), subject_1_assess_1 (0.43), attendance_2 (0.43)
  - Top categorical: academic_status (0.81), student_cohort (0.56), comments (0.67)
- Consider dimensionality reduction if overfitting occurs

**Step 6: Dataset Splitting**

- Stratified train-test split: 80% train, 20% test
- Maintain class balance in both sets
- Use random_state for reproducibility

**Step 7: Model Training**

- Train multiple classifiers:
  - Random Forest (handle categorical relationships well)
  - XGBoost (robust performance with mixed data types)
  - Logistic Regression (interpretable baseline)
- Apply class weighting to handle imbalanced data (187 vs 95)
- Use cross-validation for hyperparameter tuning

**Step 8: Model Evaluation**

- Primary metrics:
  - Accuracy, Precision, Recall, F1-Score
  - ROC AUC Score (binary classification performance)
  - Confusion Matrix visualization
- Focus on identifying high-risk students (minimize false negatives)

**Step 9: Feature Importance Analysis**

- Extract feature importance from tree-based models
- Visualize top 15-20 most predictive features
- Cross-reference with correlation analysis from feature engineering
- Optional: SHAP analysis for deeper insights

**Step 10: Model Persistence**

- Save best performing model using joblib/pickle
- Preserve preprocessing pipeline (scalers, encoders)
- Document model performance metrics
- Save to `data/refined_data_for_model/trained_model.pkl`

**Step 11: Deployment Preparation (Optional)**

- Create prediction function for new student records
- Implement input validation
- Document model usage and interpretation guidelines

### Key Implementation Details

**Data Handling:**

- Use correlation strengths from feature_mappings.json for feature selection
- Apply pre-calculated numeric weights to avoid data leakage
- Handle engineered features (sentiment scores, weighted categories)

**Model Selection Criteria:**

- Prioritize interpretability for educational stakeholders
- Balance precision/recall for risk identification
- Consider computational efficiency for deployment

**Success Metrics:**

- Primary: High recall for high-risk students (minimize missed cases)
- Secondary: Overall accuracy and F1-score
- Tertiary: Model interpretability and feature importance alignment
