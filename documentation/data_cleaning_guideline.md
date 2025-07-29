# Data Cleaning Guidelines for JCU Student Success Analytics

## Overview

This document outlines the data cleaning approach for the internship success
analytics project. We follow a **realistic data modeling approach** where
certain columns serve as static foundations, and all other columns are adjusted
based on research and common sense to maintain data integrity and realism.

## Static Foundation Columns

These columns have been pre-established and **should NOT be modified** during
data cleaning:

### 1. **Course** (`course`)

- Pre-defined course enrollments
- Determines academic pathway and requirements
- Influences subject assignments and assessment patterns

### 2. **Academic Status** (`academic_status`)

- Categories: Satisfactory, At Risk, Critical, etc.
- Reflects overall student performance level
- Drives intervention strategies and support levels

### 3. **Failed Subjects** (`failed_subjects`)

- Number of previously failed subjects
- Historical academic performance indicator
- Influences current academic support needs

## Data Cleaning Principles

### Realistic Data Modeling

All non-static columns must be adjusted to create **realistic and coherent
student profiles** based on:

1. **Research-based relationships** between variables
2. **Common sense correlations** in academic environments
3. **Logical dependencies** between related fields

### Key Relationships to Maintain

#### Academic Performance Consistency

- Students with "At Risk" status should show lower assessment scores
- Failed subjects count should correlate with current performance struggles
- Attendance patterns should align with academic outcomes

#### Course-Specific Patterns

- Assessment types should match course requirements
- Subject codes should align with course curriculum
- Workload and complexity should reflect course level

#### Intervention Logic

- Support services should align with identified issues
- Referral types should match student needs
- Follow-up intensity should correlate with risk level

## Column Categories for Cleaning

### 1. Assessment-Related Columns

**Adjust based on academic_status and failed_subjects:**

- `subject_X_assess_1-4`: Assessment scores (0-100)
- Ensure consistency with academic status
- Lower scores for at-risk students
- Account for improvement/decline patterns

### 2. Attendance Columns

**Align with academic performance:**

- `attendance_1-3`: Attendance percentages
- `attendance_adj`: Adjusted attendance
- Poor attendance should correlate with lower academic status

### 3. Support Service Columns

**Match intervention needs:**

- `study_skills(attended)`: Type of study skills support
- `referral`: Referral source and type
- `pp_meeting`: Personal planning meeting status
- `follow_up`: Follow-up actions taken

### 4. Assessment Results

**Align with academic status:**

- `readiness_assessment_results`: Literacy/Numeracy scores
- Should reflect preparedness for academic level

### 5. Issues and Comments

**NEW UPDATED RULES - Comments and Issues Distribution:**

#### Comments Distribution Rules

- **Satisfactory students**: ONLY those with identified issues have comments
- **Academic Caution & Conditional students**: ALL have comments based on JSON
  mapping
- **Excluded students**: NO comments (excluded from comment system)

#### Identified Issues Distribution

- **Satisfactory students**: Limited subset (25-35%) have identified issues
- **Academic Caution & Conditional students**: ALL must have identified issues
- **Excluded students**: ALL must have identified issues

#### Implementation

- Use `project_info/comments_issues_mapping.json` for systematic distribution
- Comments content must correspond to identified issues type
- Maintain realistic intervention documentation patterns

## Data Cleaning Workflow

### Phase 1: Validate Static Columns

1. Verify course, academic_status, and failed_subjects integrity
2. Identify any inconsistencies in static data
3. Document any anomalies for review

### Phase 2: Assessment Score Alignment

1. Analyze current assessment patterns by academic_status
2. Adjust assessment scores to create realistic distributions
3. Ensure progression patterns make sense within subjects

### Phase 3: Attendance Correlation

1. Align attendance percentages with academic performance
2. Create realistic attendance patterns (not perfectly linear)
3. Account for subject-specific attendance variations

### Phase 4: Support Service Logic

1. Map support services to student needs
2. Ensure referral sources make sense for identified issues
3. Create realistic intervention timelines

### Phase 5: Documentation Consistency

1. **Comments Assignment**:

   - Apply comments ONLY to Academic Caution & Conditional students
   - Use `project_info/comments_issues_mapping.json` for content selection
   - Exclude Satisfactory students without issues from comments
   - Exclude all Excluded students from comments

2. **Issues Alignment**:

   - Ensure ALL Academic Caution, Conditional, and Excluded students have issues
   - Limit Satisfactory students to 25-35% with issues
   - Match comment content with corresponding identified issue type

3. **Technical Issues Correlation**:
   - Ensure technical issues correlate with platform usage patterns

## Quality Checks

### Correlation Validation

- Academic status vs. average assessment scores
- Failed subjects vs. current performance
- Attendance vs. academic outcomes
- Support intensity vs. risk level

### Logical Consistency

- Assessment progression within subjects
- Referral appropriateness for identified issues
- Follow-up frequency matching risk level

### Realistic Patterns

- Normal distribution variations (not perfect correlations)
- Occasional high performers with poor attendance
- Students showing improvement over time
- Realistic intervention response patterns

## Implementation Notes

### Data Modification Approach

1. **Preserve** all static columns unchanged
2. **Adjust** dependent columns systematically
3. **Validate** relationships after each modification
4. **Document** all changes and rationale

### Tools and Methods

- Use pandas for systematic data manipulation
- Apply statistical distributions for realistic variance
- Implement validation functions for consistency checks
- Create visualization to verify patterns

### Documentation Requirements

- Log all modifications made
- Explain rationale for major adjustments
- Track validation results
- Note any unresolved inconsistencies

---

**Next Steps**: Follow this guideline to update `data_cleaning.ipynb` with
systematic cleaning procedures that maintain realistic student data patterns.
