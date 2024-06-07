<!---->

# Metadata

## Description
The METADATA table contains metadata information about a dataset that has been transformed to the OMOP Common Data Model.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Metadata (
	metadata_id integer NOT NULL,
	metadata_concept_id integer NOT NULL,
	metadata_type_concept_id integer NOT NULL,
	name varchar(250) NOT NULL,
	value_as_string varchar(250) NOT NULL,
	value_as_concept_id integer NOT NULL,
	value_as_number float NOT NULL,
	metadata_date date NOT NULL,
	metadata_datetime datetime NOT NULL
)
```

## Input


## Output


## Example output record


