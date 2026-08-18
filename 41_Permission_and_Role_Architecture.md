# 41. Permission and Role Architecture

## Overview
Role-based access control (RBAC) and permission architecture for EPC System.

## System Roles

| Role | Responsibilities | Key Permissions |
|------|-----------------|-----------------|
| **Administrator** | System admin, user mgmt | All permissions |
| **Executive** | Strategic oversight | Read project dashboards |
| **Project Manager** | Day-to-day project mgmt | Full project access |
| **Engineer** | Design work | Create/edit deliverables |
| **Procurement Manager** | Vendor & PO management | Requisitions, RFQs, POs |
| **Finance Manager** | Budget & cost control | Budget, cost, invoices |
| **Quality Manager** | Quality oversight | ITPs, inspections, NCRs |
| **HSE Officer** | Safety management | HSE incidents, audits |
| **Construction Manager** | Site execution | DPRs, crew assignments |
| **Site Supervisor** | Daily site work | Enter DPRs, material issues |
| **QC Inspector** | Quality inspections | Inspections, test results |
| **Warehouse Manager** | Material management | Receipts, issues, inventory |
| **HR Manager** | Resource management | Employee records, training |
| **Vendor** | External supplier | Limited PO/portal access |
| **Client** | Project owner | Read-only project visibility |

## Permission Levels

### Document-Level Permissions
- **Create:** Can create new documents
- **Read:** Can view documents (all fields unless field-level restricted)
- **Write/Edit:** Can modify documents
- **Submit:** Can mark documents as submitted/finalized
- **Delete:** Can delete documents
- **Amend:** Can amend submitted documents

### Field-Level Permissions
- **Read:** View field value
- **Write:** Edit field value
- **Set User Permission:** Can assign to other users

### Role Hierarchy
```
Administrator (All access)
├── Executive (Strategic view)
│   ├── Project Director
│   │   ├── Project Manager
│   │   │   ├── Engineering Manager
│   │   │   ├── Procurement Manager
│   │   │   ├── Construction Manager
│   │   │   └── Finance Manager
│   │
│   ├── Procurement Manager
│   │   └── Procurement Specialist
│   │
│   ├── Finance Director
│   │   └── Accountant
│   │
│   └── HSE Director
│       └── HSE Officer
```

## DocType Permissions Matrix

| DocType | Admin | PM | Eng | Proc | QA | Fin | HSE | Site |
|---------|-------|----|----|------|----|----|-----|------|
| Project | RWD | RWD | R | R | R | R | R | R |
| WBS Item | RWD | RWD | RW | R | - | R | - | - |
| Deliverable | RWD | R | RWD | - | R | - | - | - |
| PO | RWD | R | - | RWD | - | RW | - | - |
| DPR | RWD | RW | - | - | R | R | R | RWD |
| Inspection | RWD | R | - | - | RWD | - | - | RW |
| NCR | RWD | RW | RW | - | RWD | R | R | - |
| Invoice | RWD | R | - | R | - | RWD | - | - |

Legend: R=Read, W=Write, D=Delete, -=No access

## User Permission Assignments
- By Organization (Company)
- By Project (for project-specific access)
- By Department (for role-based access)
- By Cost Center (for finance-specific access)

## Segregation of Duties
- Cannot approve own document
- Cannot create and approve same transaction
- Finance approval required for >$10K expenses
- Change orders require multiple approvals

## Related Documents
[42_Workflow_and_State_Machine_Design.md](42_Workflow_and_State_Machine_Design.md) - Workflow with permissions
