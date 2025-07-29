# Identified Issues Data Cleaning Rules

## Overview
The `identified_issues` column captures specific problems or challenges that affect student academic performance and require intervention.

## Analysis Results
- **Total unique issue types**: 5 distinct categories
- **Coverage**: 261/698 students (37.4%) have identified issues
- **Key Pattern**: ALL students with negative academic status have identified issues, while only 29.6% of Satisfactory students have issues

## Issue Categories
1. **Sickness** - Health-related academic impact
2. **Death in family** - Bereavement affecting studies  
3. **Poor time management** - Organizational/planning difficulties
4. **Late Enrollment** - Administrative/timing challenges
5. **Mental health** - Psychological wellbeing concerns

## UPDATED Data Cleaning Rules

### 1. CRITICAL DISTRIBUTION RULE (UPDATED)
**All students with negative academic status MUST have identified issues**
- Academic Caution: 100% must have issues
- Conditional: 100% must have issues  
- Excluded: 100% must have issues

**Satisfactory students should have limited issues**
- Maximum 30-35% of Satisfactory students should have identified issues
- Issues should be minor or resolved (not severely impacting performance)
- **NEW**: Only Satisfactory students WITH issues will receive comments

### 2. Issue Assignment Guidelines

#### For Students with Academic Caution:
**Appropriate issues**:
- Poor time management
- Mental health (mild to moderate)
- Sickness (ongoing but manageable)
- Late Enrollment (adaptation challenges)

#### For Students with Conditional Status:
**Appropriate issues**:
- Mental health (moderate impact)
- Death in family (recent bereavement)
- Sickness (significant health issues)
- Poor time management (severe organizational problems)

#### For Excluded Students:
**Appropriate issues**:
- Mental health (severe impact)
- Death in family (major bereavement impact)
- Sickness (serious health conditions)
- Multiple concurrent issues possible

#### For Satisfactory Students (Limited Assignment):
**Only assign issues when**:
- Issues are resolved or well-managed
- Minimal academic impact demonstrated
- Strong support systems in place
- Issue occurred early in semester but was addressed

### 3. Data Quality Constraints

#### Mandatory Requirements:
- **Zero tolerance**: No student with negative academic status can have null/missing identified issues
- **Correlation check**: Issues must align with comment content and referral data
- **Severity matching**: Issue severity should match academic status severity

#### Distribution Validation:
- Academic Caution/Conditional/Excluded: 100% issue coverage
- Satisfactory students: 25-35% maximum issue coverage
- Total dataset: 35-40% overall issue coverage

### 4. Realistic Issue Patterns
- **Mental health** issues most common for severe academic problems
- **Poor time management** often appears with Conditional status
- **Death in family** typically temporary but significant impact
- **Sickness** varies in severity and duration
- **Late Enrollment** primarily affects early academic performance

### 5. UPDATED Implementation Guidelines

#### When Cleaning Data:
1. **First priority**: Ensure ALL negative academic status students have appropriate issues
2. **Second priority**: Strategically assign issues to 25-35% of Satisfactory students
3. **Third priority**: Use `project_info/comments_issues_mapping.json` for consistency
4. **Fourth priority**: Ensure comment-issue alignment (comments only for those with issues)
5. **Final check**: Validate overall distribution matches realistic patterns

#### Quality Assurance:
- **JSON Compliance**: All issue-comment pairs must match the mapping file
- **Comment Alignment**: Only students with issues should have comments (except Excluded)
- **Excluded Students**: Must have issues but NO comments
- Verify referral patterns align with identified issues
- Ensure temporal consistency in intervention timeline

## UPDATED Implementation Notes
- **Critical Change**: Issues now directly control comment assignment
- **Satisfactory Students**: Issues determine who gets comments
- **Excluded Students**: Have issues but are excluded from comment system
- Issues are primary predictors of academic risk AND comment eligibility
- Essential for machine learning models to understand intervention trigger patterns
- Must use JSON mapping file for systematic and consistent assignment