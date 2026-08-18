# 13. Procurement Domain Design

## 📋 Overview

This document describes the Procurement domain of the EPC ERP System, covering vendor management, purchase requisitions, RFQs, purchase orders, and supplier relationship management.

---

## 1. Procurement Domain Scope

The Procurement domain manages:
- **Vendor Management:** Vendor qualification, performance tracking, compliance
- **Procurement Planning:** Procurement strategy, vendor selection, lead time analysis
- **Requisition Management:** Purchase requisitions from multiple sources
- **Request for Quotation (RFQ):** Creating and distributing RFQs, managing responses
- **Bid Evaluation:** Scoring bids, evaluating vendors, selecting winners
- **Purchase Order Management:** Creating, tracking, amending, and closing POs
- **Vendor Communication:** Portal access, document sharing, status updates
- **Procurement Metrics:** Performance tracking, cost analysis, savings tracking

---

## 2. Procurement Process Flow

```
BOM from Engineering
        ↓
   Requisition Analysis
        ↓
   Vendor Pre-qualification
        ↓
   Procurement Strategy
        ↓
   Create RFQ
        ↓
   Distribute to Vendors
        ↓
   Receive Quotations
        ↓
   Evaluate Bids
        ↓
   Award to Vendor
        ↓
   Create & Issue PO
        ↓
   Track Delivery
        ↓
   Quality Inspection
        ↓
   Invoice & Payment
```

---

## 3. Vendor Management

### 3.1 Vendor Master Data
- **Company Information:** Name, legal entity, registration numbers
- **Contact Information:** Addresses, phone, email, website
- **Financial Information:** Banking details, credit rating, insurance
- **Certifications:** ISO 9001, ASME, API, ISO 14001, OHSAS 18001
- **Capabilities:** What they supply (equipment, materials, services, subcontracts)
- **Geographic Coverage:** Locations they serve
- **Performance History:** Previous projects, references

### 3.2 Vendor Qualification
**Criteria:**
- Financial stability (credit rating, financial statements)
- Quality management (ISO 9001 or equivalent)
- Technical capability (equipment/materials they can supply)
- HSE credentials (safety record, certifications)
- Geographic proximity (for logistics efficiency)
- References from previous clients
- Compliance with company standards

**Process:**
1. Receive vendor questionnaire
2. Evaluate against qualification criteria
3. Request supporting documentation (certificates, references)
4. Site visit/audit if required
5. Approve/reject for each capability
6. Maintain approved vendor list by category

### 3.3 Vendor Performance Metrics
- **On-Time Delivery %:** % of orders delivered by promised date
- **Quality %:** % of orders received without defects
- **Payment Terms Compliance:** % of invoices with correct terms/details
- **Responsiveness:** Average response time to queries/changes
- **Cost Competitiveness:** Price vs. market average
- **Overall Score:** Weighted average of above metrics

**Scorecard Frequency:** Monthly or quarterly  
**Target Score:** >85 for continued approval

---

## 4. Procurement Planning

### 4.1 Procurement Strategy Development
**Inputs:** BOM from engineering, project schedule, budget constraints

**Strategy Elements:**
- **Item Classification:** Capital equipment, bulk materials, MRO supplies, services
- **Sourcing Strategy:** Single-source, multi-source, framework agreements
- **Lead Time Analysis:** Identify long-lead items requiring early action
- **Cost Estimation:** Preliminary costs for budgeting
- **Vendor Selection:** Which vendors for which items
- **Logistics Planning:** Shipping methods, consolidation opportunities
- **Payment Terms:** Standard vs. milestone-based payment

### 4.2 Long-Lead Item Management
**Definition:** Items with lead time >8 weeks from RFQ to delivery

**Process:**
1. Identify at 20% design phase
2. Issue RFQs by Month 3
3. Evaluate and award by Month 4
4. Place PO by Month 5
5. Monitor delivery weekly
6. Escalate delays immediately
7. Arrange expediting if needed

---

## 5. Requisition Management

### 5.1 Requisition Types
- **Engineering BOM Requisition:** From design team
- **Stock Replenishment:** For materials below safety stock level
- **Consumables:** Office supplies, site consumables, MRO items
- **Subcontract Requisition:** For outsourced work
- **Ad Hoc Request:** Unplanned needs that arise

### 5.2 Requisition Data
- **Item Description:** Clear description of what is needed
- **Specification:** Technical specifications, standards, drawings
- **Quantity:** How much is needed
- **Unit:** Unit of measure (each, ton, meter, etc.)
- **Delivery Date:** When needed
- **Delivery Location:** Where to be shipped
- **Cost Center:** Charging department
- **Approval Status:** Awaiting approval, approved, rejected

---

## 6. Request for Quotation (RFQ)

### 6.1 RFQ Structure
- **RFQ Number:** Unique identifier (e.g., RFQ-2024-001)
- **Item Details:** Description, quantity, specification, drawings
- **Delivery Requirements:** Delivery date, location, terms
- **Technical Requirements:** Quality standards, certifications required
- **Commercial Terms:** Payment terms, currency, incoterms
- **Delivery Deadline:** When quotation must be received
- **Questions:** Contact person for vendor questions

