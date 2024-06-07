<!---->

# Condition Occurrence

## Description
This table contains records of Events of a Person suggesting the presence of a disease or medical condition stated as a diagnosis, a sign, or a symptom, which is either observed by a Provider or reported by the patient.

### User Guidance
Conditions are defined by Concepts from the Condition domain, which form a complex hierarchy. As a result, the same Person with the same disease may have multiple Condition records, which belong to the same hierarchical family. Most Condition records are mapped from diagnostic codes, but recorded signs, symptoms and summary descriptions also contribute to this table. Rule out diagnoses should not be recorded in this table, but in reality their negating nature is not always captured in the source data, and other precautions must be taken when when identifying Persons who should suffer from the recorded Condition. Record all conditions as they exist in the source data. Any decisions about diagnosis/phenotype definitions would be done through cohort specifications. These cohorts can be housed in the [COHORT](https://ohdsi.github.io/CommonDataModel/cdm531.html#payer_plan_period) table. Conditions span a time interval from start to end, but are typically recorded as single snapshot records with no end date. The reason is twofold: (i) At the time of the recording the duration is not known and later not recorded, and (ii) the Persons typically cease interacting with the healthcare system when they feel better, which leads to incomplete capture of resolved Conditions. The [CONDITION_ERA](https://ohdsi.github.io/CommonDataModel/cdm531.html#condition_era) table addresses this issue. Family history and past diagnoses ('history of') are not recorded in this table. Instead, they are listed in the [OBSERVATION](https://ohdsi.github.io/CommonDataModel/cdm531.html#observation) table. Codes written in the process of establishing the diagnosis, such as 'question of' of and 'rule out', should not represented here. Instead, they should be recorded in the [OBSERVATION](https://ohdsi.github.io/CommonDataModel/cdm531.html#observation) table, if they are used for analyses. However, this information is not always available.

### Etl Conventions
Source codes and source text fields mapped to Standard Concepts of the Condition Domain have to be recorded here.

## Query
```sql
CREATE TABLE condition_occurrence (
	condition_occurrence_id integer NOT NULL,
	person_id integer NOT NULL,
	condition_concept_id integer NOT NULL,
	condition_start_date date NOT NULL,
	condition_start_datetime datetime NOT NULL,
	condition_end_date date NOT NULL,
	condition_end_datetime datetime NOT NULL,
	condition_type_concept_id integer NOT NULL,
	condition_status_concept_id integer NOT NULL,
	stop_reason varchar(20) NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	condition_source_value varchar(50) NOT NULL,
	condition_source_concept_id integer NOT NULL,
	condition_status_source_value varchar(50) NOT NULL
)
```

## Input


## Output


## Example output record


