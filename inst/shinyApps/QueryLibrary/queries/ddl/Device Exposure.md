<!---->

# Device Exposure

## Description
The Device domain captures information about a person's exposure to a foreign physical object or instrument which is used for diagnostic or therapeutic purposes through a mechanism beyond chemical action. Devices include implantable objects (e.g. pacemakers, stents, artificial joints), medical equipment and supplies (e.g. bandages, crutches, syringes), other instruments used in medical procedures (e.g. sutures, defibrillators) and material used in clinical care (e.g. adhesives, body material, dental material, surgical material).

### User Guidance
The distinction between Devices or supplies and Procedures are sometimes blurry, but the former are physical objects while the latter are actions, often to apply a Device or supply.

### Etl Conventions
Source codes and source text fields mapped to Standard Concepts of the Device Domain have to be recorded here.

## Query
```sql
CREATE TABLE Device Exposure (
	device_exposure_id integer NOT NULL,
	person_id integer NOT NULL,
	device_concept_id integer NOT NULL,
	device_exposure_start_date date NOT NULL,
	device_exposure_start_datetime datetime NOT NULL,
	device_exposure_end_date date NOT NULL,
	device_exposure_end_datetime datetime NOT NULL,
	device_type_concept_id integer NOT NULL,
	unique_device_id varchar(255) NOT NULL,
	production_id varchar(255) NOT NULL,
	quantity integer NOT NULL,
	provider_id integer NOT NULL,
	visit_occurrence_id integer NOT NULL,
	visit_detail_id integer NOT NULL,
	device_source_value varchar(50) NOT NULL,
	device_source_concept_id integer NOT NULL,
	unit_concept_id integer NOT NULL,
	unit_source_value varchar(50) NOT NULL,
	unit_source_concept_id integer NOT NULL
)
```

## Input


## Output


## Example output record


