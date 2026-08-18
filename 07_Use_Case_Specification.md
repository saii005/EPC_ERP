# 07. Use Case Specification

## 📋 Overview

This document describes the major use cases for the EPC ERP System. Each use case captures a specific interaction between a user and the system to achieve a business goal.

---

## 1. Project Initiation Use Cases

### UC-001: Create New Project
**Actor:** Project Director, Finance Manager  
**Trigger:** Client contract signed  
**Preconditions:** Contract document available, project team identified  
**Main Flow:**
1. Actor selects "Create New Project"
2. System displays project creation form
3. Actor enters project details (name, client, contract value, timeline)
4. Actor uploads contract document
5. Actor defines initial stakeholders and approvers
6. Actor creates Work Breakdown Structure
7. System creates project and generates project ID
8. System sends notifications to project team

**Postconditions:** Project created, team notified, ready for planning  
**Exceptions:** Contract document invalid → System displays error message

---

### UC-002: Establish Project Budget
**Actor:** Finance Manager, Project Manager  
**Trigger:** Project created, contract financial terms defined  
**Main Flow:**
1. Actor selects "Create Budget"
2. System displays budget template from similar projects
3. Actor customizes budget categories and amounts
4. Actor links budget to WBS cost centers
5. Actor specifies budget approval thresholds
6. Actor submits budget for approval
7. System routes to Finance Manager for approval
8. Finance Manager reviews and approves
9. System establishes budget baseline

**Postconditions:** Budget approved, baseline established  
**Exceptions:** Budget exceeds contract value → System displays warning

---

## 2. Engineering Use Cases

### UC-003: Create Engineering Deliverable
**Actor:** Lead Engineer, Design Engineer  
**Trigger:** Design phase started  
**Main Flow:**
1. Actor selects "New Deliverable"
2. System displays deliverable form (type, owner, due date)
3. Actor selects engineering discipline (structural, mechanical, electrical)
4. Actor attaches document file (Word, PDF, CAD)
5. Actor specifies review points and approvers
6. System creates deliverable record with version control
7. Actor submits for review
8. System notifies reviewers

**Postconditions:** Deliverable submitted for review  

---

### UC-004: Execute Design Review Workflow
**Actor:** Lead Engineer (reviewer)  
**Trigger:** Deliverable submitted for review  
**Main Flow:**
1. Lead Engineer receives notification of deliverable for review
2. Actor downloads and reviews deliverable document
3. Actor adds comments and questions directly in document
4. Actor indicates review status: Approved / Approved with Comments / Rejected
5. System tracks review cycle time
6. If approved: Deliverable marked as reviewed
7. If approved with comments: Routing to Design Engineer for action
8. If rejected: Routing back to designer with comments

**Postconditions:** Review complete, comments captured, next step triggered  

---

### UC-005: Create Bill of Materials (BOM)
**Actor:** Design Engineer  
**Trigger:** Equipment and material selections finalized  
**Main Flow:**
1. Actor selects "Create BOM"
2. System displays BOM template for project
3. Actor enters line items: description, quantity, unit, specification
4. Actor attaches equipment datasheets and drawings
5. Actor specifies material sources (preferred vendors, alternate vendors)
6. System performs cost roll-up calculation
7. System identifies long-lead items (>8 weeks)
8. Actor submits BOM to Procurement Manager
9. System generates preliminary procurement plan

**Postconditions:** BOM complete, signals procurement to begin RFQ process  

---

## 3. Procurement Use Cases

### UC-006: Create & Issue Request for Quotation (RFQ)
**Actor:** Procurement Specialist  
**Trigger:** BOM received from Engineering  
**Main Flow:**
1. Actor selects "Create RFQ" from BOM
2. System populates RFQ with equipment specs and drawings
3. Actor specifies delivery terms and conditions
4. Actor selects list of vendors to quote
5. System generates RFQ document with unique ID
6. Actor distributes RFQ to selected vendors (email/portal)
7. System tracks RFQ issuance and receipt by vendors
8. System creates reminder for quote deadline
9. Vendors submit quotations within specified timeframe

**Postconditions:** RFQs issued, vendors responding  

---

### UC-007: Evaluate Bids & Create Purchase Order
**Actor:** Procurement Manager  
**Trigger:** Vendor quotations received  
**Main Flow:**
1. System collects all vendor quotations
2. Procurement Manager initiates bid evaluation
3. System displays bid evaluation matrix with criteria (price, delivery, quality, payment terms)
4. Actor scores each vendor against criteria
5. System calculates weighted scores
6. System ranks vendors by score
7. Actor selects winning vendor(s)
8. System generates Purchase Order from winning bid
9. Actor adds PO-specific terms and conditions
10. Actor routes PO for approval (approval threshold-dependent)
11. Finance Manager approves
12. System issues PO to vendor electronically

