<!---->

# Note

## Description
The NOTE table captures unstructured information that was recorded by a provider about a patient in free text (in ASCII, or preferably in UTF8 format) notes on a given date. The type of note_text is CLOB or varchar(MAX) depending on RDBMS.

### User Guidance
NA

### Etl Conventions
HL7/LOINC CDO is a standard for consistent naming of documents to support a range of use cases: retrieval, organization, display, and exchange. It guides the creation of LOINC codes for clinical notes. CDO annotates each document with 5 dimensions:

- **Kind of Document**: Characterizes the general structure of the document at a macro level (e.g. Anesthesia Consent)
- **Type of Service**: Characterizes the kind of service or activity (e.g. evaluations, consultations, and summaries). The notion of time sequence, e.g., at the beginning (admission) at the end (discharge) is subsumed in this axis. Example: Discharge Teaching.
- **Setting**: Setting is an extension of CMS's definitions (e.g. Inpatient, Outpatient)
- **Subject Matter Domain (SMD)**: Characterizes the subject matter domain of a note (e.g. Anesthesiology)
- **Role**: Characterizes the training or professional level of the author of the document, but does not break down to specialty or subspecialty (e.g. Physician)
Each combination of these 5 dimensions rolls up to a unique LOINC code.

According to CDO requirements, only 2 of the 5 dimensions are required to properly annotate a document; Kind of Document and any one of the other 4 dimensions.
However, not all the permutations of the CDO dimensions will necessarily yield an existing LOINC code. Each of these dimensions are contained in the OMOP Vocabulary under the domain of 'Meas Value' with each dimension represented as a Concept Class.

## Query
```sql
CREATE TABLE note (
	note_id integer NOT NULL,
	person_id integer NOT NULL,
	note_date date NOT NULL,
	note_datetime datetime NOT NULL,
	note_type_concept_id integer NOT NULL,
	note_class_concept_id integer NOT NULL,
	note_title varchar(250) NOT NULL,
	note_text varchar(MAX) NOT NULL,
	encoding_concept_id integer NOT NULL,
	language_concept_id integer NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	note_source_value varchar(50) NOT NULL,
	note_event_id integer NOT NULL,
	note_event_field_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


