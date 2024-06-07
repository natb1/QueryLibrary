<!---->

# Domain

## Description
The DOMAIN table includes a list of OMOP-defined Domains the Concepts of the Standardized Vocabularies can belong to. A Domain defines the set of allowable Concepts for the standardized fields in the CDM tables. For example, the "Condition" Domain contains Concepts that describe a condition of a patient, and these Concepts can only be stored in the condition_concept_id field of the CONDITION_OCCURRENCE and CONDITION_ERA tables. This reference table is populated with a single record for each Domain and includes a descriptive name for the Domain.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Domain (
	domain_id varchar(20) NOT NULL,
	domain_name varchar(255) NOT NULL,
	domain_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


