<!--


Author:Nathan Buesgens



CDM Version:5.4



Use Case:Characteristic


-->

# Person Age










 
## Query
```sql
SELECT 
	person_id,
	CAST(STRFTIME('%Y.%m%d', 'now') - strftime('%Y.%m%d', birth_datetime) as int)
FROM person
```



