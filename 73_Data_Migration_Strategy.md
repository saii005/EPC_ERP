# 73. Data Migration Strategy

## 1. Scope & Data Entities
Migrating legacy data from disparate spreadsheets, legacy ERP systems, and point solutions into the new Frappe/ERPNext EPC platform requires a phased approach:
* **Master Data:** Item masters, vendor lists, employee directories, cost centers, and warehouse definitions.
* **Open Transactions:** Active Purchase Orders, unapproved subcontracts, open Material Requisitions, and baseline WBS schedules.
* **Historical Data:** Closed project archives (for predictive AI/ML training models).

## 2. Migration Pipeline
1. **Extraction:** Exporting legacy data into standardized CSV/JSON formats.
2. **Transformation:** Mapping legacy fields to Frappe DocType schema using Python data cleaning scripts.
3. **Loading:** Utilizing Frappe's robust `data_import` tool and background batch insertion to maintain relational integrity.