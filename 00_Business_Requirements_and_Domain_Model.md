# 00. Business Requirements and Domain Model

## 1. Executive Summary & Business Context
Engineering, Procurement, and Construction (EPC) projects operate in high-stakes, capital-intensive environments where margins depend on rigorous schedule management, accurate cost control, and multi-disciplinary coordination. The **EPC ERP Business Requirements and Domain Model** establishes the architectural foundation for building a domain-specific enterprise system on the **Frappe/ERPNext** framework.

This document bridges the gap between high-level executive goals and technical database architecture, defining the core business entities, operational rules, and traceability requirements needed to run complex capital projects successfully.

---

## 2. Core Business Requirements

To replace disjointed point solutions and legacy software, the EPC ERP system must fulfill several critical functional drivers:

* **Multi-Project Portfolio Visibility:** Real-time aggregation of project health across multiple concurrent civil, industrial, or infrastructure mega-projects.
* **Work Breakdown Structure (WBS) & Cost Breakdown Structure (CBS) Integration:** Seamless linking of engineering deliverables, procurement packages, and site execution tasks directly to financial budgets.
* **Earned Value Management (EVM):** Automated calculation of Cost Performance Index (CPI), Schedule Performance Index (SPI), Estimate at Completion (EAC), and Variance at Completion (VAC).
* **End-to-End Traceability:** Unbroken tracking from client contract award and engineering revision control (IFR/IFA/IFC) to material fabrication, site installation, quality sign-off (ITP), and final handover.
* **Compliance & Risk Management:** Automated tracking of HSE incidents, non-conformance reports (NCRs), vendor performance scorecards, and regulatory statutory requirements.

---

## 3. High-Level EPC Domain Model

The domain model identifies the key business entities (DocTypes in Frappe terminology) and their relational hierarchies.

[Image of EPC project management workflow diagram]

### Key Domain Entities:
1. **Project:** The parent container holding contract value, baseline budgets, start/end dates, and portfolio metadata.
2. **Work Breakdown Structure (WBS):** Hierarchical decomposition of project scope into manageable packages (Engineering, Procurement, Construction).
3. **Cost Breakdown Structure (CBS):** Financial ledger mapping costs to WBS codes (Labor, Material, Subcontractor, Equipment, Overhead).
4. **Engineering Deliverable (MDR):** Drawings, datasheets, and calculations managed under strict revision control (IFR, IFA, IFC).
5. **Procurement Package:** Grouping of materials or services into Requisitions (MR), Requests for Quotation (RFQ), Technical Bid Evaluations (TBE), and Purchase Orders (PO) / Subcontracts.
6. **Material Log & Warehouse:** Inventory tracking down to heat numbers, serial numbers, and storage yard locations.
7. **Daily Progress Report (DPR):** Site logging of quantities installed, labor hours deployed, and equipment utilization against scheduled WBS nodes.

---

## 4. Frappe / ERPNext System Mapping Strategy

To leverage the power of ERPNext while satisfying EPC-specific domain logic, standard modules are extended via the custom `epc_core` Frappe app:

* **ERPNext Projects Module:** Extended to support deep WBS hierarchies, milestone tracking, and CBS cost rollups.
* **ERPNext Buying & Stock Modules:** Enhanced to support Technical/Commercial Bid Evaluations (TBE/CBE), long-lead item monitoring, and heat-number material traceability.
* **ERPNext Quality & Maintenance Modules:** Customized to handle Inspection and Test Plans (ITP), punch lists, and HSE safety permit workflows.