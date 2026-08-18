# 03. Business Process Model

## 📋 Overview

This document describes the core business processes that the EPC ERP System must support. It outlines how work flows through the organization from project initiation through final handover.

---

## 1. Process Map - High Level

The EPC project lifecycle flows through these major phases:

```
INITIATION → ENGINEERING → PROCUREMENT → CONSTRUCTION → COMMISSIONING → CLOSURE
```

Each phase contains multiple sub-processes that overlap and interact.

---

## 2. Key Business Processes

### 2.1 Project Initiation & Contracting
**Objective:** Establish project context and secure commitment

**Flow:**
1. Receive client RFP (Request for Proposal)
2. Develop bid and cost estimate
3. Negotiate contract terms
4. Sign contract and obtain financing
5. Establish project in system
6. Create Work Breakdown Structure (WBS)
7. Create initial budget and schedule

**Key Outputs:** Project record, contract file, approved budget, master schedule, stakeholder register

**Responsible Roles:** Business Development, Project Director, Finance

---

### 2.2 Engineering & Design
**Objective:** Create technical deliverables that define what will be built

**Flow:**
1. Create detailed design specifications
2. Generate engineering drawings (P&IDs, GA drawings, equipment datasheets)
3. Create Bill of Materials (BOM) from drawings
4. Document design basis and technical approvals needed
5. Submit deliverables for client review
6. Incorporate client comments
7. Obtain final approvals (IFA - In For Approval, IFC - In For Construction)
8. Release to procurement and construction

**Key Outputs:** Specifications, drawings, BOMs, approval records, transmittals

**Responsible Roles:** Lead Engineer, Design Engineers, Engineering Manager, Client Representative

---

### 2.3 Procurement Planning & Vendor Identification
**Objective:** Identify what needs to be purchased and pre-qualify suppliers

**Flow:**
1. Analyze engineering deliverables to identify procurement needs
2. Classify items (capital equipment, materials, services, subcontracts)
3. Create procurement plan with lead times and critical items
4. Identify potential vendors from approved vendor list
5. Issue vendor pre-qualification requests
6. Evaluate vendor responses
7. Create approved vendor list for project
8. Identify long-lead items requiring early action

**Key Outputs:** Procurement plan, approved vendor list, purchase strategy, critical path items

**Responsible Roles:** Procurement Manager, Procurement Specialist, Vendor Management

---

### 2.4 Purchase Requisition & Request for Quotation (RFQ)
**Objective:** Create formal purchasing requests and solicit supplier quotes

**Flow:**
1. Generate purchase requisitions from procurement plan
2. Attach technical specifications and drawings
3. Create RFQs for strategic items and services
4. Distribute RFQs to qualified vendors
5. Track RFQ responses
6. Log vendor queries and provide clarifications
7. Record quotations in system
8. Prepare for bid evaluation

**Key Outputs:** Requisitions, RFQs, vendor quotations, queries and clarifications log

**Responsible Roles:** Procurement Specialist, Purchasing Officer, Technical Advisor

---

### 2.5 Bid Evaluation & Purchase Order (PO) Issuance
**Objective:** Evaluate vendor bids and place orders at best value

**Flow:**
1. Establish bid evaluation criteria (price, delivery, quality, payment terms)
2. Score vendor bids against criteria
3. Conduct technical evaluation of proposed equipment
4. Conduct commercial evaluation (price, payment terms, warranty)
5. Prepare bid summary and recommendation
6. Obtain approvals from management
7. Issue purchase orders to selected vendors
8. Communicate outcome to vendors
9. Establish supplier contact and expediting schedule

**Key Outputs:** Bid evaluation reports, approved purchase orders, vendor notifications

**Responsible Roles:** Procurement Manager, Finance, Approvers

---

### 2.6 Vendor Management & Supply Chain Execution
**Objective:** Ensure vendors deliver on time, in full, and per spec

**Flow:**
1. Track order status with vendors
2. Expedite critical/long-lead items
3. Monitor vendor compliance with delivery dates
4. Receive material/equipment documentation (certs of conformance, test reports)
5. Conduct vendor quality audits as needed
6. Manage change requests and technical queries
7. Track milestone deliveries (e.g., pre-fabrication inspections)
8. Record vendor performance metrics
9. Issue payment as goods are received
10. Maintain vendor scorecards for continuous improvement

**Key Outputs:** Status reports, inspection records, performance scorecards, payment records

