# Referral Data Cleaning Rules

This document outlines the rules for populating the `Referral` column based on
the `Identified Issues` column. The logic is sourced from
`project_info/referral_pp_meeting_relationship.json`.

## Implementation Rules

- **For 'Late Enrolment':** If `Identified Issues` is 'Late Enrolment', set
  `Referral` to 'Enrolment'.
- **For 'Mental Health':** If `Identified Issues` is 'Mental Health', randomly
  assign `Referral` to either 'Student Counsellor' or 'Student Advocate'.
- **For 'death in family':** If `Identified Issues` is 'death in family', set
  `Referral` to 'Student Counsellor'.
- **For 'Poor Time Management':** If `Identified Issues` is 'Poor Time
  Management', randomly assign `Referral` to either 'Student Advocate' or
  'Student Counsellor'.
- **For 'Sickness':** If `Identified Issues` is 'Sickness', set `Referral` to
  'Other'.

### Summary Table

| Identified Issues    | Resulting Referral                        |
| -------------------- | ----------------------------------------- |
| Late Enrolment       | Enrolment                                 |
| Mental Health        | `Student Counsellor` / `Student Advocate` |
| Difficulty in Family | `Student Counsellor`                      |
| Poor Time Management | `Student Advocate` / `Student Counsellor` |
| Sickness             | `Other`                                   |