### 6.2 RFQ Distribution
- **Identification of Potential Vendors:** Approved vendor list + new vendors
- **Selection of Bidders:** Typically 3-5 vendors for competitive bidding
- **Electronic Distribution:** Email, vendor portal, or EDI
- **Tracking:** Confirmation of receipt, deadline reminders
- **Query Management:** Log vendor questions, provide clarifications
- **Late Submissions:** Policy for accepting/rejecting late bids

---

## 7. Bid Evaluation

### 7.1 Evaluation Criteria
| Criterion | Weight | Scoring |
|-----------|--------|---------|
| **Price** | 40% | Lowest price = 100 points |
| **Delivery** | 30% | On-schedule = 100 points |
| **Quality** | 20% | Past quality record |
| **Terms** | 10% | Payment terms, warranty |

### 7.2 Evaluation Process
1. Collect all quotations by deadline
2. Screen bids for completeness and compliance
3. Technical evaluation (capability, specifications)
4. Commercial evaluation (price, payment terms, warranty)
5. Calculate weighted scores
6. Prepare bid summary and recommendation
7. Route for approval
8. Notify winning and losing vendors
9. Award to winning vendor

### 7.3 Special Evaluations
- **Single Bid:** May proceed if price is market competitive
- **No Bids:** Escalate, may re-issue RFQ with adjusted terms
- **Sole Source:** Approved for strategic vendors, with justification
- **Competitive Bids:** Minimum 2-3 bids for <$50K; 3-5 for >$50K

---

## 8. Purchase Order Management

### 8.1 PO Creation
- **Link to Bid:** Reference winning bid/quotation
- **PO Number:** Unique identifier (auto-generated)
- **Vendor Details:** Name, address, contact person
- **Item Details:** Description, quantity, unit price, total
- **Delivery Terms:** Date, location, incoterms, freight terms
- **Payment Terms:** Net 30, Net 60, milestone-based, etc.
- **Quality Requirements:** Standards, certifications, inspection requirements
- **Penalty/Incentive:** Late delivery penalty, early delivery bonus
- **Conditions:** Warranty, spare parts, training, documentation required

### 8.2 PO Status Tracking
- **Issued:** PO sent to vendor
- **Acknowledged:** Vendor confirms receipt and acceptance
- **In-Transit:** Material on way to warehouse
- **Received & Inspected:** Goods received and QA approved
- **3-Way Match:** PO, receipt, and invoice verified
- **Approved for Payment:** Ready to pay
- **Paid:** Payment completed
- **Closed:** PO completed and archived

### 8.3 PO Changes & Amendments
- **Quantity Changes:** Increase/decrease order quantity
- **Delivery Date Changes:** Push out or accelerate delivery
- **Specification Changes:** Minor changes to technical requirements
- **Amount Changes:** Adjust pricing based on market changes
- **Amendment Process:** Formal amendment, approval, vendor acknowledgment

---

## 9. Vendor Portal & Communication

### 9.1 Vendor Self-Service Portal
- **PO Visibility:** View all POs, status, terms, payment date
- **Invoice Submission:** Upload invoices for 3-way matching
- **Shipment Tracking:** Track shipments, provide ETAs
- **Document Management:** Upload certificates, datasheets, test reports
- **Query Management:** Respond to company questions, raise their own
- **Performance Scorecards:** View their scorecard and feedback
- **Payment Status:** View payment due dates and history

### 9.2 Communication Methods
- **Email:** Routine communications
- **Portal:** Document sharing, official communications
- **EDI:** For high-volume, regular vendors
- **Phone/Video Call:** For urgent issues or complex discussions
- **Site Visits:** For major vendors, periodic audits

---

## 10. Procurement Metrics & KPIs

| KPI | Target | Frequency |
|-----|--------|-----------|
| **On-Time Delivery %** | >95% | Monthly |
| **Quality (Defect-Free %)** | >98% | Monthly |
| **Cost Variance** | ±5% | Monthly |
| **Procurement Lead Time** | Per plan | Per item |
| **Vendor Approval %** | >85 score | Quarterly |
| **Invoice On-Time %** | >95% | Monthly |
| **RFQ Response Rate** | >80% | Per RFQ |

---

## 11. Procurement Policies

### 11.1 Vendor Selection Policy
- Minimum 3 quotes for items >$10,000 (or sole-source justification)
- Approved vendor list preferred; new vendors need qualification
- Local content preference where applicable
- Women/minority-owned business enterprises (WMBE) consideration

### 11.2 Payment Policy
- Standard payment terms: Net 30-60 days
- Milestone payments for subcontracts
- Retainage: 5-10% until final acceptance
- Early payment discounts evaluated for cash flow benefit
- No payment until 3-way match complete

### 11.3 Quality Policy
- All vendors must have quality management system
- Critical items require inspection certificates (certs of conformance)
- Right of access to vendor facilities for audits
- Non-conformances documented and corrected

---

## 📚 Related Documents

- [04_Functional_Requirements.md](04_Functional_Requirements.md) - Procurement requirements
- [14_Vendor_Management_Design.md](14_Vendor_Management_Design.md) - Vendor details
- [08_Use_Case_Diagram.md](08_Use_Case_Diagram.md) - Procurement use cases

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Procurement Managers, Procurement Specialists
