# 32. Relational Database Schema

## Overview
Detailed relational schema with table definitions, columns, data types, and constraints.

## Core Tables

### projects
```sql
id (PK), name, client, status, start_date, end_date,
contract_value, budget_baseline, project_manager,
created_date, modified_date
```

### wbs_items
```sql
id (PK), project_id (FK), parent_id (FK), name, status,
assigned_to, budget, start_date, end_date, % complete
```

### materials
```sql
id (PK), name, specification, unit, unit_price,
supplier_id (FK), lead_time, status
```

### purchase_orders
```sql
id (PK), project_id (FK), vendor_id (FK), material_id (FK),
quantity, unit_price, total_amount, delivery_date,
payment_terms, status, created_date
```

### vendors
```sql
id (PK), name, address, contact_person, email, phone,
quality_rating, on_time_delivery %, status, created_date
```

### daily_progress
```sql
id (PK), project_id (FK), wbs_item_id (FK), work_date,
description, hours_worked, % complete, materials_used,
status, created_by, created_date
```

### inspections
```sql
id (PK), itp_id (FK), inspection_date, inspected_by,
status (pass/fail), findings, created_date
```

### invoices
```sql
id (PK), po_id (FK), vendor_id (FK), amount, invoice_date,
payment_date, status, created_date
```

### employees
```sql
id (PK), name, department, role, skills, email, phone,
active_flag, created_date
```

## Foreign Key Relationships
- wbs_items.project_id → projects.id
- materials.supplier_id → vendors.id
- purchase_orders.vendor_id → vendors.id
- daily_progress.wbs_item_id → wbs_items.id
- invoices.po_id → purchase_orders.id

## Indexes
- PRIMARY KEY on all id columns
- FOREIGN KEY indexes on all FK columns
- INDEX on project_id (frequently filtered)
- INDEX on status (frequently queried)
- INDEX on dates (range queries)

## Referential Integrity
- Delete project → cascade delete WBS, purchase orders, daily progress
- Delete vendor → prevent if has active POs
- Update statuses → trigger dependent updates

## Related Documents
[29_EPC_Domain_Model.md](29_EPC_Domain_Model.md) - Logical domain model
