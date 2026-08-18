# 30. ER Diagram

## Overview
Entity Relationship Diagram showing database schema relationships.

## Diagram Legend
```
┌─────────────────────────────────────────────────────────┐
│                     PROJECTS                             │
│  ┌────────────────┐                                      │
│  │  Project ID    │  1:N                                 │
│  │  Name          │   ├─→ WBS ITEMS                      │
│  │  Client        │   ├─→ BUDGETS                        │
│  │  Value         │   ├─→ CONTRACTS                      │
│  │  Status        │   ├─→ RESOURCES                      │
│  └────────────────┘   └─→ REQUISITIONS                   │
│         ↓                                                 │
│    WBS ITEMS  ↔  BUDGETS       M:N ┌──────────────┐     │
│         ↓                           │ MATERIALS    │     │
│    ┌─────────────────────┐          │ ┌──────────┐ │     │
│    │ Activity ID         │          │ │Material  │ │     │
│    │ Parent WBS          │          │ │Cost      │ │     │
│    │ Description         │          │ │Qty       │ │     │
│    │ Assigned Team       │          │ └──────────┘ │     │
│    │ Schedule            │          └──────────────┘     │
│    │ Budget              │                  ↓            │
│    └─────────────────────┘         ┌──────────────┐     │
│           ↓                        │ PURCHASE     │     │
│    ┌─────────────────────┐         │ ORDERS       │     │
│    │ DAILY PROGRESS      │         │ ┌──────────┐ │     │
│    │ REPORTS             │         │ │PO ID     │ │     │
│    │ Work completed      │         │ │Vendor    │ │     │
│    │ Hours worked        │         │ │Amount    │ │     │
│    │ Materials used      │         │ │Status    │ │     │
│    └─────────────────────┘         │ └──────────┘ │     │
│           ↓                        └──────────────┘     │
│    ┌─────────────────────┐                ↓            │
│    │ INSPECTIONS         │         ┌──────────────┐     │
│    │ & TESTS (ITP)       │         │ VENDORS      │     │
│    │ Hold points         │         │ ┌──────────┐ │     │
│    │ Pass/Fail           │         │ │Vendor ID │ │     │
│    │ Certs               │         │ │Quality   │ │     │
│    └─────────────────────┘         │ │Performance
│           ↓                        │ └──────────┘ │     │
│    ┌─────────────────────┐         └──────────────┘     │
│    │ INVOICES &          │                             │
│    │ PAYMENTS            │         ┌──────────────┐     │
│    │ Invoice Amount      │         │ HSE RECORDS  │     │
│    │ Payment Status      │         │ Incidents    │     │
│    │ GL Posting          │         │ Training     │     │
│    └─────────────────────┘         └──────────────┘     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

## Key Entities & Attributes
(See [29_EPC_Domain_Model.md](29_EPC_Domain_Model.md) for detailed attributes)

## Cardinality
- 1:N = One project has many WBS items
- M:N = Many materials in many BOMs
- 1:1 = One project has one budget baseline

## Related Documents
[31_DB_Design.md](31_DB_Design.md) - Database physical design
