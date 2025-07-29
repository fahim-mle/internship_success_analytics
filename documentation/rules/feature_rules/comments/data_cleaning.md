# Comments Data Cleaning Rules

## Overview
The `comments` column contains detailed intervention notes and observations about student academic progress and support provided.

## UPDATED ANALYSIS RESULTS
- **Total unique comment types**: 13
- **NEW DISTRIBUTION RULES**: Selective commenting based on academic status and identified issues
- **Exclusions**: Excluded students have NO comments; Satisfactory students only get comments if they have identified issues

## Data Cleaning Rules

### 1. UPDATED Comment Distribution by Academic Status
- **Academic Caution students**: ALL must have comments (100% coverage)
- **Conditional students**: ALL must have comments (100% coverage)  
- **Satisfactory students**: ONLY those with identified issues get comments
- **Excluded students**: NO comments (excluded from commenting system)

### 2. UPDATED Comment Assignment Using JSON Mapping

#### Implementation Method:
**Use `project_info/comments_issues_mapping.json` for systematic comment assignment**

#### For Academic Caution Students:
**Required**: ALL must have comments from JSON mapping
- Select comments matching their identified issues
- Focus on moderate intervention intensity
- Preferred issues: Poor time management, Mental health, Late Enrollment
- Timeline: Typically Week 4-7

#### For Conditional Students:
**Required**: ALL must have comments from JSON mapping  
- Select comments matching their identified issues
- Focus on moderate-high intervention intensity
- Preferred issues: Mental health, Poor time management, Sickness, Death in family
- Timeline: Typically Week 5-8

#### For Satisfactory Students:
**Limited**: ONLY if they have identified issues
- Use lower severity comments from JSON mapping
- Focus on resolved or well-managed situations
- Minimal intervention intensity

#### For Excluded Students:
**Prohibited**: NO comments assigned (completely excluded from commenting system)

### 3. Comment Content Guidelines
- **Be specific**: Include week numbers, specific concerns, actions taken
- **Show progression**: Comments should reflect ongoing monitoring
- **Include referrals**: Appropriate support service recommendations
- **Maintain consistency**: Comment tone should match academic status severity

### 4. UPDATED Data Quality Checks
- **Academic Caution & Conditional**: Ensure 100% have comments from JSON mapping
- **Satisfactory**: Ensure ONLY those with identified issues have comments
- **Excluded**: Ensure NO comments (null/missing values required)
- **Content Alignment**: Verify comment content matches identified issue type
- **JSON Compliance**: All comments must come from the mapping file

### 5. UPDATED Realistic Constraints
- **Selective Monitoring**: NOT all students require comments (new approach)
- **Excluded Students**: Completely removed from monitoring system
- **Intervention Escalation**: Comment intensity matches academic risk level
- **JSON-Based Selection**: All content must come from predefined mapping
- **Timeline Realism**: Week references should align with academic calendar

## UPDATED Implementation Notes
- Comments now serve as **targeted intervention evidence** for at-risk students only
- **Excluded students** are completely outside the support system
- **Satisfactory students** receive minimal commenting unless issues are present
- Must use `project_info/comments_issues_mapping.json` for all comment assignments
- Critical for machine learning models to distinguish intervention patterns