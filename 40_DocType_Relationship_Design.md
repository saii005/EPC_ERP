# 40. DocType Relationship Design

## Overview
Relationships and linking between DocTypes showing how data is interconnected.

## Primary Relationships

### Project-Centric Relationships
```
Project (Master)
├── 1:N → WBS Items
│   ├── 1:N → Daily Progress Reports
│   ├── 1:N → Inspections
│   ├── 1:N → NCR
│   └── 1:N → Budget Items
│
├── 1:N → Purchase Requisitions
│   └── 1:N → Purchase Orders
│       ├── N:N → Materials (via PO Items)
│       └── 1:N → Invoices
│
├── 1:N → Engineering Deliverables
│   └── 1:N → Review Records
│
├── 1:N → Contracts
│   └── 1:N → Change Orders
│
└── 1:1 → Budget Baseline
    └── 1:N → Cost Actuals
```

### Material Flow Relationships
```
Engineering Deliverable (BOM)
├── N:N → Materials
│   └── 1:N → Requisitions
│       └── 1:N → Purchase Orders
│           └── 1:N → Material Receipts
│               └── 1:1 → Warehouse Location
│                   └── 1:N → Issue-to-Site
│                       └── 1:1 → Installation Location
```

### Quality Flow Relationships
```
Inspection & Test Plan
├── 1:N → Inspection Records
│   ├── Pass → Material Certificate
│   └── Fail → Non-Conformance Report (NCR)
│       ├── 1:N → Corrective Actions
│       └── Verification → Issue Closure
```

### Vendor Relationships
```
Vendor (Master)
├── 1:N → Vendor Qualifications
├── 1:N → Purchase Orders
├── 1:N → Invoices
├── 1:N → Scorecards (Monthly/Quarterly)
├── 1:N → Audit Records
└── 1:N → Certifications
```

### Financial Relationships
```
Purchase Order
├── 1:N → Invoice
│   ├── 1:1 → GL Entry (Expense Posting)
│   └── 1:N → Payment Records
│
├── 1:1 → Budget Item
│   └── 1:N → Cost Actuals
│
└── 1:N → Warranty Records
```

## Cardinality Legends
- **1:1** - One-to-one (unique relationship)
- **1:N** - One-to-many (one parent, many children)
- **N:N** - Many-to-many (junction table required)

## Referential Integrity Rules
- **Cascade Delete:** Project delete → cascade to WBS, POs, Deliverables
- **Prevent Delete:** Vendor delete prevented if has active POs
- **Update Cascade:** Project status update → cascade to dependent items
- **Null Handling:** Optional relationships set to NULL on parent delete

## Relationship Queries
Common queries:
- Find all materials in a BOM → link via Engineering Deliverable
- Find all POs for a material → link via Material Master
- Find all inspections for an activity → link via WBS Item
- Find all costs for a project → link via WBS Item or Project

## Related Documents
[32_Relational_DB_Schema.md](32_Relational_DB_Schema.md) - Physical schema implementation
