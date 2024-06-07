<!---->

# Vocabulary

## Description
The VOCABULARY table includes a list of the Vocabularies collected from various sources or created de novo by the OMOP community. This reference table is populated with a single record for each Vocabulary source and includes a descriptive name and other associated attributes for the Vocabulary.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Vocabulary (
	vocabulary_id varchar(20) NOT NULL,
	vocabulary_name varchar(255) NOT NULL,
	vocabulary_reference varchar(255) NOT NULL,
	vocabulary_version varchar(255) NOT NULL,
	vocabulary_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


