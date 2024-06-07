<!---->

# Concept Relationship

## Description
The CONCEPT_RELATIONSHIP table contains records that define relationships between any two Concepts and the nature or type of the relationship. This table captures various types of relationships, including hierarchical, associative, and other semantic connections, enabling comprehensive analysis and interpretation of clinical concepts. Every kind of relationship is defined in the RELATIONSHIP table.

### User Guidance
The CONCEPT_RELATIONSHIP table can be used to explore hierarchical or attribute relationships between concepts to understand the hierarchical structure of clinical concepts and uncover implicit connections and associations within healthcare data. For example, users can utilize mapping relationships ('Maps to') to harmonize data from different sources and terminologies, enabling interoperability and data integration across disparate datasets.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE concept_relationship (
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


