<!---->

# Visit Detail

## Description
The VISIT_DETAIL table is an optional table used to represents details of each record in the parent VISIT_OCCURRENCE table. A good example of this would be the movement between units in a hospital during an inpatient stay or claim lines associated with a one insurance claim. For every record in the VISIT_OCCURRENCE table there may be 0 or more records in the VISIT_DETAIL table with a 1:n relationship where n may be 0. The VISIT_DETAIL table is structurally very similar to VISIT_OCCURRENCE table and belongs to the visit domain.

### User Guidance
The configuration defining the Visit Detail is described by Concepts in the Visit Domain, which form a hierarchical structure. The Visit Detail record will have an associated to the Visit Occurrence record in two ways: <br> 1. The Visit Detail record will have the VISIT_OCCURRENCE_ID it is associated to 2. The VISIT_DETAIL_CONCEPT_ID  will be a descendant of the VISIT_CONCEPT_ID for the Visit.

### Etl Conventions
It is not mandatory that the VISIT_DETAIL table be filled in, but if you find that the logic to create VISIT_OCCURRENCE records includes the roll-up of multiple smaller records to create one picture of a Visit then it is a good idea to use VISIT_DETAIL. In EHR data, for example, a Person may be in the hospital but instead of one over-arching Visit their encounters are recorded as times they interacted with a health care provider. A Person in the hospital interacts with multiple providers multiple times a day so the encounters must be strung together using some heuristic (defined by the ETL) to identify the entire Visit. In this case the encounters would be considered Visit Details and the entire Visit would be the Visit Occurrence. In this example it is also possible to use the Vocabulary to distinguish Visit Details from a Visit Occurrence by setting the VISIT_CONCEPT_ID to [9201](https://athena.ohdsi.org/search-terms/terms/9201) and the VISIT_DETAIL_CONCEPT_IDs either to 9201 or its children to indicate where the patient was in the hospital at the time of care.

## Query
```sql
CREATE TABLE Visit Detail (
	visit_detail_id integer NOT NULL,
	person_id integer NOT NULL,
	visit_detail_concept_id integer NOT NULL,
	visit_detail_start_date date NOT NULL,
	visit_detail_start_datetime datetime NOT NULL,
	visit_detail_end_date date NOT NULL,
	visit_detail_end_datetime datetime NOT NULL,
	visit_detail_type_concept_id integer NOT NULL,
	provider_id integer NOT NULL,
	care_site_id integer NOT NULL,
	visit_detail_source_value varchar(50) NOT NULL,
	visit_detail_source_concept_id Integer NOT NULL,
	admitted_from_concept_id Integer NOT NULL,
	admitted_from_source_value varchar(50) NOT NULL,
	discharged_to_source_value varchar(50) NOT NULL,
	discharged_to_concept_id integer NOT NULL,
	preceding_visit_detail_id integer NOT NULL,
	parent_visit_detail_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL
)
```

## Input


## Output


## Example output record


