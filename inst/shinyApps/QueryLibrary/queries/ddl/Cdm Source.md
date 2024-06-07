<!---->

# Cdm Source

## Description
The CDM_SOURCE table contains detail about the source database and the process used to transform the data into the OMOP Common Data Model.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Cdm Source (
	cdm_source_name varchar(255) NOT NULL,
	cdm_source_abbreviation varchar(25) NOT NULL,
	cdm_holder varchar(255) NOT NULL,
	source_description varchar(MAX) NOT NULL,
	source_documentation_reference varchar(255) NOT NULL,
	cdm_etl_reference varchar(255) NOT NULL,
	source_release_date date NOT NULL,
	cdm_release_date date NOT NULL,
	cdm_version varchar(10) NOT NULL,
	cdm_version_concept_id integer NOT NULL,
	vocabulary_version varchar(20) NOT NULL
)
```

## Input


## Output


## Example output record


