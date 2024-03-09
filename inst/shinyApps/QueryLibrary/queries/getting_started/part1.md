

# Getting Started

### Sharing SQL using Markdown Documents










 
## Query
```sql
-- The QueryLibrary is just SQL using the 
-- Common Data Model (CDM).
SELECT count(*) AS person_count FROM person

-- Common Table Expressions (CTEs)
-- can be used to write concise queries
-- by decomposing them into smaller subqueries.
INNER JOIN female USING gender_concept_id
INNER JOIN hiv USING person_id

-- CTEs can isolate logic from different SQL dialects.
-- See the links for the age &#34;alias&#34; in the next section.
JOIN age USING person_id

-- Input parameters allow the query to be 
-- used as a template.
WHERE age &gt; @min_age
```




## Common Table Expression (CTE)


- [age]({./age.md By HADES convention SQL queries use MS SQL Server dialect.}) 


- [age]({./dialect/sqlite/age.md But, referefences can be provided for any dialect.}) 




- [female]({./female.md A simple query for the female gender concept.}) 





 


 


 


 

## Description
The OHDSI QueryLibrary markdown specification
is basically just what you see in this document.
A full technical specification is available [here](./spec.md)
and may be useful for building applications that
read these documents.

Adding queries which use the OHDSI common data model (CDM)
to the query library, and referencing them in your 
applications has several benefits:

- You will be contributing to CDM data literacy 
	across the OHDSI ecosystem.
- Your CDM SQL queries will be version controlled, publicly
	validated and reusable across applications (without
	complex dependency management issues).
- You can reference the queries using the technology
	stack of choice. All that is required is to parse the 
	QueryLibrary markdown specification. This could mean
	one stack in production and one for analytics,
	or multiple analytics stacks for different purposes,
	all referencing the same queries from the library.

The QueryLibrary markdown specification allows a
health site to take a variety of complex 
data management problems
(data literacy, data quality, data lineage, etc.)
which are sometimes addressed with proprietary 
solutions, and instead reframe those problems as
simple markdown parsing problems.

&gt; Continue to [Part 2](./part2.md)




