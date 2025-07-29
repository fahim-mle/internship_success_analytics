# Dataset Feature Clarification Questions

This document lists each feature in the `jcu_student_cleaned.csv` dataset, provides observed unique values for categorical variables (extracted from the dataset), and poses simple yes/no or numerical questions to clarify the meaning and distribution of each feature. The answers will help create rules for data cleaning and synthetic data generation with realistic distributions.

---

## Feature: `student_id`

- **Observed Values**: N/A (numerical identifier, e.g., 2, 11, 14, ..., 693)
- **Questions**:
  1. Is this a unique identifier for each student? (Yes/No)
  2. Are there any duplicate student IDs? (Yes/No)
  3. What is the range of student IDs? (e.g., 1 to 1000)
  4. Are student IDs assigned sequentially? (Yes/No)

---

## Feature: `course`

- **Observed Values**: 'master of business administration', 'master of professional accounting', 'bachelor of business', 'master of information technology', 'master of engineering management', 'master of data science (professional)', 'bachelor of tourism, hospitality and events', 'master of international tourism and hospitality management', 'master of professional accounting - master of business administration', 'master of information technology - master of business administration', 'master of international tourism and hospitality management - master of business administration', 'postgraduate qualifying program - business', 'bachelor of commerce', 'bachelor of information technology', 'master of education - master of business administration'
- **Questions**:
  1. Does this represent the student's enrolled program? (Yes/No)
  2. How many unique courses are there?
  3. What is the approximate percentage of students in each course? (e.g., 30% master of business administration, 20% bachelor of business, etc.)
  4. Are some courses more likely for certain cohorts (e.g., First year, LOA)? (Yes/No)

---

## Feature: `student_cohort`

- **Observed Values**: 'First year', 'Continuing', 'Return to Study', 'LOA', 'SRI to JCUB', 'Transferred', 'New'
- **Questions**:
  1. Does this indicate the student's current enrollment status? (Yes/No)
  2. Does 'LOA' mean leave of absence? (Yes/No)
  3. How many cohort categories are there?
  4. What is the approximate percentage of students in each cohort? (e.g., 40% First year, 30% Continuing, etc.)
  5. Are certain cohorts more likely to have academic issues? (Yes/No)

---

## Feature: `academic_status`

- **Observed Values**: 'Satisfactory', 'Conditional', 'Excluded'
- **Questions**:
  1. Does this show the student's current academic standing? (Yes/No)
  2. Does 'Excluded' mean the student can no longer continue? (Yes/No)
  3. How many status categories exist?
  4. What is the approximate distribution of students across these statuses? (e.g., 70% Satisfactory, 20% Conditional, 10% Excluded)
  5. Is academic status determined by failed subjects or other factors? (Yes/No)

---

## Feature: `failed_subjects`

- **Observed Values**: 0.0, 1.0, 2.0, 5.0, 6.0, 8.0
- **Questions**:
  1. Is this the total number of subjects failed by the student? (Yes/No)
  2. Are these failures from the current trimester only? (Yes/No)
  3. What is the maximum number of failed subjects possible?
  4. What is the approximate percentage of students with each number of failed subjects? (e.g., 80% have 0, 10% have 1, etc.)
  5. Does a higher number of failed subjects lead to 'Conditional' or 'Excluded' status? (Yes/No)

---

## Feature: `study_skills(attended)`

- **Observed Values**: 'Referencing', 'Essential Skills', 'Writing', 'None', 'Studiocity', '4R Essential Skills', 'Essential Skills and Reading'
- **Questions**:
  1. Does this list the type of study skills session attended? (Yes/No)
  2. Does 'None' mean no sessions were attended? (Yes/No)
  3. How many session types are there?
  4. What is the approximate percentage of students attending each session type? (e.g., 50% None, 20% Referencing, etc.)
  5. Are students with academic issues more likely to attend sessions? (Yes/No)

---

## Feature: `referral`

