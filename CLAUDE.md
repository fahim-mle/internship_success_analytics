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

1. Build models to predict students at high and medium risk
2. Focus on binary classification or multi-class risk categorization
3. Evaluate model performance with appropriate metrics
4. Optimize models for identifying at-risk students
