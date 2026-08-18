# 72. User Acceptance Testing (UAT)

## 1. UAT Strategy & Governance
User Acceptance Testing validates that the EPC ERP system satisfies real-world operational workflows across project management, engineering, procurement, and site execution.
* **Test Sign-off Gate:** Mandatory approval from Department Heads (Engineering Director, Procurement Head, Construction Manager, Chief Financial Officer).
* **Environment:** Dedicated staging server populated with anonymized historical project data.

## 2. UAT Execution Scenarios
* **Scenario A (Engineering to Procurement):** Create a Master Deliverable Register, approve an IFC drawing, trigger a Material Requisition, and verify Purchase Order generation.
* **Scenario B (Site Execution to Cost Control):** Submit a Daily Progress Report from a mobile tablet, verify quantity earned updates, and inspect automated SPI/CPI variance metrics.