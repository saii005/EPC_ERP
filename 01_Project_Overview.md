# 01. Project Overview: EPC ERP System

## Executive Summary
The **EPC Enterprise Resource Planning (ERP) System** is an enterprise-grade, comprehensive software solution built specifically for Engineering, Procurement, and Construction (EPC) contractors, project-driven organizations, and heavy industrial plant builders. Developed on the robust **Frappe Framework** and leveraging the foundational modules of **ERPNext**, this system bridges the gap between traditional discrete ERP workflows and the complex, milestone-driven, multi-disciplinary lifecycle of EPC projects.

---

## 1. Project Vision & Objectives
* **Single Source of Truth:** Unify engineering deliverables, procurement pipelines, vendor contracts, construction progress, cost control, and quality/HSE compliance into an integrated platform.
* **Real-time Cost & Schedule Control:** Implement Earned Value Management (EVM), Work Breakdown Structure (WBS), and Cost Breakdown Structure (CBS) integration to provide executive visibility into project margins and variance.
* **Traceability & Compliance:** Maintain end-to-end traceability from client tender and engineering document submittal to material fabrication, site erection, inspection testing, and final handover.
* **Extensibility & Agility:** Leverage Frappe's low-code architecture and Python backend to allow rapid tailoring for specialized industry requirements (Oil & Gas, Infrastructure, Power, Water, EPC manufacturing).

---

## 2. Core Scope & Domain Coverage
The EPC ERP system spans the entire project lifecycle, structured across key functional modules:
1. **Engineering Management:** Deliverable registers, review/approval cycles (IFR, IFA, IFC), technical submittals, and interoperability with BIM/CAD metadata.
2. **Procurement & Subcontracts:** Requisitions, RFQs, technical & commercial bid evaluations, purchase orders, subcontracts, and progressive billing.
3. **Vendor Management:** Qualification, performance scorecards, compliance certificates, and portal access.
4. **Material Management (SCM):** Material Receiving (MIV/MRV), site warehousing, traceability (heat numbers, serial numbers), and issue-to-site tracking.
5. **Construction Management:** Daily progress reports (DPR), subcontractor work measurement, labor and equipment deployment.
6. **Quality & HSE Management:** Inspection and Test Plans (ITP), Non-Conformance Reports (NCR), punch lists, safety incidents, toolbox talks, and permits to work (PTW).
7. **Planning & Cost Control:** Primavera/MS Project integration, WBS budgeting, commitment tracking, actual costs, and Earned Value analysis.
8. **Document Control:** Transmittals, revision histories, master deliverable registers, and vendor data requirements (VDRL).

---

## 3. Technology Stack
* **Backend:** Python 3.10+, Frappe Framework, REST & GraphQL APIs.
* **Frontend:** Vue.js, Frappe UI, Bootstrap, responsive dashboards.
* **Database & Caching:** MariaDB / PostgreSQL, Redis for queue management and caching.
* **Deployment:** Docker, Kubernetes, Nginx, Gunicorn, automated CI/CD pipelines.

---

## 4. Target Users & Stakeholders
* **Project Directors / Managers:** Executive dashboards, portfolio health, margin analysis, risk registers.
* **Engineering Leads:** Deliverable tracking, technical query logs.
* **Procurement & Contracts Officers:** RFQ management, vendor evaluation, contract execution.
* **Site Engineers / QA/QC / HSE Officers:** Daily logs, inspection sign-offs, incident reporting.
* **Finance & Accounting:** Project billing, milestone invoicing, cash flow forecasting, cost accounting.
