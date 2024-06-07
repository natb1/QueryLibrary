<!---->

# Source To Concept Map

## Description
The source to concept map table is a legacy data structure within the OMOP Common Data Model, recommended for use in ETL processes to maintain local source codes which are not available as Concepts in the Standardized Vocabularies, and to establish mappings for each source code into a Standard Concept as target_concept_ids that can be used to populate the Common Data Model tables. The SOURCE_TO_CONCEPT_MAP table is no longer populated with content within the Standardized Vocabularies published to the OMOP community.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Source To Concept Map (
	source_code varchar(50) NOT NULL,
	source_concept_id integer NOT NULL,
	source_vocabulary_id varchar(20) NOT NULL,
	source_code_description varchar(255) NOT NULL,
	target_concept_id integer NOT NULL,
	target_vocabulary_id varchar(20) NOT NULL,
	valid_start_date date NOT NULL,
	valid_end_date date NOT NULL,
	invalid_reason varchar(1) NOT NULL
)
```

## Input


## Output


## Example output record