**Postconditions:** PO issued, vendor notified, payment terms established  

---

### UC-008: Track Vendor Performance
**Actor:** Vendor Manager  
**Trigger:** Monthly scorecard generation  
**Main Flow:**
1. System collects vendor performance data (on-time delivery, quality, payment terms compliance)
2. System calculates scorecard metrics (% on-time, % quality, % compliance)
3. System generates monthly scorecard for each vendor
4. Vendor Manager reviews scorecard
5. System identifies vendors with issues (score < threshold)
6. Vendor Manager initiates corrective action discussions
7. Vendor provides action plan
8. System tracks corrective action closure
9. System updates vendor approved status based on performance

**Postconditions:** Vendor performance tracked, corrective actions managed  

---

## 4. Materials & Logistics Use Cases

### UC-009: Receive Material & Update Warehouse
**Actor:** Warehouse Manager  
**Trigger:** Material delivery to warehouse  
**Main Flow:**
1. Warehouse Manager receives material shipment from courier
2. Actor scans shipment bar code or enters shipment details
3. System displays associated PO and expected delivery
4. Actor verifies quantity received matches PO
5. Actor records receipt inspection (visual condition: OK/Damaged)
6. System creates Material Receipt Voucher (MRV)
7. Actor assigns warehouse location (bin/shelf/pallet)
8. For serialized items: Actor records serial numbers, heat numbers, batch codes
9. System updates warehouse inventory
10. System records receipt for QA inspection hold (if required)

**Postconditions:** Material received, inventory updated, inspection scheduled  

---

### UC-010: Issue Material to Site
**Actor:** Warehouse Manager, Site Supervisor  
**Trigger:** Construction activity requires material  
**Main Flow:**
1. Site Supervisor submits material issue request
2. System displays material availability and location
3. Warehouse Manager picks material from location
4. System generates issue-to-site document
5. Actor records material custodian (Site Supervisor)
6. For tracked items: System records serial numbers being issued
7. System generates packing slip and shipping document
8. Material transported to site
9. Site Supervisor receives material and signs receipt
10. System updates inventory (warehouse to site transfer)

**Postconditions:** Material issued, Site Supervisor now custodian, inventory tracked  

---

## 5. Construction Use Cases

### UC-011: Create Daily Progress Report (DPR)
**Actor:** Site Supervisor, Foreman  
**Trigger:** End of business day on-site  
**Main Flow:**
1. Site Supervisor opens daily progress report form
2. Actor selects date and work activities completed
3. Actor enters work summary (description of work done)
4. Actor records labor input (crew size, hours worked)
5. Actor records material consumed/issued
6. Actor records equipment used
7. Actor specifies percentage completion of activities
8. Actor notes delays, issues, or change requests needed
9. Actor attaches photos of completed work
10. System calculates schedule variance (planned vs. actual completion)
11. System calculates cost impacts based on labor and material actuals
12. Actor submits DPR to Construction Manager
13. Construction Manager reviews and approves

**Postconditions:** Daily progress recorded, rolled-up to project status  

---

### UC-012: Manage Permit-to-Work (PTW)
**Actor:** Safety Officer, Site Supervisor  
**Trigger:** High-risk activity scheduled (hot work, confined space, excavation)  
**Main Flow:**
1. Site Supervisor identifies work as high-risk
2. Actor selects appropriate PTW form (hot work/confined space/etc.)
3. System displays activity checklist and hazards
4. Actor specifies work location, time, and crew
5. Actor identifies hazards and safety controls
6. Actor specifies PPE requirements
7. Safety Officer reviews and approves PTW
8. Actor posts approval at work location
9. Work proceeds under PTW conditions
10. Upon completion, actor closes PTW and verifies all controls removed

**Postconditions:** High-risk work properly authorized and managed  

---

## 6. Quality Use Cases

### UC-013: Conduct Inspection Per Inspection and Test Plan (ITP)
**Actor:** QC Inspector  
**Trigger:** Construction activity reaches inspection hold point  
**Main Flow:**
1. Inspector receives notification of hold point reached
2. System displays ITP for that activity with inspection checklist
3. Inspector performs inspection per checklist
4. Inspector records observations (yes/no/measurement values)
5. Inspector attaches photos of inspection
6. If PASS: Inspector marks activity as passed, work can proceed
7. If FAIL: Inspector creates Non-Conformance Report (NCR)
8. System generates inspection report with sign-off
9. System updates project quality compliance record

**Postconditions:** Inspection complete, result recorded, next step triggered  

---

