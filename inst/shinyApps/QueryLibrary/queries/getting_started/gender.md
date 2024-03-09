<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started


-->

# Person Gender










 
## Query
```sql
SELECT 
	person_id,
	concept_name AS gender_concept_name 
FROM person
	LEFT JOIN concept
		ON person.gender_concept_id = concept.concept_id
```



