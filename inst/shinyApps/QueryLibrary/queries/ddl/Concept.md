<!---->

# Concept

## Description
The Standardized Vocabularies contains records, or Concepts, that uniquely identify each fundamental unit of meaning used to express clinical information in all domain tables of the CDM. Concepts are derived from vocabularies, which represent clinical information across a domain (e.g. conditions, drugs, procedures) through the use of codes and associated descriptions. Some Concepts are designated Standard Concepts, meaning these Concepts can be used as normative expressions of a clinical entity within the OMOP Common Data Model and standardized analytics. Each Standard Concept belongs to one Domain, which defines the location where the Concept would be expected to occur within the data tables of the CDM. Concepts can represent broad categories ('Cardiovascular disease'), detailed clinical elements ('Myocardial infarction of the anterolateral wall'), or modifying characteristics and attributes that define Concepts at various levels of detail (severity of a disease, associated morphology, etc.). Records in the Standardized Vocabularies tables are derived from national or international vocabularies such as SNOMED-CT, RxNorm, and LOINC, or custom OMOP Concepts defined to cover various aspects of observational data analysis.


### User Guidance
The primary purpose of the CONCEPT table is to provide a standardized representation of medical Concepts, allowing for consistent querying and analysis across the healthcare databases.
Users can join the CONCEPT table with other tables in the CDM to enrich clinical data with standardized Concept information or use the CONCEPT table as a reference for mapping clinical data from source terminologies to Standard Concepts.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE concept (
	concept_id integer NOT NULL,
	concept_name varchar(255) NOT NULL,
	domain_id varchar(20) NOT NULL,
	vocabulary_id varchar(20) NOT NULL,
	concept_class_id varchar(20) NOT NULL,
	standard_concept varchar(1) NOT NULL,
	concept_code varchar(50) NOT NULL,
	valid_start_date date NOT NULL,
	valid_end_date date NOT NULL,
	invalid_reason varchar(1) NOT NULL
)
```

## Input


## Output


## Example output record


