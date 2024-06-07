<!---->

# Domain

## Description
The DOMAIN table includes a list of OMOP-defined Domains to which the Concepts of the Standardized Vocabularies can belong. A Domain represents a clinical definition whereby we assign matching Concepts for the standardized fields in the CDM tables. For example, the Condition Domain contains Concepts that describe a patient condition, and these Concepts can only be used in the condition_concept_id field of the CONDITION_OCCURRENCE and CONDITION_ERA tables. This reference table is populated with a single record for each Domain, including a Domain ID and a descriptive name for every Domain.

### User Guidance
Users can leverage the DOMAIN table to explore the full spectrum of health-related data Domains available in the Standardized Vocabularies. Also, the information in the DOMAIN table may be used as a reference for mapping source data to OMOP domains, facilitating data harmonization and interoperability.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE domain (
	domain_id varchar(20) NOT NULL,
	domain_name varchar(255) NOT NULL,
	domain_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