**Responsible Roles:** Vendor Manager, Expeditor, QA Officer, Finance

---

### 2.7 Material Receipt & Warehouse Management
**Objective:** Receive materials/equipment, verify quality, store safely, issue to site

**Flow:**
1. Receive goods from vendor (truck delivery or courier)
2. Verify shipment against PO (quantity, description)
3. Conduct receiving inspection (visual condition, documentation)
4. Create material receipt record (MRV/MIV)
5. Record material in warehouse system with location
6. For serialized/batch items, record serial numbers, heat numbers, lot codes
7. Store material with proper labeling and safety measures
8. Track material movement within warehouse (receipts, transfers, stock counts)
9. Issue material to site based on construction schedule
10. Record issue documentation and custodian
11. Conduct periodic stock counts and audit

**Key Outputs:** Material receipts, warehouse transfers, issue-to-site records, stock audits

**Responsible Roles:** Warehouse Manager, Logistics, Site Supervisor

---

### 2.8 Construction Planning & Execution
**Objective:** Execute physical work on-site safely, on schedule, within budget

**Flow:**
1. Translate engineering documents and schedules into site work packages
2. Create detailed construction plan (sequencing, methods, resource requirements)
3. Identify craft labor, supervisory staff, equipment needs
4. Schedule work activities with dependencies
5. Issue work permits (Permit-to-Work system for high-risk activities)
6. Conduct site induction and toolbox talks
7. Execute daily work as per plan
8. Record daily progress (work hours, materials used, quantity completed)
9. Manage change orders and scope clarifications
10. Conduct inspections at key milestones
11. Record labor hours, equipment utilization
12. Manage site safety, incidents, near-misses
13. Update schedule and budget with actuals

**Key Outputs:** Work schedules, daily progress reports (DPR), labor timesheets, equipment logs, incident reports

**Responsible Roles:** Construction Manager, Site Supervisor, Safety Officer, Craft Workers

---

### 2.9 Quality & Inspection
**Objective:** Ensure all work and materials meet technical requirements

**Flow:**
1. Create Inspection and Test Plans (ITPs) based on specifications
2. Define inspection points (hold points where work pauses for inspection)
3. Conduct inspections as work reaches defined points
4. Record inspection results (pass/fail/conditional pass)
5. For failed inspections, create Non-Conformance Reports (NCRs)
6. Develop corrective action plans
7. Execute corrections and re-inspect
8. Maintain chain of test records (calibration certificates for test equipment)
9. Create final quality certification for each deliverable
10. Archive quality records for compliance

**Key Outputs:** Inspection plans, inspection reports, NCRs, corrective actions, quality certificates

**Responsible Roles:** QA Officer, QC Inspectors, Construction Manager

---

### 2.10 Health, Safety & Environment (HSE)
**Objective:** Maintain safe working conditions and minimize environmental impact

**Flow:**
1. Develop site HSE plan based on regulations and project risks
2. Conduct safety induction for all personnel
3. Conduct regular toolbox talks (safety briefings)
4. Monitor site for hazards
5. Enforce use of Personal Protective Equipment (PPE)
6. Report near-misses and hazard observations
7. Investigate incidents and document root causes
8. Develop corrective actions to prevent recurrence
9. Track HSE metrics (hours worked, near-misses, incidents)
10. Conduct HSE audits
11. Maintain HSE compliance documentation

**Key Outputs:** HSE plan, induction records, safety briefing logs, incident reports, audit findings

**Responsible Roles:** HSE Officer, Site Supervisor, Safety Committee

---

### 2.11 Cost Control & Financial Tracking
**Objective:** Monitor actual costs against budget and control profitability

**Flow:**
1. Establish project budget and cost breakdown structure (CBS)
2. Create cost centers for major work packages
3. Identify cost drivers (labor, materials, equipment, subcontracts)
4. Track commitments (POs issued, contracts signed)
5. Record actuals (invoices, timesheets, material usage)
6. Compare actual vs. budget on regular basis (weekly/monthly)
7. Identify variances and cost drivers
8. Implement cost control measures (value engineering, vendor negotiation)
9. Generate cost reports for management
10. Forecast final cost and profitability
11. Manage cash flow and payment scheduling

**Key Outputs:** Budget spreadsheets, commitment reports, cost actuals, variance analysis, forecasts

