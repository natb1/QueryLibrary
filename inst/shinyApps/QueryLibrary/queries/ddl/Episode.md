<!---->

# Episode

## Description
The EPISODE table aggregates lower-level clinical events (VISIT_OCCURRENCE, DRUG_EXPOSURE, PROCEDURE_OCCURRENCE, DEVICE_EXPOSURE) into a higher-level abstraction representing clinically and analytically relevant disease phases,outcomes and treatments. The EPISODE_EVENT table connects qualifying clinical events (VISIT_OCCURRENCE, DRUG_EXPOSURE, PROCEDURE_OCCURRENCE, DEVICE_EXPOSURE) to the appropriate EPISODE entry. For example cancers including their development over time, their treatment, and final resolution.

### User Guidance
Valid Episode Concepts belong to the 'Episode' domain. For cancer episodes please see [article], for non-cancer episodes please see [article]. If your source data does not have all episodes that are relevant to the therapeutic area, write only those you can easily derive from the data. It is understood that that table is not currently expected to be comprehensive.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Episode (
	episode_id integer NOT NULL,
	person_id integer NOT NULL,
	episode_concept_id integer NOT NULL,
	episode_start_date date NOT NULL,
	episode_start_datetime datetime NOT NULL,
	episode_end_date date NOT NULL,
	episode_end_datetime datetime NOT NULL,
	episode_parent_id integer NOT NULL,
	episode_number integer NOT NULL,
	episode_object_concept_id integer NOT NULL,
	episode_type_concept_id integer NOT NULL,
	episode_source_value varchar(50) NOT NULL,
	episode_source_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


