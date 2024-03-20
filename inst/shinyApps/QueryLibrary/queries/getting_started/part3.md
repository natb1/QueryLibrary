<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started



_Short:PGNvZGUgY2xhc3M9InNxbCI+LS0gV09SSyBJTiBQUk9HUkVTUwotLSAxLiBBZ3JlZSBvbiB0aGUgImRpbWVuc2lvbnMiIG9mIHlvdXIKLS0gICAgZGF0YWJhc2UgY2hhcmFjdGVyaXphdGlvbiB3aXRoIHlvdXIgZGF0YSBwYXJ0bmVycy4KZ2VuZGVyLAotLSBXSVA6IGZ1bGwgY29ob3J0IGVudHJ5IGV4aXQgY3JpdGVyaWEgZXRjLgphY2V0YW1pbm9waGVuX2Rvc2FnZV9tb250aCwKLS0gMi4gQWdyZWUgb24gdGhlIG1lYXN1cmVzIHRvIHNoYXJlLgptaW4oYWdlKSBBUyBtaW5fYWdlLAotLSBUaGVzZSBtZWFzdXJlcyBtYXkgYmUgY29uc3RyYWluZWQgZm9yIHByaXZhY3kgcmVhc29ucy4KQ0FTRSBXSEVOIG1heChhZ2UpIDwgODAgVEhFTiBtYXgoYWdlKSBFTFNFIDgwIGFzIG1heF9hZ2UKPC9jb2RlPiAuLi4=


-->

# Getting Started: Part 3

### Characterizing a CDM Data Set with a Cube










 
## Query
```sql
SELECT

  -- WORK IN PROGRESS

	-- 1. Agree on the "dimensions" of your
	--    database characterization with your data partners.
	--    You may choose from these dimensions to stratify
	--    your measures when analysing the data.
	gender,
	-- WIP: full cohort entry exit criteria etc.
	acetaminophen_dosage_month,

	-- 2. Agree on the measures to share.
	--    For example, share the distribution of
	--    of person ages across the chosen dimensions.
	min(age) AS min_age,
	-- These measures may be constrained for privacy reasons.
	CASE WHEN max(age) < 80 THEN max(age) ELSE 80 as max_age
	-- Your summary may include measures
	-- from the query library, or you can
	-- create your own.
	sum(acetaminophen_dosage) AS sum_acetaminophen_dosage
	-- Note: while "count" is decomposable
	-- "distinct count" is not.
	COUNT(acetaminophen_dosage.person_id) AS acetaminophen_person_count

-- The rest is SQL boilerplate.
FROM person
	LEFT JOIN acetaminophen_dosage USING person_id
	LEFT JOIN age USING person_id
	LEFT JOIN gender USING gender_concept_id

GROUP BY
	gender,
	acetaminophen_dosage_month
```


 

## Output



 

## Example output record




 

## Description
A "cube" is a common data structure
used to summarize a data set. It has
some limitations. Namely, it can only
be used for 
[decomposable](https://en.wikipedia.org/wiki/Aggregate_function#Decomposable_aggregate_functions)
summary metrics.
Some metrics such as the median are
not decomposable and so cannot be efficiently
represented in this data structure.

The advantage of a cube is that it is a summary
data structure that supports many 
analyses that would otherwise require the original
row level data. See how the example output
in this document allows for further summarization
and analysis of the data. The output is analysed
further in Part 4 to evaluate qualifications for
an example study. Many more dimensions
and measures could be added to this cube and it
would still be an efficient data structure for
transporting summary data for additional analysis.

Using a cube to summarize your data
could be an efficient way to assess
data partnerships without sharing row level
data. Creating this type of summary data
that is comparable with other data partners
can be referred to as [CDM Database Characterization](https://ohdsi.github.io/TheBookOfOhdsi/Characterization.html#database-level-characterization). Characterizing a
database using a cube
involves agreeing with your data partners
on two things:
- The "dimensions" used to stratify the summary
	measures. For example, this could include
	gender, and time.
- The (decomposable) measures, such as counts,
	that you are collecting. The specification
	of these measures can also serve as the basis
	for agreeing on strategy for data privacy with your
	data partners. For example, measures can be agreed 
	on that exclude anomaly values.

The QueryLibrary can be used to document and
share these decisions as a computable specification
using plain SQL similar to the example in this document.

> Continue to [Part 4](./part4.md)





## Common Table Expression (CTE)


- [acetaminophen_dosage](./acetaminophen_dosage.md) A query of person dosages by month. 




- [age](./age.md) Person age 




- [gender](./gender.md) A query of gender concepts 






