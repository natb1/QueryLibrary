
	

	# Getting Started: Part 3
	
	### Summarizing a CDM Data Set with a Cube
	

	

	

	

	

	

	

	

	
		 
	
	## Description
	A &#34;cube&#34; is a common data structure
		used to summarize a data set. It has
		some limitations. Namely, it can only
		be used for &#34;decomposable&#34; summary metrics.
		Summary functions such as the median are
		not decomposable and so cannot be efficiently
		represented in this data structure.

		The advantage of a cube is that it is a summary
		data structure that supports many 
		analyses that would otherwise require the original
		row level data. See how the example output
		in this document allows for further summarization
		and analysis of the data. The output is analysed
		further in Part 4. Many more dimensions
		and measures could be added to this cube and it
		would still be an efficient data structure for
		transporting summary data.

		Using a cube to summarize your data
		could be an efficient way to assess
		data partnerships without sharing row level
		data. Creating this type of summary data
		that is comparable with other data partners
		involves agreeing on two things:
		- The &#34;dimensions&#34; used to stratify the summary
		  measures. For example, this could include
			cohort membership, or time.
		- The (decomposable) measures, such as counts,
		  that you are collecting. The specification
			of these measures can also serve as the basis
			for agreeing on strategy for data privacy with your
			data partners.
			For example, measures can be agreed on that exclude
			anomaly values.

		The QueryLibrary can be used to document and
		share these decisions as a computable specification
		using SQL like the following:
	
	
		 
	## Query
	```sql
	[10 32 32 32 32 83 69 76 69 67 84 10 10 9 9 9 47 47 32 49 46 32 65 103 114 101 101 32 111 110 32 100 105 109 101 110 115 105 111 110 115 32 119 105 116 104 32 121 111 117 114 32 100 97 116 97 32 112 97 114 116 110 101 114 115 46 10 9 9 9 103 101 110 100 101 114 44 10 9 9 9 97 99 101 116 97 109 105 110 111 112 104 101 110 95 100 111 115 97 103 101 95 109 111 110 116 104 44 10 10 9 9 9 47 47 32 50 46 32 65 103 114 101 101 32 111 110 32 109 101 97 115 117 114 101 115 46 10 9 9 9 47 47 32 32 32 32 70 111 114 32 101 120 97 109 112 108 101 44 32 115 104 97 114 101 32 116 104 101 32 100 105 115 116 114 105 98 117 116 105 111 110 32 111 102 10 9 9 9 47 47 32 32 32 32 111 102 32 112 101 114 115 111 110 32 97 103 101 115 32 97 99 114 111 115 115 32 116 104 101 32 99 104 111 115 101 110 32 100 105 109 101 110 115 105 111 110 115 46 10 9 9 9 109 105 110 40 97 103 101 41 32 65 83 32 109 105 110 95 97 103 101 44 10 9 9 9 47 47 32 84 104 101 115 101 32 109 101 97 115 117 114 101 115 32 109 97 121 32 98 101 32 99 111 110 115 116 114 97 105 110 101 100 32 102 111 114 32 112 114 105 118 97 99 121 10 9 9 9 47 47 32 114 101 97 115 111 110 115 46 10 9 9 9 67 65 83 69 32 87 72 69 78 32 109 97 120 40 97 103 101 41 32 60 32 56 48 32 84 72 69 78 32 109 97 120 40 97 103 101 41 32 69 76 83 69 32 56 48 32 97 115 32 109 97 120 95 97 103 101 10 9 9 9 47 47 32 89 111 117 114 32 115 117 109 109 97 114 121 32 109 97 121 32 105 110 99 108 117 100 101 32 109 101 97 115 117 114 101 115 10 9 9 9 47 47 32 102 114 111 109 32 116 104 101 32 113 117 101 114 121 32 108 105 98 114 97 114 121 44 32 111 114 32 121 111 117 32 99 97 110 10 9 9 9 47 47 32 99 114 101 97 116 101 32 121 111 117 114 32 111 119 110 46 10 9 9 9 115 117 109 40 97 99 101 116 97 109 105 110 111 112 104 101 110 95 100 111 115 97 103 101 41 32 65 83 32 115 117 109 95 97 99 101 116 97 109 105 110 111 112 104 101 110 95 100 111 115 97 103 101 10 9 9 9 47 47 32 78 111 116 101 58 32 119 104 105 108 101 32 34 99 111 117 110 116 34 32 105 115 32 100 101 99 111 109 112 111 115 97 98 108 101 10 9 9 9 47 47 32 34 100 105 115 116 105 110 99 116 32 99 111 117 110 116 34 32 105 115 32 110 111 116 46 10 9 9 9 99 111 117 110 116 40 97 99 101 116 97 109 105 110 111 112 104 101 110 95 100 111 115 97 103 101 46 112 101 114 115 111 110 95 105 100 41 32 65 83 32 97 99 101 116 97 109 105 110 111 112 104 101 110 95 112 101 114 115 111 110 95 99 111 117 110 116 10 10 32 32 32 32 47 47 32 84 104 101 32 114 101 115 116 32 105 115 32 83 81 76 32 98 111 105 108 101 114 112 108 97 116 101 46 10 9 9 70 82 79 77 32 112 101 114 115 111 110 10 9 9 9 76 69 70 84 32 74 79 73 78 32 97 99 101 116 97 109 105 110 111 112 104 101 110 95 100 111 115 97 103 101 32 85 83 73 78 71 32 112 101 114 115 111 110 95 105 100 10 9 9 9 76 69 70 84 32 74 79 73 78 32 97 103 101 32 85 83 73 78 71 32 112 101 114 115 111 110 95 105 100 10 9 9 9 76 69 70 84 32 74 79 73 78 32 103 101 110 100 101 114 32 85 83 73 78 71 32 103 101 110 100 101 114 95 99 111 110 99 101 112 116 95 105 100 10 10 9 9 71 82 79 85 80 32 66 89 10 9 9 9 103 101 110 100 101 114 44 10 9 9 9 97 99 101 116 97 109 105 110 111 112 104 101 110 95 100 111 115 97 103 101 95 109 111 110 116 104 10 32 32]
	```
	
		 
	
	
		 
	
	
		
	
	## Common Table Expression (CTE)
	
	
	- [acetaminophen_dosage](./acetaminophen_dosage.md) 
	
	
	
	- [age](./dialect/sqlite/age.md) 
	
	- [age](./dialect/sqlserver/measure/age.md) 
	
	
	
	- [gender](./gender.md) 
	
	
	
	
		
