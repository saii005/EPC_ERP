# 42. Workflow and State Machine Design

## Overview
State machines and workflow definitions for all key business processes.

## Project Workflow
```
State Machine: Project Status
┌──────────────────────┐
│      CREATED         │ (Initial state)
└──────────┬───────────┘
           │ Approve by Director
           ▼
┌──────────────────────┐
│      ACTIVE          │ (Execution state)
└──────────┬───────────┘
           │
    ┌──────┴──────────┐
    │                 │
    ▼                 ▼
┌────────────┐   ┌──────────┐
│  ON TRACK  │   │ AT RISK  │ (Status during active)
└────────────┘   └──────────┘
    │                 │
    └──────┬──────────┘
           │ Project complete
           ▼
┌──────────────────────┐
│      CLOSED          │ (Final state)
└──────────────────────┘
```

## Purchase Order Workflow
```
Draft → (Submit) → Issued → Acknowledged → In Transit → Received → Closed
  ↓                           ↑
  └─ (Reject) → (Re-open) ────┘
  
Approval workflow:
• <$10K: Procurement Mgr approval
• >$10K: +Finance Mgr approval
```

## Engineering Deliverable Workflow
```
Draft
  ↓ (Submit for IFR)
IFR (In For Review)
  ├─ Engineering review
  └─ (Approved) → IFA (In For Approval)
                  ├─ Client review
                  └─ (Approved) → IFC (In For Construction)
                                  └─ Released for use

Alternative paths:
IFR → (Return to Draft) → IFR (revisions needed)
IFA → (Return to Draft) → IFR (client changes)
```

## NCR Workflow
```
Open
  ├─ Investigation
  ├─ Root cause analysis
  └─ Corrective action assignment
  
In Progress
  ├─ Corrective action execution
  └─ Verification of fix
  
Closed
  └─ Verified and accepted
```

## Approval Workflow Pattern
```
State: PENDING_APPROVAL
├─ Route to Approver(s)
├─ Send notification email
├─ Approver reviews document
└─ Approver decision:
   ├─ APPROVE → State: APPROVED
   ├─ REJECT → State: REJECTED + Return to DRAFT
   └─ REQUEST_INFO → Requester provides info, back to PENDING

Transitions:
DRAFT → (Submit) → PENDING_APPROVAL → (Approve) → APPROVED
         ↓          ↓
         ├─ REJECTED ← (Reject)
         └──────────────────────────
```

## Workflow Automation Rules

### Automatic Transitions
- PO status changes when delivery confirmed
- Material receipt automatically updated when goods arrive
- Invoice automatically matches when PO + receipt + invoice align

### Automatic Notifications
- Approver notified when approval needed
- Vendor notified when PO issued
- Finance notified when invoice ready for payment
- Project Manager notified when NCR created

### Calculated Fields
- Total amount = Sum of line items
- % Complete = Average of WBS items
- Schedule Variance = Planned - Actual dates
- Cost Variance = Budget - Actual

## Workflow Configuration
- Defined using Frappe Workflow DocType
- Transitions based on user role or conditions
- Conditional transitions (if amount >$10K then require Finance approval)
- Parallel approvals supported
- Approval chain defined in workflow

## Related Documents
[09_Business_Workflow_Design.md](09_Business_Workflow_Design.md) - Business process workflows
[10_Approval_Workflow_Design.md](10_Approval_Workflow_Design.md) - Approval rules
