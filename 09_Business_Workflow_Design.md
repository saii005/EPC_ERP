# 09. Business Workflow Design

## 📋 Overview

This document defines the workflow state machines and business process automations for the EPC ERP System. It describes how documents, requests, and approvals flow through the system.

---

## 1. Document Approval Workflow

### 1.1 Engineering Deliverable Approval Workflow

```
State Diagram: Engineering Deliverable Review Cycle

┌─────────────┐
│    DRAFT    │
│ Deliverable │
│   Created   │
└──────┬──────┘
       │
       │ Submitted for IFR (In For Review)
       ▼
┌─────────────────────────────────────┐
│     IFR - In For Review             │
│  • Lead Engineer Reviews            │
│  • Adds Comments/Questions          │
│  • Timeline: 5 working days         │
└──────┬────────────────────────────────┘
       │
    ┌──┴──────────────────────────┐
    │                             │
    │ Changes Required            │ Approved
    │                             │
    ▼                             ▼
┌──────────────┐           ┌──────────────────┐
│ Returned to  │           │ IFA - In For     │
│ Draft for    │           │ Approval         │
│ Revisions    │           │                  │
└──────┬───────┘           │ • Client reviews │
       │                   │ • Final approval │
       │                   └────────┬─────────┘
       │                           │
       │                       ┌───┴───────┐
       │                       │           │
       │                  Client Comments │ Approved
       │                       │           │
       │                       ▼           ▼
       │                   ┌─────────┐   ┌─────────────┐
       │                   │  Return │   │  IFC - In   │
       │                   │  to Draft   │ For Constr. │
       │                   └────┬────┘   │             │
       │                        │        │ Approved by │
       └────────────────────────┘        │ Engineering │
                                         └─────┬───────┘
                                               │
                                               ▼
                                         ┌─────────────┐
                                         │  APPROVED   │
                                         │ & RELEASED  │
                                         │ for Use     │
                                         └─────────────┘
```

### 1.2 Purchase Order Approval Workflow

```
State Diagram: PO Approval & Issuance

┌──────────────┐
│ Requisition  │
│   Created    │
└──────┬───────┘
       │
       │ Process
       ▼
┌──────────────────────────────┐
│  PO Created from Bid         │
│  • Link to PO               │
│  • Terms Added              │
│  • Payment Conditions Set   │
└──────┬───────────────────────┘
       │
       │ Route for Approval
       ▼
┌──────────────────────────────┐
│  Approval Required?          │
│  (Based on Amount)           │
└──────┬───────────────────────┘
       │
    ┌──┴───────────────┐
    │                  │
    ▼                  ▼
  <$10K            >$10K
    │                  │
    │ Approved by      │ Approved by
    │ Procurement      │ Procurement +
    │ Manager          │ Finance Manager
    │                  │
    ▼                  ▼
┌──────────────────────────────┐
│  PO ISSUED to Vendor         │
│  • Via Email/EDI             │
│  • Vendor Acknowledges       │
│  • Status: Acknowledged      │
└──────┬───────────────────────┘
       │
       │ PO Execution
       ▼
┌──────────────────────────────┐
│  IN EXECUTION                │
│  • Tracking Delivery         │
│  • Monitoring Progress       │
└──────┬───────────────────────┘
       │
       │ Goods/Services Delivered
       ▼
┌──────────────────────────────┐
│  RECEIVED & INSPECTED        │
│  • QC Inspection Complete    │
│  • Quality Approved          │
└──────┬───────────────────────┘
       │
       │ Invoice Received
       ▼
┌──────────────────────────────┐
│  3-WAY MATCH                 │
│  • PO Match ✓               │
│  • Receipt Match ✓           │
│  • Invoice Match ✓           │
└──────┬───────────────────────┘
       │
       │ All Match
       ▼
┌──────────────────────────────┐
│  APPROVED FOR PAYMENT        │
│  • Ready to Pay              │
│  • Payment Scheduled         │
└──────┬───────────────────────┘
       │
       │ Payment Made
       ▼
┌──────────────────────────────┐
│  PAID & CLOSED               │
│  • PO Archive                │
│  • Records Maintained        │
└──────────────────────────────┘
```

---

## 2. Change Management Workflow

### 2.1 Engineering Change Order (ECO) Workflow

