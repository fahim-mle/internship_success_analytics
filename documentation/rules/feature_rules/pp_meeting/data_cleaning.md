# PP Meeting Data Cleaning Rules

This document outlines the rules for populating the `PP Meeting` column. This
value depends on the `Identified Issues` and the resulting `Referral`. The logic
is sourced from `project_info/referral_pp_meeting_relationship.json`.

## Implementation Rules

- **No Meeting Required:** If `Identified Issues` is 'Late Enrolment' or
  'Sickness', the `Referral` is not for a formal meeting. In these cases, set
  `PP Meeting` to 'Not Relevant'.
- **Meeting Required:** If `Identified Issues` is 'Mental Health', 'death in
  family', or 'Poor Time Management', a meeting is expected.
- **Set Meeting Status:** For these cases, 50% will randomly assign the
  `PP Meeting` status to one of 'Attended', 'Booked', or 'Rescheduled'. Rest 50%
  will be depend on `Academic Status`, specially who are at `academic caution` +
  `identified issue` as `poor time management` will mostly be `Rescheduled` to
  reflect realistic case.

### Summary Table

| Identified Issues    | Resulting Referral                        | Resulting PP Meeting                  |
| -------------------- | ----------------------------------------- | ------------------------------------- |
| Late Enrolment       | Enrolment                                 | Not Relevant                          |
| Mental Health        | `Student Counsellor` / `Student Advocate` | `Attended` / `Booked` / `Rescheduled` |
| death in family      | `Student Counsellor`                      | `Attended` / `Booked` / `Rescheduled` |
| Poor Time Management | `Student Advocate` / `Student Counsellor` | `Attended` / `Booked` / `Rescheduled` |
| Sickness             | `Other`                                   | Not Relevant                          |
