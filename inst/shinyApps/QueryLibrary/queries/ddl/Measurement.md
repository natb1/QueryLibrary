<!---->

# Measurement

## Description
The MEASUREMENT table contains records of Measurements, i.e. structured values (numerical or categorical) obtained through systematic and standardized examination or testing of a Person or Person's sample. The MEASUREMENT table contains both orders and results of such Measurements as laboratory tests, vital signs, quantitative findings from pathology reports, etc. Measurements are stored as attribute value pairs, with the attribute as the Measurement Concept and the value representing the result. The value can be a Concept (stored in VALUE_AS_CONCEPT), or a numerical value (VALUE_AS_NUMBER) with a Unit (UNIT_CONCEPT_ID). The Procedure for obtaining the sample is housed in the PROCEDURE_OCCURRENCE table, though it is unnecessary to create a PROCEDURE_OCCURRENCE record for each measurement if one does not exist in the source data. Measurements differ from Observations in that they require a standardized test or some other activity to generate a quantitative or qualitative result. If there is no result, it is assumed that the lab test was conducted but the result was not captured.

### User Guidance
Measurements are predominately lab tests with a few exceptions, like blood pressure or function tests. Results are given in the form of a value and unit combination. When investigating measurements, look for operator_concept_ids (<, >, etc.).

### Etl Conventions
Only records where the source value maps to a Concept in the measurement domain should be included in this table. Even though each Measurement always has a result, the fields VALUE_AS_NUMBER and VALUE_AS_CONCEPT_ID are not mandatory as often the result is not given in the source data. When the result is not known, the Measurement record represents just the fact that the corresponding Measurement was carried out, which in itself is already useful information for some use cases. For some Measurement Concepts, the result is included in the test. For example, ICD10 CONCEPT_ID [45548980](https://athena.ohdsi.org/search-terms/terms/45548980) 'Abnormal level of unspecified serum enzyme' indicates a Measurement and the result (abnormal). In those situations, the CONCEPT_RELATIONSHIP table in addition to the 'Maps to' record contains a second record with the relationship_id set to 'Maps to value'. In this example, the 'Maps to' relationship directs to [4046263](https://athena.ohdsi.org/search-terms/terms/4046263) 'Enzyme measurement' as well as a 'Maps to value' record to [4135493](https://athena.ohdsi.org/search-terms/terms/4135493) 'Abnormal'.

## Query
```sql
CREATE TABLE measurement (
	measurement_id integer NOT NULL,
	person_id integer NOT NULL,
	measurement_concept_id integer NOT NULL,
	measurement_date date NOT NULL,
	measurement_datetime datetime NOT NULL,
	measurement_time varchar(10) NOT NULL,
	measurement_type_concept_id integer NOT NULL,
	operator_concept_id integer NOT NULL,
	value_as_number float NOT NULL,
	value_as_concept_id integer NOT NULL,
	unit_concept_id integer NOT NULL,
	range_low float NOT NULL,
	range_high float NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	measurement_source_value varchar(50) NOT NULL,
	measurement_source_concept_id integer NOT NULL,
	unit_source_value varchar(50) NOT NULL,
	unit_source_concept_id integer NOT NULL,
	value_source_value varchar(50) NOT NULL,
	measurement_event_id integer NOT NULL,
	meas_event_field_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


