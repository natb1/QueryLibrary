<!--

-->

# Measurement










 

## Description
The MEASUREMENT table contains records of Measurements, i.e. structured values (numerical or categorical) obtained through systematic and standardized examination or testing of a Person or Person's sample. The MEASUREMENT table contains both orders and results of such Measurements as laboratory tests, vital signs, quantitative findings from pathology reports, etc. Measurements are stored as attribute value pairs, with the attribute as the Measurement Concept and the value representing the result. The value can be a Concept (stored in VALUE_AS_CONCEPT), or a numerical value (VALUE_AS_NUMBER) with a Unit (UNIT_CONCEPT_ID). The Procedure for obtaining the sample is housed in the PROCEDURE_OCCURRENCE table, though it is unnecessary to create a PROCEDURE_OCCURRENCE record for each measurement if one does not exist in the source data. Measurements differ from Observations in that they require a standardized test or some other activity to generate a quantitative or qualitative result. If there is no result, it is assumed that the lab test was conducted but the result was not captured.
### User Guidance
Measurements are predominately lab tests with a few exceptions, like blood pressure or function tests. Results are given in the form of a value and unit combination. When investigating measurements, look for operator_concept_ids (<, >, etc.).



 
## Query
```sql
CD
```








 

## Input




 

## Output



 

## Example output record





