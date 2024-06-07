<!---->

# Observation

## Description
The OBSERVATION table captures clinical facts about a Person obtained in the context of examination, questioning or a procedure. Any data that cannot be represented by any other domains, such as social and lifestyle facts, medical history, family history, etc. are recorded here.

### User Guidance
Observations differ from Measurements in that they do not require a standardized test or some other activity to generate clinical fact. Typical observations are medical history, family history, the stated need for certain treatment, social circumstances, lifestyle choices, healthcare utilization patterns, etc. If the generation clinical facts requires a standardized testing such as lab testing or imaging and leads to a standardized result, the data item is recorded in the MEASUREMENT table. If the clinical fact observed determines a sign, symptom, diagnosis of a disease or other medical condition, it is recorded in the CONDITION_OCCURRENCE table. Valid Observation Concepts are not enforced to be from any domain though they still should be Standard Concepts.

### Etl Conventions
Records whose Source Values map to any domain besides Condition, Procedure, Drug, Measurement or Device should be stored in the Observation table. Observations can be stored as attribute value pairs, with the attribute as the Observation Concept and the value representing the clinical fact. This fact can be a Concept (stored in VALUE_AS_CONCEPT), a numerical value (VALUE_AS_NUMBER), a verbatim string (VALUE_AS_STRING), or a datetime (VALUE_AS_DATETIME). Even though Observations do not have an explicit result, the clinical fact can be stated separately from the type of Observation in the VALUE_AS_* fields. It is recommended for Observations that are suggestive statements of positive assertion should have a value of 'Yes' (concept_id=4188539), recorded, even though the null value is the equivalent.

## Query
```sql
CREATE TABLE Observation (
	observation_id integer NOT NULL,
	person_id integer NOT NULL,
	observation_concept_id integer NOT NULL,
	observation_date date NOT NULL,
	observation_datetime datetime NOT NULL,
	observation_type_concept_id integer NOT NULL,
	value_as_number float NOT NULL,
	value_as_string varchar(60) NOT NULL,
	value_as_concept_id Integer NOT NULL,
	qualifier_concept_id integer NOT NULL,
	unit_concept_id integer NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	observation_source_value varchar(50) NOT NULL,
	observation_source_concept_id integer NOT NULL,
	unit_source_value varchar(50) NOT NULL,
	qualifier_source_value varchar(50) NOT NULL,
	value_source_value varchar(50) NOT NULL,
	observation_event_id integer NOT NULL,
	obs_event_field_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


