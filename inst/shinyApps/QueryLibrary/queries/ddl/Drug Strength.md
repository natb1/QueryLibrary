<!---->

# Drug Strength

## Description
The DRUG_STRENGTH table contains structured content about the amount or concentration and associated units of a specific ingredient contained within a particular drug product. This table is supplemental information to support standardized analysis of drug utilization.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE Drug Strength (
	drug_concept_id integer NOT NULL,
	ingredient_concept_id integer NOT NULL,
	amount_value float NOT NULL,
	amount_unit_concept_id integer NOT NULL,
	numerator_value float NOT NULL,
	numerator_unit_concept_id integer NOT NULL,
	denominator_value float NOT NULL,
	denominator_unit_concept_id integer NOT NULL,
	box_size integer NOT NULL,
	valid_start_date date NOT NULL,
	valid_end_date date NOT NULL,
	invalid_reason varchar(1) NOT NULL
)
```

## Input


## Output


## Example output record


