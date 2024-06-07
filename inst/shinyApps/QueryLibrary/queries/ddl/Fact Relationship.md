<!---->

# Fact Relationship

## Description
The FACT_RELATIONSHIP table contains records about the relationships between facts stored as records in any table of the CDM. Relationships can be defined between facts from the same domain, or different domains. Examples of Fact Relationships include: [Person relationships](https://athena.ohdsi.org/search-terms/terms?domain=Relationship&standardConcept=Standard&page=2&pageSize=15&query=) (parent-child), care site relationships (hierarchical organizational structure of facilities within a health system), indication relationship (between drug exposures and associated conditions), usage relationships (of devices during the course of an associated procedure), or facts derived from one another (measurements derived from an associated specimen).

### User Guidance
NA

### Etl Conventions
All relationships are directional, and each relationship is represented twice symmetrically within the FACT_RELATIONSHIP table. For example, two persons if person_id = 1 is the mother of person_id = 2 two records are in the FACT_RELATIONSHIP table (all strings in fact concept_id records in the Concept table:
- Person, 1, Person, 2, parent of
- Person, 2, Person, 1, child of

## Query
```sql
CREATE TABLE Fact Relationship (
	domain_concept_id_1 integer NOT NULL,
	fact_id_1 integer NOT NULL,
	domain_concept_id_2 integer NOT NULL,
	fact_id_2 integer NOT NULL,
	relationship_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


