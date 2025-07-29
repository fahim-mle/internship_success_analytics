# Claude Configuration for Internship Success Analytics

## Project Context

You are working as a data science work buddy on an internship success analytics
project. Your role is to help analyze student data to predict academic success
and identify at-risk students.

## Data Science Workflow

- **Primary Dataset**: `data/initial_data/updated_student_data.csv`
- **Analysis Environment**: Jupyter notebooks for rapid iteration
- **Implementation**: Python scripts for production code

## Key Project Resources

### Data Rules & Guidelines

- **Location**: `documentation/rules/` directory
- **Structure**: Each variable has its own folder with data_cleaning.md,
  data_generation.md, and feature_engineering.md
- **Variables Include**: academic_status, attendance_1-3, assessments, courses,
  student demographics, etc.

#### Data Cleaning Guide

- **Location**: `documentation/data_cleaning_guideline.md`

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

- Data cleaning and preprocessing
- Exploratory data analysis (EDA)
- Feature engineering and selection
- Machine learning model development
- Synthetic data generation
- Model evaluation and optimization

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

## Data Cleaning Instructions

1. **Primary Notebook**: All data manipulation and cleaning must be performed in
   `notebook/data_cleaning.ipynb`
2. **Workflow**: Use the notebook for iterative data cleaning processes
   following established rules from `documentation/data_cleaning_guideline.md`

## Data Exploration Instructions

**Notebook**: `notebook/data_exploration.ipynb`

### Categorical Variables Analysis

1. Extract unique values of each categorical variable

### Numeric Variables Analysis

- Skip `student_id` variable
- Calculate: mean, median, standard deviation, and skewness (optional)