- **Observed Values**: 'Student Advocate', 'Student Counsellor', 'Lecturer', 'Other', 'Enrollment'
- **Questions**:
  1. Does this indicate who referred the student for support? (Yes/No)
  2. Are there more referral types than listed? (Yes/No)
  3. How many referral types exist?
  4. What is the approximate percentage of students for each referral type? (e.g., 30% Student Advocate, 25% Lecturer, etc.)
  5. Does a referral indicate the student is at academic risk? (Yes/No)

---

## Feature: `pp_meeting`

- **Observed Values**: 'Not relevant', 'Booked', 'Attended', 'Rescheduled'
- **Questions**:
  1. Does this show if a progress/performance meeting occurred? (Yes/No)
  2. Does 'Not relevant' mean no meeting was needed? (Yes/No)
  3. Are there other meeting statuses? (Yes/No)
  4. What is the approximate percentage of students in each meeting status? (e.g., 50% Not relevant, 30% Attended, etc.)
  5. Are meetings more common for students with failed subjects? (Yes/No)

---

## Feature: `self_assessment`

- **Observed Values**: 'Yes', 'No'
- **Questions**:
  1. Does this indicate if the student completed a self-assessment? (Yes/No)
  2. Is 'Yes' a positive indicator for academic success? (Yes/No)
  3. What is the approximate percentage of students with 'Yes' vs. 'No'? (e.g., 60% Yes, 40% No)
  4. Are self-assessments mandatory? (Yes/No)

---

## Feature: `readiness_assessment_results`

- **Observed Values**: 'L/G:9/10 N:5/10 R:8/10'
- **Questions**:
  1. Does this measure student readiness for study? (Yes/No)
  2. Are scores always out of 10? (Yes/No)
  3. What do 'L/G', 'N', and 'R' stand for? (e.g., Learning, Numeracy, Reading)
  4. What is the typical range for each score? (e.g., L/G: 7-10, N: 3-7, R: 6-10)
  5. Are higher scores associated with better academic outcomes? (Yes/No)

---

## Feature: `follow_up`

- **Observed Values**: 'Yes', 'No'
- **Questions**:
  1. Does this show if follow-up support was needed? (Yes/No)
  2. Is 'Yes' linked to academic risk? (Yes/No)
  3. What is the approximate percentage of students with 'Yes' vs. 'No'? (e.g., 40% Yes, 60% No)
  4. Are follow-ups triggered by specific events (e.g., low attendance)? (Yes/No)

---

## Feature: `follow_up_type`

- **Observed Values**: 'Phone', 'Email', 'F2F', 'No Reply'
- **Questions**:
  1. Does this specify the method of follow-up? (Yes/No)
  2. Does 'No Reply' mean the student didn’t respond? (Yes/No)
  3. How many follow-up types are there?
  4. What is the approximate percentage of each follow-up type? (e.g., 30% Email, 20% Phone, etc.)
  5. Is 'No Reply' more common for at-risk students? (Yes/No)

---

## Feature: `subject_1`, `subject_2`, `subject_3`

- **Observed Values**: 'ED5097', 'CO5117', 'BU1002', 'CP5046', 'ED5880', 'LB5113', 'CO5103', 'CO5109', 'EG5200', 'EG5220', 'EG5310', 'BU1003', 'BU1007', 'CP5047', 'CP5503', 'TO1008', 'TO2117', 'TO3052', 'TO5101', 'TO5103', 'TO5104', 'MA5831', 'MA5840', 'MA5851', 'BU1112', 'BX2011', 'BX2014', 'LB5202', 'LB5205', 'CP1401', 'CP1402', 'CP1404', 'LB5203', 'LB5212'
- **Questions**:
  1. Are these the codes for enrolled subjects? (Yes/No)
  2. Can a student have more than 3 subjects? (Yes/No)
  3. How many unique subject codes exist?
  4. What is the approximate percentage of students enrolled in each subject? (e.g., 10% BU1002, 5% CP5046, etc.)
  5. Are certain subjects associated with higher failure rates? (Yes/No)

---

## Feature: `subject_1_assess_1`, `subject_1_assess_2`, `subject_1_assess_3`, `subject_1_assess_4`, etc

