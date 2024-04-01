<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started



_Short:PHA+SW4gdGhpcyBxdWVyeSB0aHJlZSBleGFtcGxlIGRhdGEgcGFydG5lcnMgYXJlIG5hbWVkCiJldW5vbWlhIiwgInN5bnRoZWEiLCBhbmQgIm1pbWljIi4gVGhleSBoYXZlIGFsbCBzaGFyZWQKYW5kIGV4ZWN1dGVkIHRoZSBxdWVyeSBpbiBwYXJ0IDMgaW4gb3JkZXIgdG8gY3JlYXRlIGEKZGF0YWJhc2UgY2hhcmFjdGVyaXphdGlvbiAuLi48L3A+


-->

# Getting Started: Part 4

### Comparing Cubes in a Data Network










		 

## Description
In this query three example data partners are named 
"eunomia", "synthea", and "mimic". They 
have all shared and executed the query in part 3
in order to create a database characterization.
Data partners can use their preferred method
of sharing those summary results with each other
(ex. emailing CSV files, publishing the results on
github, or using a shared database).

Given this set of summary results, 
the following query can be used to 
document and evaluate the acceptance criteria for
these partners in a particular study.



		 
## Query
```sql
{[FROM FROM FROM FROM -- At least 100 persons with acetaminophen dosage -- for each of the given months, for each of the -- given genders. min]}
```


		

## Common Table Expression (CTE)


- [eunomia_partner](./example_data/eunomia_partner.md) Example database characterization from 'Eunomia' partner 




- [mimix_partner](./example_data/mimic_partner.md) Example database characterization from 'Mimic' partner 




- [synthea_partner](./example_data/synthea_partner.md) Example database characterization from 'Synthea' partner 





		 

## Output



		
