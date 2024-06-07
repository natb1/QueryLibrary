<!---->

# Care Site

## Description
The CARE_SITE table contains a list of uniquely identified institutional (physical or organizational) units where healthcare delivery is practiced (offices, wards, hospitals, clinics, etc.).

### User Guidance
NA

### Etl Conventions
Care site is a unique combination of location_id and place_of_service_source_value. Care site does not take into account the provider (human) information such a specialty. Many source data do not make a distinction between individual and institutional providers. The CARE_SITE table contains the institutional providers. If the source, instead of uniquely identifying individual Care Sites, only provides limited information such as Place of Service, generic or "pooled" Care Site records are listed in the CARE_SITE table. There can be hierarchical and business relationships between Care Sites. For example, wards can belong to clinics or departments, which can in turn belong to hospitals, which in turn can belong to hospital systems, which in turn can belong to HMOs.The relationships between Care Sites are defined in the FACT_RELATIONSHIP table.

## Query
```sql
CREATE TABLE Care Site (
	care_site_id integer NOT NULL,
	care_site_name varchar(255) NOT NULL,
	place_of_service_concept_id integer NOT NULL,
	location_id integer NOT NULL,
	care_site_source_value varchar(50) NOT NULL,
	place_of_service_source_value varchar(50) NOT NULL
)
```

## Input


## Output


## Example output record


