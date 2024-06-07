<!---->

# Concept Class

## Description
The CONCEPT_CLASS table is a reference table, which includes a list of the classifications used to differentiate Concepts within a given Vocabulary. This reference table is populated with a single record for each Concept Class.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Concept Class (
	concept_class_id varchar(20) NOT NULL,
	concept_class_name varchar(255) NOT NULL,
	concept_class_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