**Responsible Roles:** Project Finance Officer, Cost Controller, Accounting

---

### 2.12 Revenue & Billing
**Objective:** Invoice client for work performed and collect payment

**Flow:**
1. Establish billing terms in contract (milestone-based, time & materials, lump sum)
2. Identify billing events (design complete, equipment delivered, work completed)
3. Collect supporting documentation (delivery notes, inspection records, work completion certs)
4. Prepare invoice with detail of work performed and costs
5. Route invoice for internal approvals
6. Issue invoice to client with supporting documentation
7. Track invoice status (sent, received, disputed, approved for payment)
8. Manage payment collections
9. Record revenue in accounting system
10. Reconcile payments received

**Key Outputs:** Invoices, billing summaries, payment status reports, revenue records

**Responsible Roles:** Finance Manager, Billing Clerk, Accounting

---

### 2.13 Document Control & Traceability
**Objective:** Maintain centralized, traceable records of all project documentation

**Flow:**
1. Establish document control procedures and naming standards
2. Capture all project documents (plans, specifications, drawings, reports)
3. Assign document ID, classification, and metadata
4. Track document revisions and versions
5. Maintain approval/signature history for each document
6. Distribute documents to relevant stakeholders
7. Archive superseded versions with audit trail
8. Enable document search and retrieval
9. Ensure compliance with regulatory document retention requirements
10. Prepare document index and master registers for handover

**Key Outputs:** Document register, revision control logs, distribution records, audit trail

**Responsible Roles:** Document Controller, Document Custodians

---

### 2.14 Commissioning & Handover
**Objective:** Transition completed system from construction to client operations

**Flow:**
1. Prepare commissioning plan (sequence of testing and startup activities)
2. Develop operating and maintenance procedures
3. Train client operations and maintenance personnel
4. Conduct system startup and initial testing
5. Execute performance testing (does system meet specified performance?)
6. Address performance gaps and deficiencies
7. Create punch list of outstanding items
8. Complete outstanding work
9. Obtain final client acceptance and sign-off
10. Transfer operations to client
11. Archive all project records and data
12. Close out contracts with vendors and subcontractors

**Key Outputs:** Commissioning reports, training records, operations manuals, punch list closure, handover certificate

**Responsible Roles:** Project Manager, Construction Manager, Operations Lead, Client Representative

---

### 2.15 Project Closure & Lessons Learned
**Objective:** Formally close project and capture lessons for future improvement

**Flow:**
1. Conduct final reconciliation of budget vs. actual costs and schedule
2. Close out all open purchase orders and contracts
3. Settle all outstanding invoices and payments
4. Archive all project records and documentation
5. Conduct project post-mortem review
6. Capture lessons learned (what worked well, what could improve)
7. Document best practices identified during project
8. Update company procedures and standards based on lessons
9. Formally release project resources
10. Conduct exit meeting with client

**Key Outputs:** Final cost/schedule reports, lessons learned report, updated procedures, project closure certificate

**Responsible Roles:** Project Manager, Finance, HR, Project Team

---

## 3. Process Interactions & Dependencies

- **Parallel Execution:** Engineering, procurement, and construction planning often occur simultaneously
- **Engineering drives Procurement:** Engineering deliverables define what needs to be purchased
- **Procurement drives Construction:** Availability of materials determines construction schedule
- **Quality gates:** Inspections must pass before work proceeds
- **Financial tracking:** Runs continuously throughout all processes
- **Document control:** Operates across all processes

---

## 4. Key Process Metrics

| Process | Key Metric | Target |
|---------|-----------|--------|
| Engineering | Design review time | <5 days per review |
| Procurement | RFQ-to-PO time | <10 days |
| Vendor Mgmt | On-time delivery | >95% |
| Material Mgmt | Warehouse accuracy | >98% |
| Construction | Schedule variance | ±5% |
| Quality | Inspection pass rate | >95% first-time |
| HSE | Lost-time incidents | Zero |
| Finance | Invoice-to-payment | <30 days |

---

## 📚 Next Steps

1. Read [04_Functional_Requirements.md](04_Functional_Requirements.md) to understand specific system capabilities
2. Review [09_Business_Workflow_Design.md](09_Business_Workflow_Design.md) for detailed workflow state machines
3. Check [27_EPC_End_to_End_Process_Map.md](27_EPC_End_to_End_Process_Map.md) for visual process flows

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Business Analysts, Process Owners
