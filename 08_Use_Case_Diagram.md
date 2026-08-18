# 08. Use Case Diagram

## 📋 Overview

This document provides visual representations of use cases and actors in the EPC ERP System using UML Use Case Diagrams.

---

## 1. System Boundary & Main Actors

```
┌─────────────────────────────────────── EPC ERP SYSTEM ───────────────────────────────────┐
│                                                                                           │
│  EXECUTIVE        PROJECT MGMT        ENGINEERING         PROCUREMENT        FIELD       │
│  ┌────────────┐   ┌────────────┐     ┌────────────┐      ┌────────────┐     ┌────────┐ │
│  │ Executive  │   │   Project  │     │  Engineer  │      │Procurement│     │  Site  │ │
│  │ Dashboard  │   │  Manager   │     │  Manager   │      │  Manager   │     │Supervisor
│  └─────┬──────┘   └─────┬──────┘     └─────┬──────┘      └─────┬──────┘     └───┬────┘ │
│        │                │                   │                   │                 │      │
│        │         ┌──────┴────────┐          │         ┌─────────┴─────────┐      │      │
│        │         │               │          │         │                  │      │      │
│  ┌─────▼────────────────────────────────────▼──────────▼──────────────────▼──────▼──┐  │
│  │                                                                                   │  │
│  │  • View Executive Dashboards           • Create Engineering Deliverables        │  │
│  │  • Review Portfolio Status             • Execute Review Workflows               │  │
│  │                                        • Create Bill of Materials                │  │
│  │  • Create New Project                  • Manage Design Changes                  │  │
│  │  • Establish Project Budget                                                     │  │
│  │  • Manage Project Scope                • Create RFQs                            │  │
│  │  • Track Project Status                • Evaluate Bids                          │  │
│  │  • Manage Resources                    • Create Purchase Orders                 │  │
│  │                                        • Track Vendor Performance                │  │
│  │                                                                                   │  │
│  │                                                                  • Create DPRs    │  │
│  │                                                                  • Manage PTW      │  │
│  │                                         • Receive Materials      • Record HSE     │  │
│  │                                         • Issue to Site           • Update Status │  │
│  │                                         • Track Inventory                        │  │
│  │                                                                                   │  │
│  └───────────────────────────────────────────────────────────────────────────────────┘  │
│                                                                                           │
└───────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Project Lifecycle Use Cases

```
                         ┌─────────────────────────────────────────────┐
                         │      EPC ERP SYSTEM - PROJECT LIFECYCLE    │
                         └─────────────────────────────────────────────┘

    ┌──────────────┐         ┌──────────────┐         ┌──────────────┐
    │  Initiation  │────────▶│  Engineering │────────▶│Procurement & │
    │  Phase       │         │  & Design    │         │ Logistics    │
    └──────────────┘         └──────────────┘         └──────────────┘
           │                        │                        │
           │                        │                        │
      UC-001: Create              UC-003:                UC-006:
      New Project               Create Deliverable      Create RFQ
           │                        │                        │
      UC-002:                   UC-004:                UC-007:
      Establish Budget          Execute Review         Evaluate Bids
           │                        │                        │
                                UC-005:                UC-008:
                              Create BOM             Track Vendor
                                                    Performance

           │                        │                        │
           └────────────────────────┴────────────────────────┘
                          │
                          ▼
           ┌──────────────────────────────────────┐
           │    Construction Phase                │
           │  ┌────────────┐  ┌───────────────┐  │
           │  │  Materials │  │  Field Work   │  │
           │  └────────────┘  └───────────────┘  │
           │        │                  │         │
           │    UC-009:           UC-011:        │
           │    Receive Material  Create DPR     │
           │        │                  │         │
           │    UC-010:           UC-012:        │
           │    Issue to Site     Manage PTW     │
           │                                     │
           │  ┌────────────┐  ┌───────────────┐  │
           │  │  Quality   │  │  HSE/Incidents
           │  └────────────┘  └───────────────┘  │
           │        │                  │         │
           │    UC-013:           UC-015:        │
           │    Conduct Inspect   Report Incident
           │        │                  │         │
           │    UC-014:                          │
           │    Manage NCR                       │
           │                                     │
           └──────────────────────────────────────┘
                          │
                          ▼
           ┌──────────────────────────────────────┐
           │  Closeout Phase                      │
           │                                      │
           │  UC-016: Track Project Costs         │
           │  UC-017: Generate Project Invoice    │
           │  UC-018: Distribute Documents        │
           │  UC-019: Generate Status Report      │
           │                                      │
           └──────────────────────────────────────┘
