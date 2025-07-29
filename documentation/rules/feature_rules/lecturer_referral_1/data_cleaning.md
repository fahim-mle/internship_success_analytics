# Lecturer refereal General data cleaning instructions

## The following instruction will be applicable for all 3 lecturer_referal_x {x =1,2,3} variables

## From this point we will use `data/cleaned_data/student_data_v1.csv` as it is the latest version of data cleaning process

1. All the lecturer referral mainly depends on comments identified_issues
   column.
2. Make rules for associating identified_issues with lecturer_referral. From
   common sense what I found is, each identified issues can fall under 1 or more
   lecturer referral category.

   - Mental health: Concern for welfare, Attendance, Non submission
   - Death in family: Concern for welfare, Non submission (highly likely)
   - Late enrolment: Non submission, Attendance(less likely)
   - Poor time management: Non submission, Attendance
   - During mutation, each lecturer_referal will choose from the referral
     category using the relationship with the identified issue, but to keep it
     natural, each feature will choose from the options independantly and
     randomly from the option. As we are trying to mimic real world scenraio, so
     each lecturer must come up with their referral independant of others.

3. Those who doesn't have identified issues, less than 2% of the students (Note:
   initially randomly distritribute the values, later it'll be correlated with
   assessment score. As for now assessment scores are not realistic till now)

The above rules will be implemented for all lecturer*referal_1,2,3 \_AND* 3rd
rule where less than 2% student also get lecturer_referral will be independant
of each other, meaning it may pop up randomly on rows of each column.

## After updating the lecturer_referral variables, we will store the updated version of csv to `data/cleaned_data/student_data_v2.csv`. We will not mutate the original data

## For easy use of data muttion for lecturer referrals you will find the JSON format relation `project_info/lecturer_referral_identified_issues_relation.json`
