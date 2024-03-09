
	

	# Getting Started
	
	### Sharing SQL using Markdown Documents
	

	

	

	

	

	

	

	

	
		 
	## Query
	```sql
	[10 32 32 32 32 45 45 32 84 104 101 32 81 117 101 114 121 76 105 98 114 97 114 121 32 105 115 32 106 117 115 116 32 83 81 76 32 117 115 105 110 103 32 116 104 101 32 10 9 9 45 45 32 67 111 109 109 111 110 32 68 97 116 97 32 77 111 100 101 108 32 40 67 68 77 41 46 10 9 9 83 69 76 69 67 84 32 99 111 117 110 116 40 42 41 32 65 83 32 112 101 114 115 111 110 95 99 111 117 110 116 32 70 82 79 77 32 112 101 114 115 111 110 10 10 9 9 45 45 32 67 111 109 109 111 110 32 84 97 98 108 101 32 69 120 112 114 101 115 115 105 111 110 115 32 40 67 84 69 115 41 10 9 9 45 45 32 99 97 110 32 98 101 32 117 115 101 100 32 116 111 32 119 114 105 116 101 32 99 111 110 99 105 115 101 32 113 117 101 114 105 101 115 10 9 9 45 45 32 98 121 32 100 101 99 111 109 112 111 115 105 110 103 32 116 104 101 109 32 105 110 116 111 32 115 109 97 108 108 101 114 32 115 117 98 113 117 101 114 105 101 115 46 10 9 9 73 78 78 69 82 32 74 79 73 78 32 102 101 109 97 108 101 32 85 83 73 78 71 32 103 101 110 100 101 114 95 99 111 110 99 101 112 116 95 105 100 10 9 9 73 78 78 69 82 32 74 79 73 78 32 104 105 118 32 85 83 73 78 71 32 112 101 114 115 111 110 95 105 100 10 10 9 9 45 45 32 67 84 69 115 32 99 97 110 32 105 115 111 108 97 116 101 32 108 111 103 105 99 32 102 114 111 109 32 100 105 102 102 101 114 101 110 116 32 83 81 76 32 100 105 97 108 101 99 116 115 46 10 9 9 74 79 73 78 32 97 103 101 32 85 83 73 78 71 32 112 101 114 115 111 110 95 105 100 10 10 9 9 45 45 32 73 110 112 117 116 32 112 97 114 97 109 101 116 101 114 115 32 97 108 108 111 119 32 116 104 101 32 113 117 101 114 121 32 116 111 32 98 101 32 10 9 9 45 45 32 117 115 101 100 32 97 115 32 97 32 116 101 109 112 108 97 116 101 46 10 9 9 87 72 69 82 69 32 97 103 101 32 62 32 64 109 105 110 95 97 103 101 10 32 32]
	```
	
		
	
	## Common Table Expression (CTE)
	
	
	- [age](./dialect/sqlite/age.md) 
	
	- [age](./dialect/sqlserver/age.md) 
	
	
	
	- [female](./female.md) 
	
	
	
	
		 
	
	
		 
	
	
		 
	
	
		 
	
	## Description
	The OHDSI QueryLibrary markdown is a simple
		extension to the markdown document specification.
		This example document shows how SQL
		queries are represented in the QueryLibrary using markdown.

		Adding queries using the OHDSI common data model (CDM)
		to the query library, and referencing them in your 
		applications has several benefits:

		- Your CDM SQL queries will be version controlled, publicly
		  validated and reusable across applications.
		- You can reference the queries using the technology
		  stack of choice. All that is required is to parse the 
			QueryLibrary markdown specification. This could mean
			one stack in production and one for analytics,
			or multiple analytics stacks for different purposes,
			all referencing the same queries from the library.
		- You will be contributing to CDM data literacy 
		  across the OHDSI ecosystem.

		The QueryLibrary markdown specification allows a
		health site to take a variety of complex 
		data management problems
		(data literacy, data quality, data lineage, etc.)
    which are sometimes addressed with proprietary 
		solutions, and instead reframe those problems as
		simple markdown parsing problems.

    ### QueryLibrary Markdown Specification

		Most QueryLibrary extensions to the markdown specification
		involve special treatment of document &#34;sections&#34;
		with certain names. All sections are denoted by their 
		`## Heading`, the order
		of the sections does not matter,
		and documents may include any
		number of unspecified sections. The &#34;comment tags&#34;
		and &#34;name&#34; of a QueryLibrary document are not 
		sections and must
		occur first in the document. The name of the document
		is the first heading. The comment tags are
		described below.

		#### Sections:

		- Query

			Documents must have a 
			`## Query` section 
			similar to this document which
			is just SQL that is expected to follow
			Hades conventions. That includes using the 
			MS SQL Server dialect.

		- Description

			The `## Description` section
			is the main documentation for the query.

		- Inputs

			Documents may include an Input section to suggest
			how the query could be parameterized. Inputs must
			be provided as a markdown table with (only) the columns
			&#34;Parameter&#34;, &#34;Example&#34;, &#34;Mandatory&#34;, and &#34;Notes&#34;.
			Inputs can be included in the query either using
			the example value, or using the Hades/SQLRender
			convention for templating (
			`@parameter_name).

		- Outputs and Example output record

			Documents may include an Output table 
			and/or and Example output record table
			to provide
			additional documentation of the query outputs.

			The Output table must have
			(only) the columns Field, and Description.

			The Example output record table must have (only)
			the columns Field, and Value.

		- Common Table Expressions (CTE)

			The 
			`## Common Table Expression (CTE)`
			section of the QueryLibrary markdown documents
			allow queries to reference common subqueries. This
			way, even very complex queries can be represented
			in the query library:
			- Large queries can be decomposed into smaller queries.
			- Queries that rely on features that vary between 
			  dialects can be isolated into subqueries.

			CTEs are a markdown list of markdown anchor tags 
			(&#34;links&#34;). The text of the anchor is the SQL 
			alias used in the query
			and the anchor refers to the URL of any other 
			QueryLibrary document.

			In addition, 
			a `## CTE Exclusion` list
			provides a simple solution for writing 
			queries with exclusion criteria that 
			is both concise and works with all
			SQL dialects. An example and more 
			explanation is given in
			&#34;Getting Started: Part 2&#34;. 
			An alias in the exclusion table that
			references a document with the query 
			`foo` is considered to be
			equivalent to the following subqeury:
			```
			SELECT * FROM foo 
			LEFT JOIN person 
			WHERE foo.person_id != NULL
			```

		#### Tags
		Additional metadata can also be added to these 
		documents by including an html comment in the head
		of the document with newline separated
		`key:value` pairs. It is assumed that
		these pairs will have whitespace trimmed during parsing.
		
		Tags allow the markdown spec to be extended
		further by the query authors with optional 
		features such as tagging queries by author or use case.
		See the raw text of this document for an example.
	
	
		
