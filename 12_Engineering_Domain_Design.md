# 12. Engineering Domain Design

## 📋 Overview

This document describes the Engineering domain of the EPC ERP System, covering design deliverables, review cycles, technical specifications, and engineering workflows.

---

## 1. Engineering Domain Scope

The Engineering domain manages:
- **Deliverable Management:** Specifications, drawings, calculations, BOMs
- **Review Cycles:** IFR (In For Review) → IFA (In For Approval) → IFC (In For Construction)
- **Technical Approvals:** Engineering sign-offs and client approvals
- **Design Changes:** Engineering Change Orders (ECOs) and impact analysis
- **Design Basis:** Design assumptions, criteria, and engineering standards
- **Technical Queries:** RFIs (Request for Information) and TQs (Technical Queries)
- **Document Control:** Engineering document versioning and release management

---

## 2. Key Entities & Relationships

### 2.1 Engineering Deliverables
- **Specifications** (Process, Mechanical, Electrical, I&C)
- **Drawings** (P&IDs, General Arrangements, Equipment Schedules, Details)
- **Bills of Materials** (BOMs with quantities and specifications)
- **Calculations** (Design calculations, stress analysis, flow diagrams)
- **Technical Datasheets** (Equipment specs, material properties)
- **As-Built Documentation** (Final installed configuration)

### 2.2 Approval Stages
- **DRAFT:** Initial creation, internal review
- **IFR (In For Review):** Engineering team review, comments collection
- **IFA (In For Approval):** Client review and formal approval
- **IFC (In For Construction):** Released for procurement and construction use
- **CLOSED:** Superseded or obsolete

---

## 3. Deliverable Types & Workflows

### 3.1 Specifications
- **Process Specifications:** Detailed description of system/equipment operation
- **Equipment Datasheets:** Equipment nameplate data, performance parameters
- **Material Specifications:** Material grades, properties, certifications
- **Installation Specifications:** How to install/mount equipment
- **Inspection Specifications:** Quality criteria and acceptance criteria

**Approval Flow:** DRAFT → Engineering Review (5 days) → IFR → Client Review (5 days) → IFA → Release → IFC

### 3.2 Drawings
- **P&ID (Piping & Instrumentation Diagram):** System flow and control logic
- **GA (General Arrangement):** Overall layout and dimensions
- **Detail Drawings:** Component-level details
- **Equipment Datasheets:** Manufacturer data
- **Cable/Wiring Diagrams:** Electrical routing and connections
- **Isometric Drawings:** 3D representation

**Approval Stages:** 30% → 60% → 90% → 100% Design

### 3.3 Bills of Materials (BOMs)
- Complete list of equipment, materials, and consumables
- Quantities, unit prices, and lead times
- Vendor information and sourcing
- Technical specifications and drawings reference

**Use:** Drives procurement, cost estimation, and material tracking

---

## 4. Design Review Process

### 4.1 30% Design Review
**Timeline:** Month 2  
**Content:** Preliminary design, process flow, equipment list  
**Participants:** Project PM, Lead Engineers, Client Representative  
**Approval:** Conceptual approval to proceed

### 4.2 60% Design Review
**Timeline:** Month 4  
**Content:** Detailed specifications, P&IDs, equipment selections, cost estimates  
**Participants:** Full engineering team, Procurement, Project PM, Client  
**Approval:** Technical approval to proceed to detailed design

### 4.3 90% Design Review
**Timeline:** Month 5  
**Content:** Complete drawings, specifications, BOMs, construction methodology  
**Participants:** Full project team including QA, Safety, Construction  
**Approval:** Ready for client final review

### 4.4 Final Review (100%)
**Timeline:** Month 6  
**Content:** Completed deliverables, all comments resolved  
**Participants:** Client review, final sign-off  
**Approval:** Formal client acceptance, release to procurement/construction

---

## 5. Design Change Management