```

---

## 3. Procurement Process Use Cases

```
                    ┌─────────────────────────────┐
                    │   PROCUREMENT PROCESS       │
                    │     USE CASES               │
                    └─────────────────────────────┘

        ┌──────────────────────────┐
        │   Procurement Manager    │
        │   (Approver)             │
        └──────┬───────────────────┘
               │
               │ approves
               ▼
        ┌──────────────────────────┐
        │ Create Requisition       │◀────── From Engineering BOM
        │ (UC-046)                 │        From Stock Request
        │                          │        From Site Request
        └──────┬───────────────────┘
               │
               │ reviews
               ▼
        ┌──────────────────────────┐
        │ Create & Issue RFQ       │
        │ (UC-006)                 │
        │ to Vendors               │
        └──────┬───────────────────┘
               │
               │ collect quotations
               ▼
        ┌──────────────────────────┐
        │ Evaluate Bids            │
        │ (UC-007)                 │
        │ & Create PO              │
        └──────┬───────────────────┘
               │
               │ track
               ▼
        ┌──────────────────────────┐
        │ Track Vendor Performance │
        │ (UC-008)                 │
        │ & Scorecards             │
        └──────────────────────────┘
```

---

## 4. Materials & Warehouse Flow

```
                    ┌─────────────────────────────┐
                    │  MATERIALS & WAREHOUSE      │
                    │     USE CASES               │
                    └─────────────────────────────┘

        Supplier
            │
            │ ships
            ▼
        ┌──────────────────────────┐
        │ Receive Material         │
        │ (UC-009)                 │
        │ into Warehouse           │
        └──────┬───────────────────┘
               │
               │ stored, tracked
               ▼
        ┌──────────────────────────┐
        │ Warehouse Inventory      │
        │ Management               │
        └──────┬───────────────────┘
               │
               │ site request
               ▼
        ┌──────────────────────────┐
        │ Issue Material to Site   │
        │ (UC-010)                 │
        │ Custodian Transfer       │
        └──────┬───────────────────┘
               │
               │ used
               ▼
        ┌──────────────────────────┐
        │ Construction Activity    │
        │ Material Consumption     │
        └──────────────────────────┘
```

---

## 5. Construction & Field Execution

```
                    ┌─────────────────────────────┐
                    │   CONSTRUCTION EXECUTION    │
                    │     USE CASES               │
                    └─────────────────────────────┘

        ┌────────────────────────────────────────────┐
        │         Site Activities Proceed            │
        └────────────┬────────────────────────────────┘
                     │
        ┌────────────┴────────────────────┬──────────┐
        │                                 │          │
        ▼                                 ▼          ▼
    ┌─────────────┐              ┌─────────────┐  ┌────────────┐
    │Create Daily │              │  Conduct    │  │  Manage    │
    │ Progress    │◀─────────────▶│Inspections  │  │ Permits to │
    │Report (DPR) │              │ per ITP     │  │ Work (PTW) │
    │(UC-011)     │              │(UC-013)     │  │(UC-012)    │
    └─────────────┘              └──────┬──────┘  └────────────┘
        │                               │
        │ updates                       │ finds defect
        │ project status                │
        │                               ▼
        │                         ┌──────────────┐
        │                         │  Create NCR  │
        │                         │  (UC-014)    │
        │                         │  Manage      │
        │                         │  Corrective  │
        │                         │  Actions     │
        │                         └──────────────┘
        │
        └─────────────┬────────────┘
                      │
        ┌─────────────▼────────────┐
        │  HSE Monitoring          │
        │  • Report Incidents      │
        │    (UC-015)              │
        │  • Near-Miss Reporting   │
        │  • Safety Audits         │
        └──────────────────────────┘
