<!---->

# Concept Class

## Description
The CONCEPT_CLASS table includes semantic categories that reference the source structure of each Vocabulary. Concept Classes represent so-called horizontal (e.g. MedDRA, RxNorm) or vertical levels (e.g. SNOMED) of the vocabulary structure. Vocabularies without any Concept Classes, such as HCPCS, use the vocabulary_id as the Concept Class. This reference table is populated with a single record for each Concept Class, which includes a Concept Class ID and a fully specified Concept Class name.


### User Guidance
Users can utilize the CONCEPT_CLASS table to explore the different classes or categories of concepts within the OHDSI vocabularies.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE concept_class (
	concept_class_id varchar(20) NOT NULL,
	concept_class_name varchar(255) NOT NULL,
	concept_class_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


