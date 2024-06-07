<!---->

# Concept Ancestor

## Description
The CONCEPT_ANCESTOR table is designed to simplify observational analysis by providing the complete hierarchical relationships between Concepts. Only direct parent-child relationships between Concepts are stored in the CONCEPT_RELATIONSHIP table. To determine higher level ancestry connections, all individual direct relationships would have to be navigated at analysis time. The CONCEPT_ANCESTOR table includes records for all parent-child relationships, as well as grandparent-grandchild relationships and those of any other level of lineage. Using the CONCEPT_ANCESTOR table allows for querying for all descendants of a hierarchical concept. For example, drug ingredients and drug products are all descendants of a drug class ancestor.

This table is entirely derived from the CONCEPT, CONCEPT_RELATIONSHIP and RELATIONSHIP tables.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Concept Ancestor (
	ancestor_concept_id integer NOT NULL,
	descendant_concept_id integer NOT NULL,
	min_levels_of_separation integer NOT NULL,
	max_levels_of_separation integer NOT NULL
)
```

## Input


## Output


## Example output record


