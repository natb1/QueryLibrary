<!---->

# Person

## Description
This table serves as the central identity management for all Persons in the database. It contains records that uniquely identify each person or patient, and some demographic information.

### User Guidance
All records in this table are independent Persons.

### Etl Conventions
All Persons in a database needs one record in this table, unless they fail data quality requirements specified in the ETL. Persons with no Events should have a record nonetheless. If more than one data source contributes Events to the database, Persons must be reconciled, if possible, across the sources to create one single record per Person. The content of the BIRTH_DATETIME must be equivalent to the content of BIRTH_DAY, BIRTH_MONTH and BIRTH_YEAR.

## Query
```sql
CREATE TABLE Person (
	person_id integer NOT NULL,
	gender_concept_id integer NOT NULL,
	year_of_birth integer NOT NULL,
	month_of_birth integer NOT NULL,
	day_of_birth integer NOT NULL,
	birth_datetime datetime NOT NULL,
	race_concept_id integer NOT NULL,
	ethnicity_concept_id integer NOT NULL,
	location_id integer NOT NULL,
	provider_id integer NOT NULL,
	care_site_id integer NOT NULL,
	person_source_value varchar(50) NOT NULL,
	gender_source_value varchar(50) NOT NULL,
	gender_source_concept_id integer NOT NULL,
	race_source_value varchar(50) NOT NULL,
	race_source_concept_id integer NOT NULL,
	ethnicity_source_value varchar(50) NOT NULL,
	ethnicity_source_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


