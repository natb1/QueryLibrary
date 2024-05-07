<!--

-->

# Visit Detail










 

## Description
The VISIT_DETAIL table is an optional table used to represents details of each record in the parent VISIT_OCCURRENCE table. A good example of this would be the movement between units in a hospital during an inpatient stay or claim lines associated with a one insurance claim. For every record in the VISIT_OCCURRENCE table there may be 0 or more records in the VISIT_DETAIL table with a 1:n relationship where n may be 0. The VISIT_DETAIL table is structurally very similar to VISIT_OCCURRENCE table and belongs to the visit domain.
### User Guidance
The configuration defining the Visit Detail is described by Concepts in the Visit Domain, which form a hierarchical structure. The Visit Detail record will have an associated to the Visit Occurrence record in two ways: <br> 1. The Visit Detail record will have the VISIT_OCCURRENCE_ID it is associated to 2. The VISIT_DETAIL_CONCEPT_ID  will be a descendant of the VISIT_CONCEPT_ID for the Visit.



 
## Query
```sql
CD
```








 

## Input




 

## Output



 

## Example output record