```
State Diagram: Engineering Change Order

┌──────────────────┐
│  CHANGE REQUEST  │
│  • Initiated by  │
│    Project/Engr  │
└────────┬─────────┘
         │
         │ Register & Analyze
         ▼
┌──────────────────────────────────┐
│  ECO ANALYSIS                    │
│  • Impact on Scope               │
│  • Technical Feasibility         │
│  • Impact on Schedule            │
│  • Impact on Cost                │
│  • Responsible: Engineering      │
└────────┬──────────────────────────┘
         │
         │ Analysis Complete
         ▼
┌──────────────────────────────────┐
│  IMPACT ASSESSMENT               │
│  • Timeline Impact: X weeks      │
│  • Cost Impact: $X               │
│  • Quality Impact: None/Minor/Maj
└────────┬──────────────────────────┘
         │
         │ Route for Approval
         ▼
┌──────────────────────────────────┐
│  APPROVALS REQUIRED              │
│  • Engineering Manager: +        │
│  • Project Manager: +            │
│  • Finance (if $): +             │
│  • Client (if contractual): +    │
└────────┬──────────────────────────┘
         │
      ┌──┴──────────────────┐
      │                     │
   APPROVED             REJECTED
      │                     │
      ▼                     ▼
  ┌────────┐            ┌────────┐
  │APPROVED│            │REJECTED│
  │        │            │Close   │
  └───┬────┘            └────────┘
      │
      │ Update Design Documents
      │ Update Schedule/Budget
      ▼
  ┌────────────────────────────────┐
  │IMPLEMENTED & CLOSED            │
  │Document Status: Closed         │
  │Archive Change Record           │
  └────────────────────────────────┘
```

---

## 3. Approval Workflow Patterns

### 3.1 Single-Level Approval
Used for routine requisitions, small change orders, standard documents

```
Creator → Approver → Status: Approved/Rejected
```

### 3.2 Multi-Level Approval
Used for large contracts, major change orders, budget changes

```
Creator → L1 Approver → L2 Approver → L3 Approver → Approved
```

### 3.3 Conditional Approval
Used when approval routing depends on amount or content

```
Amount < $10K:  Creator → Manager → Approved
Amount > $10K:  Creator → Manager → Director → Finance → Approved
```

### 3.4 Parallel Approval
Used when multiple independent approvals required

```
Creator → ├─ Approver 1
         ├─ Approver 2
         └─ Approver 3 → All Approved → Completed
```

---

## 4. Inspection & Quality Workflow

### 4.1 Inspection & Test Plan (ITP) Execution

```
State Diagram: ITP Execution & Hold Points

┌──────────────────────────┐
│  ITP Created             │
│  • Based on Spec         │
│  • Hold Points Defined   │
└────────┬─────────────────┘
         │
         │ Activity Begins
         ▼
┌──────────────────────────┐
│  WORK IN PROGRESS        │
│  • Crew executing work   │
│  • Materials consumed    │
└────────┬─────────────────┘
         │
         │ Activity reaches hold point
         ▼
┌──────────────────────────┐
│  HOLD - INSPECTION       │
│  Notify Inspector        │
└────────┬─────────────────┘
         │
         │ Inspector arrives
         ▼
┌──────────────────────────┐
│  INSPECTION ONGOING      │
│  • Checklist execution   │
│  • Measurements          │
│  • Photo documentation   │
└────────┬─────────────────┘
         │
      ┌──┴──────────────────┐
      │                     │
    PASS              FAIL/DEFECT
      │                     │
      ▼                     ▼
  ┌────────┐            ┌──────────┐
  │APPROVED│            │Create NCR│
  │ Activity│           │Investigate
  │ Proceeds │           │Root Cause
  └────────┘            │Corrective
                        │Actions
                        └──────┬───┘
                               │
                         ┌─────▼─────┐
                         │  RE-INSPECT│
                         │  Fix OK?   │
                         └─────┬─────┘
                               │
                         If OK, go to
                         APPROVED
```

---

## 5. Incident Management Workflow

### 5.1 HSE Incident Reporting & Investigation

```
State Diagram: Incident Management

┌──────────────┐
│  INCIDENT    │
│  OCCURS      │
└────────┬─────┘
         │
         │ Immediate Actions Taken
         ▼
┌──────────────────────────┐
│  REPORTED                │
│  • Description logged    │
│  • Severity classified   │
│  • Immediate containment │
└────────┬─────────────────┘
         │
         │ Safety Officer reviews
         ▼
┌──────────────────────────┐
│  UNDER INVESTIGATION     │
│  • Root cause analysis   │
│  • Evidence collected    │
│  • Timeline documented   │
└────────┬─────────────────┘
         │
         │ Investigation complete
         ▼
┌──────────────────────────┐
│  FINDINGS & ACTIONS      │
│  • Root causes identified
│  • Corrective actions    │
│  • Preventive measures   │
└────────┬─────────────────┘
         │
         │ Assign to responsible party
         ▼
┌──────────────────────────┐
│  ACTIONS IN PROGRESS     │
│  • Corrective actions    │
│  • Timeline: X days      │
│  • Status tracking       │
└────────┬─────────────────┘
         │
         │ Actions completed
         ▼
┌──────────────────────────┐
│  VERIFIED & CLOSED       │
│  • Follow-up inspection  │
│  • Effectiveness checked │
│  • Incident closed       │
└──────────────────────────┘
```

