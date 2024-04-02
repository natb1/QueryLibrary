<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started



_Order:Query,Common Table Expression (CTE),Input,Output,Example output record,Description



_Short:PHByZT48Y29kZSBjbGFzcz0ic3FsIj4tLSBUaGUgUXVlcnlMaWJyYXJ5IGlzIGp1c3QgU1FMIHVzaW5nIHRoZSBDb21tb24gRGF0YSBNb2RlbCAoQ0RNKS4KU0VMRUNUIENPVU5UKCopIEFTIHBlcnNvbl9jb3VudCBGUk9NIHBlcnNvbgotLSBQaGVub3R5cGUgcXVlcmllcy4KSU5ORVIgSk9JTiBmZW1hbGUgVVNJTkcgZ2VuZGVyX2NvbmNlcHRfaWQKSU5ORVIgSk9JTiBoaXYgVVNJTkcgcGVyc29uX2lkCi0tIFBvcHVsYXRpb24gY2hhcmFjdGVyaXN0aWNzLgpMRUZUIEpPSU4gYWdlIFVTSU5HIHBlcnNvbl9pZApXSEVSRSBhZ2UgPiBAbWluX2FnZQo8L2NvZGU+IC4uLjwvcHJlPg==


-->

# Getting Started

### Sharing SQL using Markdown Documents










 
## Query
```sql
-- The QueryLibrary is just SQL using the 
-- Common Data Model (CDM).
SELECT COUNT(*) AS person_count, foo 
FROM person

-- Common Table Expressions (CTEs)
-- can be used to write concise queries
-- by decomposing them into smaller subqueries,
-- for example phenotype queries.
INNER JOIN female USING (person_id)
INNER JOIN hiv USING (person_id)

-- CTEs can isolate logic from different SQL dialects.
-- See the links for the age "alias" in the next section.
LEFT JOIN age USING (person_id)

-- Input parameters allow the query to be 
-- used as a template.
WHERE age > @min_age
```




## Common Table Expression (CTE)


- [age](./age.md) By HADES convention SQL queries use MS SQL Server dialect. 


- [age](./dialect/sqlite/age.md) But, references can be provided for any dialect. 




- [female](./female.md) A simple query for the female gender concept. 




- [hiv](./hiv.md) A query for persons using the OHDSI phenotype library. 





 

## Input
| PARAMETER | EXAMPLE | MANDATORY |                             NOTES                             |
|-----------|---------|-----------|---------------------------------------------------------------|
| @min_age  |      18 | true      | Parameters allow QueryLibrary users to share query templates. |




 

## Output
|    FIELD     |         DESCRIPTION         |
|--------------|-----------------------------|
| person_count | An example summary measure. |



 

## Example output record
|    FIELD     | VALUE |
|--------------|-------|
| person_count |   100 |




 

## Description
The OHDSI QueryLibrary markdown specification
is basically just what you see in this document.
A full technical specification is available [here](./spec.md)
and may be useful for building applications that
read these documents.

> See also: <a target="_blank" href="https://ohdsi.github.io/TheBookOfOhdsi/SqlAndR.html">The Book of OHDSI: SQL and R</a>

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
(data literacy, data quality, database characterization, etc.)
which are sometimes addressed with proprietary 
solutions, and instead reframe those problems as
simple markdown parsing problems.

> Continue to [Part 2](./part2.md)