### 5.1 Engineering Change Order (ECO) Process
1. **Identify Change:** Engineering identifies need or client requests change
2. **Create ECO:** Document change description and justification
3. **Impact Analysis:** Analyze impact on scope, cost, schedule, quality
4. **Route for Approval:** Multiple levels based on impact
5. **Implement Change:** Update affected documents
6. **Communicate Changes:** Distribute to all affected parties
7. **Archive:** Maintain change history and audit trail

### 5.2 Change Categories
- **Clarification:** Technical query resolution, no scope change
- **Minor:** Drawing revisions, corrections, no schedule/cost impact
- **Moderate:** Changes affecting multiple areas, minor cost/schedule impact
- **Major:** Significant scope changes, major cost/schedule impact
- **Client Change:** Scope changes requested by client, via change orders

---

## 6. Technical Query Management (RFI/TQ)

### 6.1 Query Types
- **RFI (Request for Information):** Questions from contractor to client
- **TQ (Technical Query):** Questions between disciplines
- **Clarification:** Clarification needed from engineering documents
- **Deviation:** Request to deviate from original specification

### 6.2 Query Process
1. Submit query with context and question
2. Engineer researches and provides response
3. Route for approval if response requires changes
4. Document response and close query
5. Update relevant documents if needed
6. Maintain query log for project record

---

## 7. Design Team Organization

### 7.1 Team Structure
- **Lead Engineer:** Overall design responsibility, client interface
- **Senior Engineers:** Major system areas (mechanical, electrical, I&C)
- **Design Engineers:** Detailed design and drawing preparation
- **Junior Engineers:** Support, calculations, documentation
- **Quality Reviewer:** Design QA and compliance review
- **Drafter/CAD Technician:** CAD drawing support

### 7.2 Responsibilities
- **Lead Engineer:** Design strategy, approvals, client interface
- **System Engineers:** System integration, calculations, specifications
- **Design Engineers:** Detailed design, P&IDs, GA drawings
- **Junior Engineers:** Support calculations, standard specifications

---

## 8. Design Tools & Software

### 8.1 CAD & Design Tools
- **AutoCAD** or equivalent: P&IDs, GA drawings
- **PDMS** or **3D CAD:** 3D design and clash detection
- **Process Simulation:** Heat/mass balance calculations
- **Structural Analysis:** FEA for stress analysis
- **Electrical Design:** Electrical single line diagrams

### 8.2 Data Management
- **Central design repository:** All drawings and documents
- **Version control:** Track drawing revisions
- **BOM management:** Maintain material lists from CAD
- **Change tracking:** Audit trail of document changes

---

## 9. Design Compliance & Standards

### 9.1 Design Standards
- **ASME:** Equipment design standards (pressure vessels, piping)
- **API:** Petroleum industry standards
- **ANSI:** American National Standards
- **ISO:** International Standards
- **Client Standards:** Project-specific standards
- **Company Standards:** Best practices and standardized designs

### 9.2 Code Compliance
- **Pressure Equipment Directive (PED):** European compliance
- **NFPA:** Electrical codes and standards
- **Local Building Codes:** Project location requirements
- **Environmental Regulations:** Compliance with environmental standards

---

## 10. Design Phase Metrics

| Metric | Target | Unit |
|--------|--------|------|
| Design Schedule Performance | 100% | On-time |
| Design Quality | 95% | First-pass approval |
| RFI Response Time | <3 days | Business days |
| Design Review Cycle Time | <10 days | Days |
| Change Implementation | <5 days | Days |

---

## 📚 Related Documents

- [35_Frappe_App_Architecture.md](35_Frappe_App_Architecture.md) - Technical architecture
- [39_DocType_Field_Specification.md](39_DocType_Field_Specification.md) - Data structure
- [46_Form_Design.md](46_Form_Design.md) - UI for engineering forms

---

**Last Updated:** August 2026 | **Status:** Complete | **Audience:** Engineering Managers, Architects