```

---

## 6. Quality Management Flow

```
                    ┌─────────────────────────────┐
                    │   QUALITY MANAGEMENT        │
                    │     USE CASES               │
                    └─────────────────────────────┘

        ┌──────────────────────────┐
        │ Create Inspection &      │
        │ Test Plan (ITP)          │
        │ based on Specs           │
        └──────┬───────────────────┘
               │
               │ defines hold points
               ▼
        ┌──────────────────────────┐
        │ Conduct Inspection       │
        │ per ITP                  │
        │ (UC-013)                 │
        └──────┬───────────────────┘
               │
        ┌──────┴──────────┐
        │                 │
        ▼                 ▼
    ┌────────┐        ┌────────┐
    │  PASS  │        │  FAIL  │
    └────────┘        └────┬───┘
        │                  │
        │            Create NCR
        │            (UC-014)
        │                  │
        │            ┌─────▼──────┐
        │            │ Investigate│
        │            │ Root Cause │
        │            └─────┬──────┘
        │                  │
        │            Create
        │            Corrective
        │            Action
        │                  │
        │            ┌─────▼──────┐
        │            │Verify Fix  │
        │            │Re-Inspect  │
        │            └─────┬──────┘
        │                  │
        │            ┌─────▼──────┐
        ▼            ▼            │
    ┌──────────────────┐          │
    │ Activity Approved│◀─────────┘
    │ & Work Proceeds  │
    └──────────────────┘
```

---

## 7. Financial Tracking & Reporting

```
                    ┌─────────────────────────────┐
                    │   FINANCIAL USE CASES       │
                    └─────────────────────────────┘

        ┌──────────────────────────────────────────┐
        │    Cost Data Collected From:             │
        │    • Labor (Timesheets)                  │
        │    • Materials (Receipts)                │
        │    • Equipment (Usage Logs)              │
        │    • Subcontractors (Invoices)           │
        └───────────────┬──────────────────────────┘
                        │
                        ▼
        ┌──────────────────────────────────────────┐
        │  Track Project Costs                     │
        │  (UC-016)                                │
        │  • Allocate to WBS                       │
        │  • Compare Budget vs. Actual             │
        │  • Calculate Variances & CPI             │
        └───────────────┬──────────────────────────┘
                        │
                        │
        ┌───────────────┴──────────────────┐
        │                                  │
        ▼                                  ▼
    ┌─────────────────┐          ┌──────────────────┐
    │Generate Monthly │          │  Generate Project│
    │Cost Status      │          │  Invoice         │
    │Reports          │          │  (UC-017)        │
    └─────────────────┘          └──────┬───────────┘
        │                               │
        │                         ┌─────▼──────┐
        │                         │  Route for │
        │                         │  Approval  │
        │                         └─────┬──────┘
        │                               │
        └───────────────┬───────────────┘
                        │
                        ▼
        ┌──────────────────────────────────────────┐
        │  Stakeholder Reports &                   │
        │  Executive Dashboards                    │
        │  (UC-019)                                │
        └──────────────────────────────────────────┘
```

---

## 8. Document Management & Control

```
                    ┌─────────────────────────────┐
                    │  DOCUMENT MANAGEMENT        │
                    │     USE CASES               │
                    └─────────────────────────────┘

        Document Created
            │
            ▼
        ┌──────────────────────────┐
        │  Upload to System        │
        │  (UC-018)                │
        └──────┬───────────────────┘
               │
               ▼
        ┌──────────────────────────┐
        │  Document Controller     │
        │  • Assigns ID            │
        │  • Adds Metadata         │
        │  • Sets Approvers        │
        └──────┬───────────────────┘
               │
               ▼
        ┌──────────────────────────┐
        │  Approval Workflow       │
        │  Route to Approvers      │
        └──────┬───────────────────┘
               │
               ▼
        ┌──────────────────────────┐
        │  Distribute Document     │
        │  to Recipients           │
        │  Track Acknowledgment    │
        └──────┬───────────────────┘
               │
        ┌──────┴──────────────┐
        │                     │
        ▼                     ▼
    ┌────────────┐        ┌─────────────┐
    │ Current    │        │  Archive    │
    │ Version    │        │  Previous   │
    │ in Use     │        │  Versions   │
    └────────────┘        │ (Audit Trail)
                          └─────────────┘
```

---

## 📚 Related Documents

- [07_Use_Case_Specification.md](07_Use_Case_Specification.md) - Detailed use case descriptions
- [09_Business_Workflow_Design.md](09_Business_Workflow_Design.md) - Workflow state machines
- [27_EPC_End_to_End_Process_Map.md](27_EPC_End_to_End_Process_Map.md) - Process flow diagrams

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Business Analysts, System Designers
