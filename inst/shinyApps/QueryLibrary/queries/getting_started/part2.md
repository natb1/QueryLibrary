<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started



_Short:PHByZT48Y29kZSBjbGFzcz0ic3FsIj4tLSBJTk5FUiBKT0lOIGlzIHNvIG5hbWVkIGJlY2F1c2UgaXQgaXMgYW5hbG9nb3VzCi0tIHRvIGZpbmRpbmcgdGhlIGludGVyc2VjdGlvbiBvZiB0d28gb3IgbW9yZSBzZXRzLgotLSBTZWUgdGhlIGxpbmtlZCBxdWVyaWVzIGluIHRoZSBDVEUgc2VjdGlvbgotLSB0byB1bmRlcnN0YW5kIGhvdyB0aGVzZSBzdWJzZXRzIGFyZSBjcmVhdGVkLgotLSBUaGUgUXVlcnlMaWJyYXJ5IGluY2x1ZGVzIG1hbnkgcHJlYnVpbHQgcXVlcmllcwotLSBmb3IgdGhpcywgaW5jbHVkaW5nIHRoZSBPSERTSSBwaGVub3R5cGUgbGlicmFyeS4KSU5ORVIgSk9JTiBmZW1hbGUgVVNJTkcgZ2VuZGVyX2NvbmNlcHRfaWQKSU5ORVIgSk9JTiBoaXYgVVNJTkcgcGVyc29uX2lkCjwvY29kZT4gLi4uPC9wcmU+


-->

# Getting Started: Part 2

### Cohort Inclusion Criteria










 
## Query
```sql
-- 
SELECT COUNT(*) AS person_count FROM person

-- INNER JOIN is so named because it is analogous
-- to finding the intersection of two or more sets.
-- See the linked queries in the CTE section
-- to understand how these subsets are created.
-- The QueryLibrary includes many prebuilt queries
-- for this, including the OHDSI phenotype library.
INNER JOIN female USING gender_concept_id
INNER JOIN hiv USING person_id

-- Note:
-- All SQL dialects have multiple ways of representing
-- set operations and the implementation may have a
-- performance impact that differs depending
-- on your data platform. The SQL syntax
-- here is generally performant, and doesn't rely
-- on features of any one dialect.

-- The most concise way to create exclusion criteria would
-- be to INNER JOIN a suqquery that is the "anti-set", 
-- ex. "not insured":
INNER JOIN uninsured USING person_id

-- Or, if doing so is inconvenient,
-- this syntax is more verbose, but more 
-- flexible and supported by all SQL dialects.
-- The ## CTE Exclusion section can be used 
-- as a shorthand for the syntax below
-- while writing the more concise INNER JOIN syntax above.
-- See the ## CTE Exclusion section below for an example.
LEFT JOIN insured USING person_id
WHERE insured.person_id IS NULL
```




## Common Table Expression (CTE)


- [female](./female.md) A simple query for the female gender concept. 




- [hiv](./hiv.md) A query of persons using the phenotype library. 







## CTE Exclusion


- [uninsured](./insured.md) The insured query is expected to be used as an exlusion criteria. 





 

## Description
> Continue to [Part 3](./part3.md)




