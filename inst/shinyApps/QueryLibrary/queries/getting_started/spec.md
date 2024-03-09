# QueryLibrary Markdown Specification

Most QueryLibrary extensions to the markdown specification
involve special treatment of document "sections"
with certain names. All sections are denoted by their 
`## Heading`, the order
of the sections does not matter,
and documents may include any
number of unspecified sections. The "comment tags"
and "name" of a QueryLibrary document are not 
sections and must
occur first in the document. The name of the document
is the first heading. The comment tags are
described below.

## Sections:

### Query

Documents must have a 
`## Query` section 
similar to this document which
is just SQL that is expected to follow
Hades conventions. That includes using the 
MS SQL Server dialect.

### Description

The `## Description` section
is the main documentation for the query.

### Inputs

Documents may include an Input section to suggest
how the query could be parameterized. Inputs must
be provided as a markdown table with (only) the columns
"Parameter", "Example", "Mandatory", and "Notes".
Inputs can be included in the query either using
the example value, or using the Hades/SQLRender
convention for templating (`@parameter_name`).

### Outputs and Example output record

Documents may include an Output table 
and/or and Example output record table
to provide
additional documentation of the query outputs.

The Output table must have
(only) the columns Field, and Description.

The Example output record table must have (only)
the columns Field, and Value.

### Common Table Expressions (CTE)

The `## Common Table Expression (CTE)`
section of the QueryLibrary markdown documents
allow queries to reference common subqueries. This
way, even very complex queries can be represented
in the query library:
- Large queries can be decomposed into smaller queries.
- Queries that rely on features that vary between 
    dialects can be isolated into subqueries.

CTEs are a markdown list of markdown anchor tags 
("links"). The text of the anchor is the SQL 
alias used in the query
and the anchor refers to the URL of any other 
QueryLibrary document.

In addition, a `## CTE Exclusion` list
provides a simple solution for writing 
queries with exclusion criteria that 
is both concise and works with all
SQL dialects. An example and more 
explanation is given in
"Getting Started: Part 2". 
An alias in the exclusion table that
references a document with the query 
`foo` is considered to be
equivalent to the following subqeury:
```
SELECT * FROM foo 
LEFT JOIN person 
WHERE foo.person_id != NULL
```

## Tags
Additional metadata can also be added to these 
documents by including an html comment in the head
of the document with newline separated
` + "`" + `key:value` + "`" + ` pairs. It is assumed that
these pairs will have whitespace trimmed during parsing.

Tags allow the markdown spec to be extended
further by the query authors with optional 
features such as tagging queries by author or use case.
See the raw text of this document for an example.

