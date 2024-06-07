<!---->

# Provider

## Description
The PROVIDER table contains a list of uniquely identified healthcare providers. These are individuals providing hands-on healthcare to patients, such as physicians, nurses, midwives, physical therapists etc.

### User Guidance
Many sources do not make a distinction between individual and institutional providers. The PROVIDER table contains the individual providers. If the source, instead of uniquely identifying individual providers, only provides limited information such as specialty, generic or 'pooled' Provider records are listed in the PROVIDER table.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Provider (
	provider_id integer NOT NULL,
	provider_name varchar(255) NOT NULL,
	npi varchar(20) NOT NULL,
	dea varchar(20) NOT NULL,
	specialty_concept_id integer NOT NULL,
	care_site_id integer NOT NULL,
	year_of_birth integer NOT NULL,
	gender_concept_id integer NOT NULL,
	provider_source_value varchar(50) NOT NULL,
	specialty_source_value varchar(50) NOT NULL,
	specialty_source_concept_id integer NOT NULL,
	gender_source_value varchar(50) NOT NULL,
	gender_source_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


