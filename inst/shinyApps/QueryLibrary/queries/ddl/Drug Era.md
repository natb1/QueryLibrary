<!---->

# Drug Era

## Description
A Drug Era is defined as a span of time when the Person is assumed to be exposed to a particular active ingredient. A Drug Era is not the same as a Drug Exposure: Exposures are individual records corresponding to the source when Drug was delivered to the Person, while successive periods of Drug Exposures are combined under certain rules to produce continuous Drug Eras. Every record in the DRUG_EXPOSURE table should be part of a drug era based on the dates of exposure. 

### User Guidance
NA

### Etl Conventions
The SQL script for generating DRUG_ERA records can be found [here](https://ohdsi.github.io/CommonDataModel/sqlScripts.html#drug_eras).

## Query
```sql
CREATE TABLE drug_era (
	drug_era_id integer NOT NULL,
	person_id integer NOT NULL,
	drug_concept_id integer NOT NULL,
	drug_era_start_date date NOT NULL,
	drug_era_end_date date NOT NULL,
	drug_exposure_count integer NOT NULL,
	gap_days integer NOT NULL
)
```

## Input


## Output


## Example output record


