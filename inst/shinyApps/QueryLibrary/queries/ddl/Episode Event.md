<!---->

# Episode Event

## Description
The EPISODE_EVENT table connects qualifying clinical events (such as CONDITION_OCCURRENCE, DRUG_EXPOSURE, PROCEDURE_OCCURRENCE, MEASUREMENT) to the appropriate EPISODE entry. For example, linking the precise location of the metastasis (cancer modifier in MEASUREMENT) to the disease episode.

### User Guidance
This connecting table is used instead of the FACT_RELATIONSHIP table for linking low-level events to abstracted Episodes.

### Etl Conventions
Some episodes may not have links to any underlying clinical events. For such episodes, the EPISODE_EVENT table is not populated.

## Query
```sql
CREATE TABLE Episode Event (
	episode_id integer NOT NULL,
	event_id integer NOT NULL,
	episode_event_field_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


