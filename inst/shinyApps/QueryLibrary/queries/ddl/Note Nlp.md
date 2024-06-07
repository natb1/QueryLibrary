<!---->

# Note Nlp

## Description
The NOTE_NLP table encodes all output of NLP on clinical notes. Each row represents a single extracted term from a note.

### User Guidance
NA

### Etl Conventions
NA

## Query
```sql
CREATE TABLE note_nlp (
	note_nlp_id integer NOT NULL,
	note_id integer NOT NULL,
	section_concept_id integer NOT NULL,
	snippet varchar(250) NOT NULL,
	&#34;offset&#34; varchar(50) NOT NULL,
	lexical_variant varchar(250) NOT NULL,
	note_nlp_concept_id integer NOT NULL,
	note_nlp_source_concept_id integer NOT NULL,
	nlp_system varchar(250) NOT NULL,
	nlp_date date NOT NULL,
	nlp_datetime datetime NOT NULL,
	term_exists varchar(1) NOT NULL,
	term_temporal varchar(50) NOT NULL,
	term_modifiers varchar(2000) NOT NULL
)
```

## Input


## Output


## Example output record


