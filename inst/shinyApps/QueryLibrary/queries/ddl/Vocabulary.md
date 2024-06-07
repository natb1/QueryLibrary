<!---->

# Vocabulary

## Description
The VOCABULARY table includes a list of the Vocabularies integrated from various sources or created de novo in OMOP CDM. This reference table contains a single record for each Vocabulary and includes a descriptive name and other associated attributes for the Vocabulary.

### User Guidance
The primary purpose of the VOCABULARY table is to provide explicit information about specific vocabulary versions and the references to the sources from which they are asserted. Users can identify the version of a particular vocabulary used in the database, enabling consistency and reproducibility in data analysis. Besides, users can check the vocabulary release version in their CDM which refers to the vocabulary_id = 'None'.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE vocabulary (
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