---

## 6. Material Receipt Workflow

### 6.1 Material Receiving & Inspection

```
State Diagram: Material Receipt Process

┌────────────────────────┐
│  SHIPMENT RECEIVED     │
│  at Warehouse          │
└────────┬───────────────┘
         │
         │ Log Receipt
         ▼
┌────────────────────────┐
│  INSPECTION PENDING    │
│  • Quantity check      │
│  • Condition check     │
│  • Documentation check │
└────────┬───────────────┘
         │
         │ Inspection performed
         ▼
┌────────────────────────┐
│  INSPECTION RESULT?    │
└────────┬───────────────┘
         │
    ┌────┴──────────────┐
    │                   │
  PASS              FAIL/DAMAGE
    │                   │
    ▼                   ▼
┌────────────┐      ┌──────────────┐
│ ACCEPTED   │      │ QUARANTINE   │
│            │      │ On Hold      │
│ Entry to   │      │              │
│Warehouse   │      │ Notify Vendor│
└────┬───────┘      │ Claim Process
     │              └──────┬───────┘
     │                     │
     ▼                     ▼
┌─────────────────────────────────┐
│ ASSIGNED TO LOCATION            │
│ Bin/Shelf/Pallet Assignment     │
│ Serial Numbers Recorded (if req) │
└────────┬────────────────────────┘
         │
         │ Track in Inventory
         ▼
┌─────────────────────────────────┐
│ AVAILABLE FOR ISSUE TO SITE     │
│ Awaiting Site Request           │
└─────────────────────────────────┘
```

---

## 7. Invoice & Payment Workflow

### 7.1 Invoice Processing & Payment

```
State Diagram: Invoice Processing

┌──────────────────┐
│  INVOICE         │
│  RECEIVED        │
│  from Vendor     │
└────────┬─────────┘
         │
         │ Log & Register
         ▼
┌──────────────────────────────┐
│  3-WAY MATCH VERIFICATION    │
│  • Compare to PO             │
│  • Compare to Receipt        │
│  • Verify Amount             │
└────────┬─────────────────────┘
         │
      ┌──┴──────────────────┐
      │                     │
    MATCH            MISMATCH
      │                     │
      ▼                     ▼
  ┌────────┐            ┌──────────┐
  │APPROVED│            │ DISPUTED │
  │ for    │            │          │
  │ Payment│            │ Query    │
  └───┬────┘            │ Vendor   │
      │                 └────┬─────┘
      │                      │
      │                 ┌────┴─────┐
      │                 │ Resolved? │
      │                 └────┬─────┘
      │                      │
      │                   If Yes
      │                      │
      │                      ▼
      │                  Go to Approved
      │
      │ Payment Scheduled
      ▼
┌──────────────────────────────┐
│  PAYMENT IN PROCESS          │
│  • Amount & Date Confirmed   │
│  • GL Posting                │
│  • Bank Transfer Initiated   │
└────────┬─────────────────────┘
         │
         │ Payment Cleared
         ▼
┌──────────────────────────────┐
│  PAID & CLOSED               │
│  • Payment recorded          │
│  • Invoice archived          │
│  • Records filed             │
└──────────────────────────────┘
```

---

## 8. Automation & Notifications

### 8.1 Automated Workflow Triggers

| Trigger | Action | Recipient |
|---------|--------|-----------|
| PO Created | Notification of PO issuance | Vendor |
| Delivery Due | Reminder of expected delivery | Vendor Mgr |
| Invoice received | 3-way match validation | Finance |
| NCR Created | Notify QA Manager | QA Manager |
| ITP Hold Point | Notify Inspector | QC Inspector |
| Change Order | Route for approval | Approvers |
| Payment Due | Reminder to process payment | Finance |
| Document Expires | Certification renewal notification | Owner |

---

## 📚 Next Steps

1. Review [10_Approval_Workflow_Design.md](10_Approval_Workflow_Design.md) for detailed approval rules
2. Check [42_Workflow_and_State_Machine_Design.md](42_Workflow_and_State_Machine_Design.md) for technical implementation
3. See [46_Form_Design.md](46_Form_Design.md) for workflow UI

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Business Analysts, Process Architects
