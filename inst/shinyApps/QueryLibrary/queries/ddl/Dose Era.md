<!---->

# Dose Era

## Description
A Dose Era is defined as a span of time when the Person is assumed to be exposed to a constant dose of a specific active ingredient.

### User Guidance
NA

### Etl Conventions
Dose Eras will be derived from records in the DRUG_EXPOSURE table and the Dose information from the DRUG_STRENGTH table using a standardized algorithm. Dose Form information is not taken into account. So, if the patient changes between different formulations, or different manufacturers with the same formulation, the Dose Era is still spanning the entire time of exposure to the Ingredient.

## Query
```sql
CREATE TABLE dose_era (
	dose_era_id integer NOT NULL,
	person_id integer NOT NULL,
	drug_concept_id integer NOT NULL,
	unit_concept_id integer NOT NULL,
	dose_value float NOT NULL,
	dose_era_start_date date NOT NULL,
	dose_era_end_date date NOT NULL
)
```

## Input


## Output


## Example output record


