<!--

-->

# Cost










 

## Description
The COST table captures records containing the cost of any medical event recorded in one of the OMOP clinical event tables such as DRUG_EXPOSURE, PROCEDURE_OCCURRENCE, VISIT_OCCURRENCE, VISIT_DETAIL, DEVICE_OCCURRENCE, OBSERVATION or MEASUREMENT.

Each record in the cost table account for the amount of money transacted for the clinical event. So, the COST table may be used to represent both receivables (charges) and payments (paid), each transaction type represented by its COST_CONCEPT_ID. The COST_TYPE_CONCEPT_ID field will use concepts in the Standardized Vocabularies to designate the source (provenance) of the cost data. A reference to the health plan information in the PAYER_PLAN_PERIOD table is stored in the record for information used for the adjudication system to determine the persons benefit for the clinical event.
### User Guidance
When dealing with summary costs, the cost of the goods or services the provider provides is often not known directly, but derived from the hospital charges multiplied by an average cost-to-charge ratio.



 
## Query
```sql
CD
```








 

## Input




 

## Output



 

## Example output record





