<!---->

# Payer Plan Period

## Description
The PAYER_PLAN_PERIOD table captures details of the period of time that a Person is continuously enrolled under a specific health Plan benefit structure from a given Payer. Each Person receiving healthcare is typically covered by a health benefit plan, which pays for (fully or partially), or directly provides, the care. These benefit plans are provided by payers, such as health insurances or state or government agencies. In each plan the details of the health benefits are defined for the Person or her family, and the health benefit Plan might change over time typically with increasing utilization (reaching certain cost thresholds such as deductibles), plan availability and purchasing choices of the Person. The unique combinations of Payer organizations, health benefit Plans and time periods in which they are valid for a Person are recorded in this table.

### User Guidance
A Person can have multiple, overlapping, Payer_Plan_Periods in this table. For example, medical and drug coverage in the US can be represented by two Payer_Plan_Periods. The details of the benefit structure of the Plan is rarely known, the idea is just to identify that the Plans are different.

### Etl Conventions
NA

## Query
```sql
CREATE TABLE payer_plan_period (
	payer_plan_period_id integer NOT NULL,
	person_id integer NOT NULL,
	payer_plan_period_start_date date NOT NULL,
	payer_plan_period_end_date date NOT NULL,
	payer_concept_id integer NOT NULL,
	payer_source_value varchar(50) NOT NULL,
	payer_source_concept_id integer NOT NULL,
	plan_concept_id integer NOT NULL,
	plan_source_value varchar(50) NOT NULL,
	plan_source_concept_id integer NOT NULL,
	sponsor_concept_id integer NOT NULL,
	sponsor_source_value varchar(50) NOT NULL,
	sponsor_source_concept_id integer NOT NULL,
	family_source_value varchar(50) NOT NULL,
	stop_reason_concept_id integer NOT NULL,
	stop_reason_source_value varchar(50) NOT NULL,
	stop_reason_source_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record

