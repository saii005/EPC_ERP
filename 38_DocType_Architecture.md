# 38. DocType Architecture

## Overview
DocType (data type) architecture defining how data models are structured and organized.

## DocType Categories

### Master Data DocTypes
- **Project:** Master project record
- **Vendor:** Vendor master data
- **Material:** Material master data
- **Employee:** Employee master data
- **Department:** Organizational structure

### Transactional DocTypes
- **Purchase Order:** Vendor transaction
- **Material Receipt:** Warehouse receipt
- **Daily Progress Report:** Construction progress
- **Invoice:** Financial transaction

### Setup DocTypes
- **Company:** Multi-company configuration
- **Warehouse:** Warehouse setup
- **Cost Center:** Financial cost tracking
- **Department:** Organizational structure

### List DocTypes
- **Engineering Deliverable List:** Collection of deliverables
- **Inspection List:** Collection of inspections
- **NCR List:** Quality issues register

## DocType Structure
```
DocType: Purchase Order
├── Fields:
│   ├── name (DocType)
│   ├── po_number (String, required)
│   ├── vendor (Link to Vendor)
│   ├── po_date (Date)
│   ├── delivery_date (Date)
│   ├── total_amount (Currency)
│   ├── payment_terms (Select)
│   ├── status (Select)
│   └── items (Table) → PO Item rows
│       ├── material (Link to Material)
│       ├── quantity (Float)
│       ├── unit_price (Currency)
│       ├── line_total (Currency)
│
├── Validations:
│   ├── Check total_amount > 0
│   ├── Check delivery_date > po_date
│   ├── Validate vendor is approved
│
├── Methods:
│   ├── on_submit() - Set status to "Issued"
│   ├── on_cancel() - Notify vendor of cancellation
│   ├── validate() - Check all validations
│
├── Permissions:
│   ├── Create: Procurement Manager
│   ├── Read: Procurement Team
│   ├── Write: Procurement Manager only
│   ├── Submit: Finance Manager
│
└── Workflow:
    Draft → Submitted → Acknowledged → In Transit → Received → Closed
```

## DocType Relationships
- **Link:** References to other DocTypes (n:1)
- **Table:** Child rows (1:n)
- **Many-to-Many:** Create through junction tables

## DocType Properties
- **Naming:** Auto-generated or custom series
- **Status:** Define possible statuses
- **Permissions:** Role-based access control
- **Workflows:** Approval workflows
- **Validations:** Data validation rules
- **Methods:** Custom Python logic

## Performance Considerations
- Index frequently queried fields
- Limit table row size for large transactions
- Archive old data periodically
- Optimize queries for reports

## Related Documents
[39_DocType_Field_Specification.md](39_DocType_Field_Specification.md) - Field specifications
