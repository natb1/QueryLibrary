<!---->

# Cohort

## Description
The COHORT table contains records of subjects that satisfy a given set of criteria for a duration of time. The definition of the cohort is contained within the COHORT_DEFINITION table. It is listed as part of the RESULTS schema because it is a table that users of the database as well as tools such as ATLAS need to be able to write to. The CDM and Vocabulary tables are all read-only so it is suggested that the COHORT and COHORT_DEFINTION tables are kept in a separate schema to alleviate confusion.

### User Guidance
NA

### Etl Conventions
Cohorts typically include patients diagnosed with a specific condition, patients exposed to a particular drug, but can also be Providers who have performed a specific Procedure. Cohort records must have a Start Date and an End Date, but the End Date may be set to Start Date or could have an applied censor date using the Observation Period Start Date. Cohort records must contain a Subject Id, which can refer to the Person, Provider, Visit record or Care Site though they are most often Person Ids. The Cohort Definition will define the type of subject through the subject concept id. A subject can belong (or not belong) to a cohort at any moment in time. A subject can only have one record in the cohort table for any moment of time, i.e. it is not possible for a person to contain multiple records indicating cohort membership that are overlapping in time

## Query
```sql
CREATE TABLE Cohort (
	cohort_definition_id integer NOT NULL,
	subject_id integer NOT NULL,
	cohort_start_date date NOT NULL,
	cohort_end_date date NOT NULL
)
```

## Input


## Output


## Example output record


