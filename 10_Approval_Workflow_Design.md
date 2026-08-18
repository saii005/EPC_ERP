# 10. Approval Workflow Design

## 📋 Overview

This document specifies detailed approval workflow rules, thresholds, and routing logic for the EPC ERP System. It defines who approves what, when, and under what conditions.

---

## 1. General Approval Principles

### 1.1 Segregation of Duties
- No user can self-approve their own actions
- Approver must be at higher authority level than requester
- Independent reviews required for financial transactions >$10,000

### 1.2 Approval Thresholds
All approval routing based on monetary amount, where applicable

### 1.3 Escalation Rules
- If approver unavailable for >2 days: automatically escalate to next level
- For urgent matters: escalation to Director possible with justification

---

## 2. Purchase Order Approval Workflow

### 2.1 PO Approval Matrix

| PO Amount | Required Approvers | Timeline | Notes |
|-----------|-------------------|----------|-------|
| < $1,000 | Procurement Manager | 1 day | Routine, standard vendors |
| $1,000 - $10,000 | Procurement Mgr + Finance Analyst | 2 days | Standard review |
| $10,000 - $50,000 | Procurement Mgr + Finance Mgr | 3 days | Financial review required |
| $50,000 - $250,000 | Procurement Mgr + Finance Mgr + Project Director | 5 days | High-value items |
| > $250,000 | + CEO/MD approval | 5-10 days | Strategic items, contracts |
| Subcontracts | Procurement Mgr + Legal + Finance Mgr + Project Mgr | 10 days | Requires legal review |

### 2.2 PO Approval Rules
- **Approval Rule 1:** For new vendors (not on approved list) → add Vendor Manager approval
- **Approval Rule 2:** For services > $50K → add HR Manager approval (resource availability)
- **Approval Rule 3:** For items with long lead time (>12 weeks) → add Project Manager approval
- **Approval Rule 4:** For expedited POs (shorter than standard lead time) → add Procurement Manager comment

---

## 3. Change Order Approval Workflow

### 3.1 Engineering Change Order (ECO) Approval

| Change Type | Cost Impact | Schedule Impact | Required Approvers | Timeline |
|-------------|------------|-----------------|-------------------|----------|
| **Cosmetic/Minor** | None | None | Engineering Mgr | 1 day |
| **Technical** | None | None | Engineering Mgr + Lead Engr | 2 days |
| **Scope** | < 5% | < 2 weeks | Project Mgr + Engineering Mgr | 3 days |
| **Cost** | 5-10% | Any | Project Mgr + Finance Mgr | 5 days |
| **Cost** | > 10% | Any | Project Director + Finance Mgr | 7 days |
| **Schedule** | Any | > 4 weeks | Project Director | 5 days |
| **Client Scope** | Any | Any | Client + Project Director | 10 days |

### 3.2 ECO Approval Rules
- **Rule 1:** If change affects multiple disciplines → add heads of other disciplines
- **Rule 2:** If schedule impact > critical path → add Senior PM or PMO
- **Rule 3:** If client visible → always get client approval
- **Rule 4:** For emergency changes → verbal approval, formal documentation within 24 hours

---

## 4. Budget & Cost Approval Workflow

### 4.1 Budget Amendment Approval

| Amendment Amount | Budget Impact | Required Approvers | Notes |
|-----------------|---------------|-------------------|-------|
| < $10,000 | < 1% | Project Manager | Routine variances |
| $10,000 - $50,000 | 1-3% | Project Mgr + Finance Mgr | Moderate adjustment |
| $50,000 - $250,000 | 3-5% | Project Director + Finance Mgr | Significant impact |
| > $250,000 | > 5% | CEO/MD + Finance Dir | Major budget change |

### 4.2 Budget Rules
- Budget cannot be exceeded without formal amendment
- No cost commitment >10% of unspent budget can be made without approval
- Monthly budget reviews with variance >5% require Finance Manager comment

---

## 5. Contract & Commercial Approval Workflow

### 5.1 Vendor Agreement Approval

| Agreement Type | Value | Duration | Required Approvers |
|----------------|-------|----------|-------------------|
| **Frame Agreement** | Any | > 1 year | Procurement Mgr + Legal + Finance |
| **Subcontract** | < $100K | Project term | Procurement Mgr + PM + Finance |
| **Subcontract** | > $100K | Project term | + Project Director + Legal |
| **Equipment Lease** | Any | Any | Procurement Mgr + Finance + Legal |
| **Maintenance Contract** | Any | > 1 year | Operations Mgr + Finance |

### 5.2 Commercial Terms Review
- All terms reviewed for payment milestones, warranties, insurance requirements
- Penalty clauses and incentives require Finance approval
- Payment terms >Net 60 require Finance Director approval
- Currency hedging required for non-USD contracts >$1M

---

## 6. Document & Deliverable Approval Workflow

### 6.1 Engineering Deliverable Approval

| Document Type | Review Level | Approver | Timeline |
|----------------|-------------|----------|----------|
| **Specification** | Draft | Lead Engineer | 2 days |
| **Specification** | Client Review | Engineering Manager | 3 days |
| **Specification** | Final Approval | Client Representative | 5 days |
| **Drawing** | Draft | Design Engineer Lead | 1 day |
| **Drawing** | 30% Review | Engineering Manager | 2 days |
| **Drawing** | 60% Review | Project Engineer | 2 days |
| **Drawing** | 90% Review | Client (if required) | 5 days |
| **Drawing** | Final (100%) | Lead Engineer | 1 day |
| **BOM** | Draft | Design Engineer | 1 day |
| **BOM** | Final | Procurement Manager | 2 days |
| **Calculation** | Draft | Calculation Review Engr | 2 days |
| **Calculation** | Final | Quality Assurance | 1 day |

