# 29. EPC Domain Model

## Overview
Logical data model showing all entities and relationships in the EPC domain.

## Core Entities

### Projects
- Project ID, name, client, contract value
- Status (Planning, Active, Closed)
- Stakeholders, approvers

### Contracts
- Contract ID, parties, value, terms
- Payment milestones, penalties
- Warranty, liability, termination

### Work Breakdown Structure (WBS)
- WBS ID, description, parent/child relationships
- Assigned team, budget, schedule
- Cost center mapping

### Personnel
- Employee ID, name, skills, department
- Project assignments, utilization
- Training and certifications

### Engineering Deliverables
- Deliverable ID, type, status, version
- Owner, review cycle, approvals
- Client review status

### Materials
- Material ID, description, specification
- Quantity, unit, cost
- Supplier, lead time

### Vendors
- Vendor ID, company, contact info
- Qualifications, certifications
- Performance scorecard

### Purchase Orders
- PO ID, vendor, items, quantities
- Unit prices, total cost, delivery date
- Payment terms, status

### Inventory
- Material receipt/issue records
- Warehouse location, bin
- Serial numbers, batch numbers

### Quality Records
- Inspection plans (ITPs)
- Inspection reports
- Non-conformance reports (NCRs)

### Financial Records
- Cost actuals, commitments
- Invoices, payments
- GL accounts, expense codes

### HSE Records
- Incidents, near-misses
- Training records
- Audit findings

## Relationships
- Project contains WBS items
- WBS items have budget and schedule
- Engineering deliverables drive Materials
- Materials linked to POs
- POs linked to Vendors
- Vendors linked to Performance data
- All have related Quality and HSE records

## Related Documents
[30_ER_Diagram.md](30_ER_Diagram.md) - Entity relationship diagram
