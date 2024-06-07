<!---->

# Cost

## Description
The COST table captures records containing the cost of any medical event recorded in one of the OMOP clinical event tables such as DRUG_EXPOSURE, PROCEDURE_OCCURRENCE, VISIT_OCCURRENCE, VISIT_DETAIL, DEVICE_OCCURRENCE, OBSERVATION or MEASUREMENT.

Each record in the cost table account for the amount of money transacted for the clinical event. So, the COST table may be used to represent both receivables (charges) and payments (paid), each transaction type represented by its COST_CONCEPT_ID. The COST_TYPE_CONCEPT_ID field will use concepts in the Standardized Vocabularies to designate the source (provenance) of the cost data. A reference to the health plan information in the PAYER_PLAN_PERIOD table is stored in the record for information used for the adjudication system to determine the persons benefit for the clinical event.

### User Guidance
When dealing with summary costs, the cost of the goods or services the provider provides is often not known directly, but derived from the hospital charges multiplied by an average cost-to-charge ratio.

### Etl Conventions
One cost record is generated for each response by a payer. In a claims databases, the payment and payment terms reported by the payer for the goods or services billed will generate one cost record. If the source data has payment information for more than one payer (i.e. primary insurance and secondary insurance payment for one entity), then a cost record is created for each reporting payer. Therefore, it is possible for one procedure to have multiple cost records for each payer, but typically it contains one or no record per entity. Payer reimbursement cost records will be identified by using the PAYER_PLAN_ID field. Drug costs are composed of ingredient cost (the amount charged by the wholesale distributor or manufacturer), the dispensing fee (the amount charged by the pharmacy and the sales tax).

## Query
```sql
CREATE TABLE cost (
	cost_id integer NOT NULL,
	cost_event_id integer NOT NULL,
	cost_domain_id varchar(20) NOT NULL,
	cost_type_concept_id integer NOT NULL,
	currency_concept_id integer NOT NULL,
	total_charge float NOT NULL,
	total_cost float NOT NULL,
	total_paid float NOT NULL,
	paid_by_payer float NOT NULL,
	paid_by_patient float NOT NULL,
	paid_patient_copay float NOT NULL,
	paid_patient_coinsurance float NOT NULL,
	paid_patient_deductible float NOT NULL,
	paid_by_primary float NOT NULL,
	paid_ingredient_cost float NOT NULL,
	paid_dispensing_fee float NOT NULL,
	payer_plan_period_id integer NOT NULL,
	amount_allowed float NOT NULL,
	revenue_code_concept_id integer NOT NULL,
	revenue_code_source_value varchar(50) NOT NULL,
	drg_concept_id integer NOT NULL,
	drg_source_value varchar(3) NOT NULL
)
```

## Input


## Output


## Example output record