- **Observed Values**: N/A (numerical scores, e.g., 76.2, 69.23, ranging from 0 to 100)
- **Questions**:
  1. Are these assessment scores for each subject? (Yes/No)
  2. Are scores out of 100? (Yes/No)
  3. Are there always 4 assessments per subject? (Yes/No)
  4. What is the typical range of scores for each assessment? (e.g., 50-90)
  5. What is the average score for each assessment? (e.g., mean of 70)
  6. Are scores lower for students with 'Conditional' or 'Excluded' status? (Yes/No)

---

## Feature: `attendance_1`, `attendance_2`, `attendance_3`

- **Observed Values**: N/A (numerical, e.g., 58.24, 73.24, ranging from 0 to 100)
- **Questions**:
  1. Is this attendance percentage for each subject? (Yes/No)
  2. Is it measured from 0 to 100? (Yes/No)
  3. Is there a minimum attendance requirement? (Yes/No)
  4. What is the typical attendance range for each subject? (e.g., 60-90)
  5. What is the average attendance for each subject? (e.g., mean of 75)
  6. Is low attendance linked to failed subjects? (Yes/No)

---

## Feature: `learn_jcu_issues_1`, `learn_jcu_issues_2`, `learn_jcu_issues_3`

- **Observed Values**: 'Access', 'No Access'
- **Questions**:
  1. Does this show issues with the learning platform? (Yes/No)
  2. Does 'No Access' mean the student didn’t log in? (Yes/No)
  3. Are there other issue types? (Yes/No)
  4. What is the approximate percentage of 'Access' vs. 'No Access' for each subject? (e.g., 60% Access, 40% No Access)
  5. Are 'No Access' issues linked to academic risk? (Yes/No)

---

## Feature: `lecturer_referral_1`, `lecturer_referral_2`, `lecturer_referral_3`

- **Observed Values**: 'Non Submission', 'Attendance', 'Concern for Welfare'
- **Questions**:
  1. Does this indicate why the lecturer referred the student? (Yes/No)
  2. Are there more referral reasons than listed? (Yes/No)
  3. How many referral reasons exist?
  4. What is the approximate percentage of each referral reason? (e.g., 40% Non Submission, 30% Attendance, etc.)
  5. Are referrals more common for students with failed subjects? (Yes/No)

---

## Feature: `comments`

- **Observed Values**: N/A (free-text, e.g., "Week 7. Student disclosed high stress levels and lack of sleep...")
- **Questions**:
  1. Are these notes about student progress or issues? (Yes/No)
  2. Are comments present for all students? (Yes/No)
  3. Can comments be empty? (Yes/No)
  4. What percentage of students have comments? (e.g., 80%)
  5. Can comments be used to extract additional features (e.g., sentiment)? (Yes/No)

---

## Feature: `identified_issues`

- **Observed Values**: 'Sickness', 'Late Enrollment', 'Mental health', 'Death in family', 'Poor time management', 'None'
- **Questions**:
  1. Does this list specific problems affecting the student? (Yes/No)
  2. Can a student have multiple issues? (Yes/No)
  3. How many issue types are there?
  4. What is the approximate percentage of each issue type? (e.g., 50% None, 20% Sickness, etc.)
  5. Are certain issues linked to academic risk? (Yes/No)

---

## Feature: `course_group`

- **Observed Values**: 'IT', 'Non-IT'
- **Questions**:
  1. Does this categorize courses by field? (Yes/No)
  2. Are there only 2 groups? (Yes/No)
  3. What is the approximate percentage of students in IT vs. Non-IT? (e.g., 30% IT, 70% Non-IT)
  4. Does course group affect academic risk? (Yes/No)

---

## Feature: `attendance_adj`

- **Observed Values**: N/A (numerical, e.g., 58.24, 73.24, ranging from 0 to 100)
- **Questions**:
  1. Is this an adjusted attendance percentage? (Yes/No)
  2. Is it an average across all subjects? (Yes/No)
  3. Is it used to determine academic status? (Yes/No)
  4. What is the typical range of adjusted attendance? (e.g., 60-90)
  5. What is the average adjusted attendance? (e.g., mean of 75)
  6. How is it calculated from attendance_1, attendance_2, attendance_3? (e.g., simple average, weighted average)

---
