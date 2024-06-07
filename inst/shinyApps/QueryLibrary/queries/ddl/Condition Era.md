<!---->

# Condition Era

## Description
A Condition Era is defined as a span of time when the Person is assumed to have a given condition. Similar to Drug Eras, Condition Eras are chronological periods of Condition Occurrence and every Condition Occurrence record should be part of a Condition Era. Combining individual Condition Occurrences into a single Condition Era serves two purposes:

- It allows aggregation of chronic conditions that require frequent ongoing care, instead of treating each Condition Occurrence as an independent event.
- It allows aggregation of multiple, closely timed doctor visits for the same Condition to avoid double-counting the Condition Occurrences.
For example, consider a Person who visits her Primary Care Physician (PCP) and who is referred to a specialist. At a later time, the Person visits the specialist, who confirms the PCP's original diagnosis and provides the appropriate treatment to resolve the condition. These two independent doctor visits should be aggregated into one Condition Era.

### User Guidance
NA

### Etl Conventions
Each Condition Era corresponds to one or many Condition Occurrence records that form a continuous interval.
The condition_concept_id field contains Concepts that are identical to those of the CONDITION_OCCURRENCE table records that make up the Condition Era. In contrast to Drug Eras, Condition Eras are not aggregated to contain Conditions of different hierarchical layers. The SQl Script for generating CONDITION_ERA records can be found [here](https://ohdsi.github.io/CommonDataModel/sqlScripts.html#condition_eras)
The Condition Era Start Date is the start date of the first Condition Occurrence.
The Condition Era End Date is the end date of the last Condition Occurrence. Condition Eras are built with a Persistence Window of 30 days, meaning, if no occurrence of the same condition_concept_id happens within 30 days of any one occurrence, it will be considered the condition_era_end_date.

## Query
```sql
CREATE TABLE condition_era (
	condition_era_id integer NOT NULL,
	person_id integer NOT NULL,
	condition_concept_id integer NOT NULL,
	condition_era_start_date date NOT NULL,
	condition_era_end_date date NOT NULL,
	condition_occurrence_count integer NOT NULL
)
```

## Input


## Output


## Example output record