### UC-014: Manage Non-Conformance Report (NCR)
**Actor:** QC Inspector, Quality Manager, Engineering  
**Trigger:** Inspection failed or defect discovered  
**Main Flow:**
1. Inspector creates NCR with defect description
2. QC Manager reviews NCR for severity (critical/major/minor)
3. Engineering identifies root cause
4. Quality Manager creates corrective action plan
5. System assigns corrective action to responsible party
6. Responsible party completes corrective action
7. Inspector verifies corrective action
8. If satisfactory: NCR closed
9. System updates quality trend metrics

**Postconditions:** Defect managed, corrective action completed, quality improved  

---

## 7. HSE Use Cases

### UC-015: Report Incident / Near-Miss
**Actor:** Site Supervisor, Safety Officer, Employee  
**Trigger:** Safety incident or near-miss occurs on-site  
**Main Flow:**
1. Employee/Supervisor reports incident to Safety Officer
2. Safety Officer opens incident report form
3. Actor enters incident details (date, time, location, description)
4. Actor specifies incident type (injury/near-miss/hazard/environmental)
5. Actor records immediate actions taken
6. Safety Officer conducts initial investigation
7. Safety Officer identifies root cause(s)
8. Safety Officer specifies corrective and preventive actions
9. System routes to responsible party for implementation
10. Party completes actions and closes incident
11. Safety Officer verifies closure

**Postconditions:** Incident documented, corrective actions tracked, HSE metrics updated  

---

## 8. Financial Use Cases

### UC-016: Track Project Costs
**Actor:** Finance Manager, Cost Controller  
**Trigger:** Ongoing during project execution  
**Main Flow:**
1. System collects cost data from multiple sources:
   - Labor costs (timesheets)
   - Material costs (receipts and invoices)
   - Equipment costs (equipment time logs)
   - Subcontractor costs (invoices and claims)
2. System allocates costs to WBS activities and cost centers
3. System rolls up costs by project, phase, and cost type
4. System calculates actuals vs. budget and variance
5. System calculates cost performance index (CPI)
6. System generates cost status report
7. Finance Manager reviews report
8. Finance Manager identifies cost drivers and hot spots
9. Finance Manager makes recommendations for cost control
10. Project Manager implements corrective actions if needed

**Postconditions:** Project costs tracked, variances identified, management action taken  

---

### UC-017: Generate Project Invoice
**Actor:** Finance Manager, Billing Clerk  
**Trigger:** Billing event occurs (milestone complete, time period end)  
**Main Flow:**
1. Billing Clerk identifies billing event (milestone completed, monthly billing)
2. System gathers supporting documentation:
   - Delivery certificates
   - Inspection reports
   - Work completion certificates
3. Billing Clerk creates invoice with detail of work completed
4. System calculates invoice amount per contract terms
5. Invoice routed for internal approval (Project Manager → Finance Manager)
6. Finance Manager approves
7. System issues invoice to client (email + portal upload)
8. System tracks invoice status (sent, received, approved for payment, paid)
9. Finance team manages payment collection and reconciliation

**Postconditions:** Invoice issued, payment tracked, revenue recognized  

---

## 9. Document Management Use Cases

### UC-018: Control & Distribute Project Document
**Actor:** Document Controller  
**Trigger:** New project document created or updated  
**Main Flow:**
1. Project team member uploads document to system
2. Document Controller reviews document
3. System assigns unique document ID
4. Controller adds metadata (title, author, version, classification)
5. Controller specifies distribution list
6. System automatically distributes to all recipients
7. System tracks receipt and acknowledgment
8. When document superseded: System archives old version, maintains audit trail
9. System ensures only current version used
10. For compliance documents: System enforces access controls

**Postconditions:** Document distributed, version control enforced, compliance maintained  

---

## 10. Reporting & Analytics Use Cases

### UC-019: Generate Project Status Report
**Actor:** Project Manager  
**Trigger:** Weekly/monthly status report due  
**Main Flow:**
1. Project Manager selects "Generate Status Report"
2. System collects current project data:
   - Schedule status (planned vs. actual)
   - Cost status (budget vs. actual)
   - Quality status (inspection results)
   - Risk status (open risks and mitigation)
   - Resource status (utilization)
3. System generates report with charts and metrics
4. Project Manager customizes content and adds narrative
5. System routes to approver (Program Manager/Director)
6. Approver reviews and approves
7. System distributes to stakeholders (email/portal)
8. System archives report

**Postconditions:** Status report distributed, stakeholders informed  

---

## 📚 Next Steps

1. Review [09_Business_Workflow_Design.md](09_Business_Workflow_Design.md) for workflow state machines
2. Check [45_Page_and_Screen_Specification.md](45_Page_and_Screen_Specification.md) for UI implementation
3. See [51_Backend_Interface_Specification.md](51_Backend_Interface_Specification.md) for API requirements

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Business Analysts, System Designers
