<!---->

# Specimen

## Description
The specimen domain contains the records identifying biological samples from a person.

### User Guidance
NA

### Etl Conventions
Anatomic site is coded at the most specific level of granularity possible, such that higher level classifications can be derived using the Standardized Vocabularies.

## Query
```sql
CREATE TABLE Specimen (
	specimen_id integer NOT NULL,
	person_id integer NOT NULL,
	specimen_concept_id integer NOT NULL,
	specimen_type_concept_id integer NOT NULL,
	specimen_date date NOT NULL,
	specimen_datetime datetime NOT NULL,
	quantity float NOT NULL,
	unit_concept_id integer NOT NULL,
	anatomic_site_concept_id integer NOT NULL,
	disease_status_concept_id integer NOT NULL,
	specimen_source_id varchar(50) NOT NULL,
	specimen_source_value varchar(50) NOT NULL,
	unit_source_value varchar(50) NOT NULL,
	anatomic_site_source_value varchar(50) NOT NULL,
	disease_status_source_value varchar(50) NOT NULL
)
```

## Input


## Output


## Example output record


