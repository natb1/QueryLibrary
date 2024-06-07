<!---->

# Death

## Description
The death domain contains the clinical event for how and when a Person dies. A person can have up to one record if the source system contains evidence about the Death, such as: Condition in an administrative claim, status of enrollment into a health plan, or explicit record in EHR data.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Death (
	person_id integer NOT NULL,
	death_date date NOT NULL,
	death_datetime datetime NOT NULL,
	death_type_concept_id integer NOT NULL,
	cause_concept_id integer NOT NULL,
	cause_source_value varchar(50) NOT NULL,
	cause_source_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


