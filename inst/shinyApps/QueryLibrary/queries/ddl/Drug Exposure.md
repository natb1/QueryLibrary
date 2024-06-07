<!---->

# Drug Exposure

## Description
This table captures records about the exposure to a Drug ingested or otherwise introduced into the body. A Drug is a biochemical substance formulated in such a way that when administered to a Person it will exert a certain biochemical effect on the metabolism. Drugs include prescription and over-the-counter medicines, vaccines, and large-molecule biologic therapies. Radiological devices ingested or applied locally do not count as Drugs.

### User Guidance
The purpose of records in this table is to indicate an exposure to a certain drug as best as possible. In this context a drug is defined as an active ingredient. Drug Exposures are defined by Concepts from the Drug domain, which form a complex hierarchy. As a result, one DRUG_SOURCE_CONCEPT_ID may map to multiple standard concept ids if it is a combination product. Records in this table represent prescriptions written, prescriptions dispensed, and drugs administered by a provider to name a few. The DRUG_TYPE_CONCEPT_ID can be used to find and filter on these types. This table includes additional information about the drug products, the quantity given, and route of administration.

### Etl Conventions
Information about quantity and dose is provided in a variety of different ways and it is important for the ETL to provide as much information as possible from the data. Depending on the provenance of the data fields may be captured differently i.e. quantity for drugs administered may have a separate meaning from quantity for prescriptions dispensed. If a patient has multiple records on the same day for the same drug or procedures the ETL should not de-dupe them unless there is probable reason to believe the item is a true data duplicate. Take note on how to handle refills for prescriptions written.

## Query
```sql
CREATE TABLE Drug Exposure (
	drug_exposure_id integer NOT NULL,
	person_id integer NOT NULL,
	drug_concept_id integer NOT NULL,
	drug_exposure_start_date date NOT NULL,
	drug_exposure_start_datetime datetime NOT NULL,
	drug_exposure_end_date date NOT NULL,
	drug_exposure_end_datetime datetime NOT NULL,
	verbatim_end_date date NOT NULL,
	drug_type_concept_id integer NOT NULL,
	stop_reason varchar(20) NOT NULL,
	refills integer NOT NULL,
	quantity float NOT NULL,
	days_supply integer NOT NULL,
	sig varchar(MAX) NOT NULL,
	route_concept_id integer NOT NULL,
	lot_number varchar(50) NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	drug_source_value varchar(50) NOT NULL,
	drug_source_concept_id integer NOT NULL,
	route_source_value varchar(50) NOT NULL,
	dose_unit_source_value varchar(50) NOT NULL
)
```

## Input


## Output


## Example output record


