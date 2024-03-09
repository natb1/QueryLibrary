

# Getting Started: Part 4

### Comparing Cubes in a Data Network










		 

## Description
In this query three example data partners are named 
&#34;eunomia&#34;, &#34;synthea&#34;, and &#34;mimic&#34;. They 
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

SELECT partner AS eligible_partner
FROM (
	SELECT *, &#34;eunomia&#34; AS partner FROM eunomia_partner
	UNION ALL 
	SELECT *, &#34;sythea&#34; AS partner FROM synthea_partner
	UNION ALL 
	SELECT *, &#34;mimic&#34; AS partner FROM mimic_partner
)

-- At least 100 persons with acetaminophen dosage
-- for each of the given months, for each of the
-- given genders.
WHERE
	month &gt; &#34;2020-01&#34;
	AND (
		gender_concept_name IN (&#34;Male&#34;, &#34;Female&#34;)
	)
GROUP BY partner
HAVING min(acetaminophen_person_count) &gt; 100
  
```


		

## Common Table Expression (CTE)


- [eunomia_partner]({./example_data/eunomia_partner.md Example database characterization from &#39;Eunomia&#39; partner}) 




- [mimix_partner]({./example_data/mimic_partner.md Example database characterization from &#39;Mimic&#39; partner}) 




- [synthea_partner]({./example_data/synthea_partner.md Example database characterization from &#39;Synthea&#39; partner}) 





		 


		
