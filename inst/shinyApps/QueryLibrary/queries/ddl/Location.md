<!---->

# Location

## Description
The LOCATION table represents a generic way to capture physical location or address information of Persons and Care Sites.

### User Guidance
The current iteration of the LOCATION table is US centric. Until a major release to correct this, certain fields can be used to represent different international values. <br><br> - STATE can also be used for province or district<br>- ZIP is also the postal code or postcode <br>- COUNTY can also be used to represent region

### Etl Conventions
Each address or Location is unique and is present only once in the table. Locations do not contain names, such as the name of a hospital. In order to construct a full address that can be used in the postal service, the address information from the Location needs to be combined with information from the Care Site.

## Query
```sql
CREATE TABLE Location (
	location_id integer NOT NULL,
	address_1 varchar(50) NOT NULL,
	address_2 varchar(50) NOT NULL,
	city varchar(50) NOT NULL,
	state varchar(2) NOT NULL,
	zip varchar(9) NOT NULL,
	county varchar(20) NOT NULL,
	location_source_value varchar(50) NOT NULL,
	country_concept_id integer NOT NULL,
	country_source_value varchar(80) NOT NULL,
	latitude float NOT NULL,
	longitude float NOT NULL
)
```

## Input


## Output


## Example output record


