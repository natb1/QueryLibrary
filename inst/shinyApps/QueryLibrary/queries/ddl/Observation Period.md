<!---->

# Observation Period

## Description
This table contains records which define spans of time during which two conditions are expected to hold: (i) Clinical Events that happened to the Person are recorded in the Event tables, and (ii) absense of records indicate such Events did not occur during this span of time.

### User Guidance
For each Person, one or more OBSERVATION_PERIOD records may be present, but they will not overlap or be back to back to each other. Events may exist outside all of the time spans of the OBSERVATION_PERIOD records for a patient, however, absence of an Event outside these time spans cannot be construed as evidence of absence of an Event. Incidence or prevalence rates should only be calculated for the time of active OBSERVATION_PERIOD records. When constructing cohorts, outside Events can be used for inclusion criteria definition, but without any guarantee for the performance of these criteria. Also, OBSERVATION_PERIOD records can be as short as a single day, greatly disturbing the denominator of any rate calculation as part of cohort characterizations. To avoid that, apply minimal observation time as a requirement for any cohort definition.

### Etl Conventions
Each Person needs to have at least one OBSERVATION_PERIOD record, which should represent time intervals with a high capture rate of Clinical Events. Some source data have very similar concepts, such as enrollment periods in insurance claims data. In other source data such as most EHR systems these time spans need to be inferred under a set of assumptions. It is the discretion of the ETL developer to define these assumptions. In many ETL solutions the start date of the first occurrence or the first high quality occurrence of a Clinical Event (Condition, Drug, Procedure, Device, Measurement, Visit) is defined as the start of the OBSERVATION_PERIOD record, and the end date of the last occurrence of last high quality occurrence of a Clinical Event, or the end of the database period becomes the end of the OBSERVATOIN_PERIOD for each Person. If a Person only has a single Clinical Event the OBSERVATION_PERIOD record can be as short as one day. Depending on these definitions it is possible that Clinical Events fall outside the time spans defined by OBSERVATION_PERIOD records. Family history or history of Clinical Events generally are not used to generate OBSERVATION_PERIOD records around the time they are referring to. Any two overlapping or adjacent OBSERVATION_PERIOD records have to be merged into one.

## Query
```sql
CREATE TABLE Observation Period (
	observation_period_id integer NOT NULL,
	person_id integer NOT NULL,
	observation_period_start_date date NOT NULL,
	observation_period_end_date date NOT NULL,
	period_type_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


