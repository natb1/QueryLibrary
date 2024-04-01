<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started



_Short:PHByZT48Y29kZSBjbGFzcz0ic3FsIj4tLSBXT1JLIElOIFBST0dSRVNTCi0tIDEuIEFncmVlIG9uIHRoZSAiZGltZW5zaW9ucyIgb2YgeW91cgotLSAgICBkYXRhYmFzZSBjaGFyYWN0ZXJpemF0aW9uIHdpdGggeW91ciBkYXRhIHBhcnRuZXJzLgpnZW5kZXIsCi0tIFdJUDogZnVsbCBjb2hvcnQgZW50cnkgZXhpdCBjcml0ZXJpYSBldGMuCmFjZXRhbWlub3BoZW5fZG9zYWdlX21vbnRoLAotLSAyLiBBZ3JlZSBvbiB0aGUgbWVhc3VyZXMgdG8gc2hhcmUuCm1pbihhZ2UpIEFTIG1pbl9hZ2UsCi0tIFRoZXNlIG1lYXN1cmVzIG1heSBiZSBjb25zdHJhaW5lZCBmb3IgcHJpdmFjeSByZWFzb25zLgpDQVNFIFdIRU4gbWF4KGFnZSkgPCA4MCBUSEVOIG1heChhZ2UpIEVMU0UgODAgYXMgbWF4X2FnZQo8L2NvZGU+IC4uLjwvcHJlPg==


-->

# Getting Started: Part 3

### Characterizing a CDM Data Set with a Cube










 
## Query
```sql
{[-- WORK IN PROGRESS -- 1. Agree on the "dimensions" of your --    database characterization with your data partners. --    You may choose from these dimensions to stratify --    your measures when analysing the data. -- WIP: full cohort entry exit criteria etc. -- 2. Agree on the measures to share. --    For example, share the distribution of --    of person ages across the chosen dimensions. min -- These measures may be constrained for privacy reasons. max max -- Your summary may include measures -- from the query library, or you can -- create your own. sum -- Note: while "count" is decomposable -- "distinct count" is not. -- The rest is SQL boilerplate. FROM]}
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