### 6.2 Document Review Rules
- Client-visible deliverables require Project Manager final review
- Calculations require independent reviewer (not preparer)
- Interface documents (between disciplines) require both discipline heads
- Design basis changes require re-review of dependent documents

---

## 7. Quality & Compliance Approval Workflow

### 7.1 NCR (Non-Conformance Report) Approval

| NCR Severity | Corrective Action | Approval | Closure Timeline |
|-------------|-----------------|----------|------------------|
| **CRITICAL** | Immediate stop-work, engineering redesign | Project Mgr + Client | 5 days |
| **MAJOR** | Rework, re-inspection, client notification | Project Mgr | 10 days |
| **MINOR** | Repair, re-inspection, document | QA Manager | 5 days |
| **OBSERVATION** | Document, process improvement | QA Manager | 30 days |

### 7.2 NCR Approval Rules
- Critical NCRs require immediate escalation to Project Director
- Any NCR requiring client notification needs client approval before closure
- Trend of similar NCRs (>3) triggers quality audit
- NCR closure requires evidence (photos, test reports) and inspector sign-off

---

## 8. Inspection & Test Plan (ITP) Approval

| ITP Type | Approver | Timeline | Notes |
|----------|----------|----------|-------|
| **Initial ITP** | Quality Manager | 5 days | Based on specs |
| **ITP Amendment** | Quality Manager | 2 days | Scope or scope changes |
| **Hold Point Release** | QC Inspector + PM | 1 day | Work can proceed |
| **Hold Point Hold** | QC Inspector | Same day | Defect found |

---

## 9. HSE & Incident Approval Workflow

### 9.1 Incident Severity & Approval

| Incident Type | Severity Level | Escalation | Reporting Timeline |
|---------------|----------------|------------|-------------------|
| **Near-Miss** | Low | HSE Officer | 1 day |
| **Minor Injury** | Medium | HSE Officer + First Aider | 1 day |
| **Lost Time Injury** | High | HSE Officer + PM + Director | 1 hour |
| **Fatality** | Critical | HSE Officer + CEO + Legal | Immediate |
| **Environmental Release** | Critical | HSE Officer + Director | Immediate |

### 9.2 Incident Closure Rules
- HSE Officer must approve closure
- All corrective actions must be verified complete
- Root cause analysis required for all incidents >Lost Time
- Similar incidents (>2) trigger management review

---

## 10. Invoice & Payment Approval Workflow

### 10.1 Invoice Approval Matrix

| Invoice Amount | 3-Way Match | Finance Review | Payment Approval |
|----------------|------------|-----------------|------------------|
| < $1,000 | Finance Analyst | Automatic | Finance Analyst |
| $1,000 - $10,000 | Finance Analyst | Finance Analyst | Finance Mgr |
| $10,000 - $50,000 | Finance Analyst | Finance Manager | Finance Manager |
| $50,000 - $250,000 | Finance Manager | Finance Manager | Finance Director |
| > $250,000 | Finance Manager | Finance Director | CFO |

### 10.2 Invoice Rules
- 3-way match must pass before payment approval
- Payment cannot exceed PO amount (or approved variation)
- Disputed invoices require vendor resolution before payment
- Early payment discounts require Finance Manager approval

---

## 11. Approval SLAs (Service Level Agreements)

| Approval Type | SLA | Escalation at |
|---------------|-----|--------------|
| Routine PO (<$10K) | 1 day | 2 days |
| Standard Approval | 2 days | 4 days |
| Financial Review | 3 days | 5 days |
| Management Approval | 5 days | 10 days |
| Client Approval | Contractual | +50% |

---

## 12. Approval Dashboard & Metrics

### 12.1 Approval Metrics Tracked
- **Average Approval Time:** by approval type, approver
- **Approval Bottlenecks:** approvers with longest queues
- **SLA Compliance:** % of approvals meeting SLA
- **Escalation Rate:** % of approvals escalated
- **Rejection Rate:** % of submissions rejected

### 12.2 Escalation Rules
If approval not completed within SLA:
1. Send reminder notification at 50% of SLA
2. Send escalation alert at 75% of SLA
3. Escalate to next approval level at 100% of SLA
4. For critical approvals (>10 days overdue), escalate to Director

---

## 13. Delegation of Approval Authority

### 13.1 Delegation Rules
- Approvers can delegate to peer (same authority level) with explicit notification
- Delegation maximum duration: 30 days
- Cannot delegate to subordinate (one level down) - must escalate instead
- Delegation audit trail maintained
- No multi-level delegation (A→B→C not allowed)

### 13.2 Common Delegations
- Project Manager delegates to Assistant PM during leave
- Finance Manager delegates to Senior Accountant for routine approvals
- Engineering Manager delegates to Senior Engineer for technical reviews

---

## 📚 Next Steps

1. Review [09_Business_Workflow_Design.md](09_Business_Workflow_Design.md) for workflow state machines
2. Check [42_Workflow_and_State_Machine_Design.md](42_Workflow_and_State_Machine_Design.md) for technical implementation
3. See [41_Permission_and_Role_Architecture.md](41_Permission_and_Role_Architecture.md) for system roles and permissions

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Process Architects, System Administrators
