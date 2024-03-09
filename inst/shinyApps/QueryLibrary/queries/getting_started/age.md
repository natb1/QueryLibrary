<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Getting Started


-->

# Person Age










 
## Query
```sql
SELECT 
	person_id,
	DATEDIFF(year, birth_datetime, GETDATE()) as age
FROM person
```



