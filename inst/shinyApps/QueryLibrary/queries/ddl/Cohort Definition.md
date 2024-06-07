<!---->

# Cohort Definition

## Description
The COHORT_DEFINITION table contains records defining a Cohort derived from the data through the associated description and syntax and upon instantiation (execution of the algorithm) placed into the COHORT table. Cohorts are a set of subjects that satisfy a given combination of inclusion criteria for a duration of time. The COHORT_DEFINITION table provides a standardized structure for maintaining the rules governing the inclusion of a subject into a cohort, and can store operational programming code to instantiate the cohort within the OMOP Common Data Model.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Cohort Definition (
	cohort_definition_id integer NOT NULL,
	cohort_definition_name varchar(255) NOT NULL,
	cohort_definition_description varchar(MAX) NOT NULL,
	definition_type_concept_id integer NOT NULL,
	cohort_definition_syntax varchar(MAX) NOT NULL,
	subject_concept_id integer NOT NULL,
	cohort_initiation_date date NOT NULL
)
```

## Input


## Output


## Example output record


