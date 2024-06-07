<!---->

# Relationship

## Description
The RELATIONSHIP table provides a reference list of all types of relationships that can be used to associate any two concepts in the CONCEPT_RELATIONSHP table.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Relationship (
	relationship_id varchar(20) NOT NULL,
	relationship_name varchar(255) NOT NULL,
	is_hierarchical varchar(1) NOT NULL,
	defines_ancestry varchar(1) NOT NULL,
	reverse_relationship_id varchar(20) NOT NULL,
	relationship_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


