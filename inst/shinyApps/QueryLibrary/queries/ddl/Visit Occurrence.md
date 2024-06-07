<!---->

# Visit Occurrence

## Description
This table contains Events where Persons engage with the healthcare system for a duration of time. They are often also called "Encounters". Visits are defined by a configuration of circumstances under which they occur, such as (i) whether the patient comes to a healthcare institution, the other way around, or the interaction is remote, (ii) whether and what kind of trained medical staff is delivering the service during the Visit, and (iii) whether the Visit is transient or for a longer period involving a stay in bed.

### User Guidance
The configuration defining the Visit are described by Concepts in the Visit Domain, which form a hierarchical structure, but rolling up to generally familiar Visits adopted in most healthcare systems worldwide:

- [Inpatient Visit](https://athena.ohdsi.org/search-terms/terms/9201): Person visiting hospital, at a Care Site, in bed, for duration of more than one day, with physicians and other Providers permanently available to deliver service around the clock 
- [Emergency Room Visit](https://athena.ohdsi.org/search-terms/terms/9203): Person visiting dedicated healthcare institution for treating emergencies, at a Care Site, within one day, with physicians and Providers permanently available to deliver service around the clock
- [Emergency Room and Inpatient Visit](https://athena.ohdsi.org/search-terms/terms/262): Person visiting ER followed by a subsequent Inpatient Visit, where Emergency department is part of hospital, and transition from the ER to other hospital departments is undefined
- [Non-hospital institution Visit](https://athena.ohdsi.org/search-terms/terms/42898160): Person visiting dedicated institution for reasons of poor health, at a Care Site, long-term or permanently, with no physician but possibly other Providers permanently available to deliver service around the clock
- [Outpatient Visit](https://athena.ohdsi.org/search-terms/terms/9202): Person visiting dedicated ambulatory healthcare institution, at a Care Site, within one day, without bed, with physicians or medical Providers delivering service during Visit
- [Home Visit](https://athena.ohdsi.org/search-terms/terms/581476): Provider visiting Person, without a Care Site, within one day, delivering service
- [Telehealth Visit](https://athena.ohdsi.org/search-terms/terms/5083): Patient engages with Provider through communication media
- [Pharmacy Visit](https://athena.ohdsi.org/search-terms/terms/581458): Person visiting pharmacy for dispensing of Drug, at a Care Site, within one day
- [Laboratory Visit](https://athena.ohdsi.org/search-terms/terms/32036): Patient visiting dedicated institution, at a Care Site, within one day, for the purpose of a Measurement.
- [Ambulance Visit](https://athena.ohdsi.org/search-terms/terms/581478): Person using transportation service for the purpose of initiating one of the other Visits, without a Care Site, within one day, potentially with Providers accompanying the Visit and delivering service
- [Case Management Visit](https://athena.ohdsi.org/search-terms/terms/38004193): Person interacting with healthcare system, without a Care Site, within a day, with no Providers involved, for administrative purposes

The Visit duration, or 'length of stay', is defined as VISIT_END_DATE - VISIT_START_DATE. For all Visits this is <1 day, except Inpatient Visits and Non-hospital institution Visits. The CDM also contains the VISIT_DETAIL table where additional information about the Visit is stored, for example, transfers between units during an inpatient Visit.

### Etl Conventions
Visits can be derived easily if the source data contain coding systems for Place of Service or Procedures, like CPT codes for well visits. In those cases, the codes can be looked up and mapped to a Standard Visit Concept. Otherwise, Visit Concepts have to be identified in the ETL process. This table will contain concepts in the Visit domain. These concepts are arranged in a hierarchical structure to facilitate cohort definitions by rolling up to generally familiar Visits adopted in most healthcare systems worldwide. Visits can be adjacent to each other, i.e. the end date of one can be identical with the start date of the other. As a consequence, more than one-day Visits or their descendants can be recorded for the same day. Multi-day visits must not overlap, i.e. share days other than start and end days. It is often the case that some logic should be written for how to define visits and how to assign Visit_Concept_Id. For example, in US claims outpatient visits that appear to occur within the time period of an inpatient visit can be rolled into one with the same Visit_Occurrence_Id. In EHR data inpatient visits that are within one day of each other may be strung together to create one visit. It will all depend on the source data and how encounter records should be translated to visit occurrences. Providers can be associated with a Visit through the PROVIDER_ID field, or indirectly through PROCEDURE_OCCURRENCE records linked both to the VISIT and PROVIDER tables.

## Query
```sql
CREATE TABLE visit_occurrence (
	visit_occurrence_id integer NOT NULL,
	person_id integer NOT NULL,
	visit_concept_id integer NOT NULL,
	visit_start_date date NOT NULL,
	visit_start_datetime datetime NOT NULL,
	visit_end_date date NOT NULL,
	visit_end_datetime datetime NOT NULL,
	visit_type_concept_id Integer NOT NULL,
	provider_id integer NOT NULL,
	care_site_id integer NOT NULL,
	visit_source_value varchar(50) NOT NULL,
	visit_source_concept_id integer NOT NULL,
	admitted_from_concept_id integer NOT NULL,
	admitted_from_source_value varchar(50) NOT NULL,
	discharged_to_concept_id integer NOT NULL,
	discharged_to_source_value varchar(50) NOT NULL,
	preceding_visit_occurrence_id integer NOT NULL
)
```

## Input


## Output


## Example output record


