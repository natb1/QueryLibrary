<!---->

# Concept Synonym

## Description
The CONCEPT_SYNONYM table is used to store alternate names and descriptions for Concepts.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Concept Synonym (
	concept_id integer NOT NULL,
	concept_synonym_name varchar(1000) NOT NULL,
	language_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


