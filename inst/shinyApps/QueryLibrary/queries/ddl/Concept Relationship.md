<!---->

# Concept Relationship

## Description
The CONCEPT_RELATIONSHIP table contains records that define direct relationships between any two Concepts and the nature or type of the relationship. Each type of a relationship is defined in the RELATIONSHIP table.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Concept Relationship (
	concept_id_1 integer NOT NULL,
	concept_id_2 integer NOT NULL,
	relationship_id varchar(20) NOT NULL,
	valid_start_date date NOT NULL,
	valid_end_date date NOT NULL,
	invalid_reason varchar(1) NOT NULL
)
```

## Input


## Output


## Example output record


