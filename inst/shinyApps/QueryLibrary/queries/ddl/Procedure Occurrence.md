<!---->

# Procedure Occurrence

## Description
This table contains records of activities or processes ordered by, or carried out by, a healthcare provider on the patient with a diagnostic or therapeutic purpose.

### User Guidance
Lab tests are not a procedure, if something is observed with an expected resulting amount and unit then it should be a measurement. Phlebotomy is a procedure but so trivial that it tends to be rarely captured. It can be assumed that there is a phlebotomy procedure associated with many lab tests, therefore it is unnecessary to add them as separate procedures. If the user finds the same procedure over concurrent days, it is assumed those records are part of a procedure lasting more than a day. This logic is in lieu of the procedure_end_date, which will be added in a future version of the CDM.

### Etl Conventions
When dealing with duplicate records, the ETL must determine whether to sum them up into one record or keep them separate. Things to consider are: - Same Procedure - Same PROCEDURE_DATETIME - Same Visit Occurrence or Visit Detail - Same Provider - Same Modifier for Procedures. Source codes and source text fields mapped to Standard Concepts of the Procedure Domain have to be recorded here.

## Query
```sql
CREATE TABLE Procedure Occurrence (
	procedure_occurrence_id integer NOT NULL,
	person_id integer NOT NULL,
	procedure_concept_id integer NOT NULL,
	procedure_date date NOT NULL,
	procedure_datetime datetime NOT NULL,
	procedure_end_date date NOT NULL,
	procedure_end_datetime datetime NOT NULL,
	procedure_type_concept_id integer NOT NULL,
	modifier_concept_id integer NOT NULL,
	quantity integer NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	procedure_source_value varchar(50) NOT NULL,
	procedure_source_concept_id integer NOT NULL,
	modifier_source_value varchar(50) NOT NULL
)
```

## Input


## Output


## Example output record


