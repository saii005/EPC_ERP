# 34. ERPNext Customization Strategy

## Overview
Strategy for extending ERPNext to support EPC-specific business requirements.

## Custom DocTypes to Create
- **Engineering Deliverable:** Specifications, drawings, BOMs
- **Daily Progress Report:** Construction daily progress tracking
- **Inspection & Test Plan:** Quality inspection planning
- **Non-Conformance Report (NCR):** Quality issue management
- **HSE Incident:** Safety incident tracking
- **Vendor Scorecard:** Vendor performance tracking
- **Master Deliverable Register:** Engineering deliverable registry

## Standard DocType Extensions
- **Purchase Order:** Add EPC-specific fields (expediting, inspection)
- **Project:** Add WBS, phase, earned value fields
- **Stock:** Add material traceability (serial, batch, heat number)
- **Quality Inspection:** Extend for EPC inspection types
- **Journal Entry:** Extend for project cost allocation

## Custom Fields
- Project: phase, WBS code, earned value data
- PO: expediting status, long-lead flag
- Stock: traceability fields, warehouse location
- Employee: skills, certifications, project assignments

## Workflow Customizations
- Engineering deliverable approval workflow
- Purchase order approval based on amount
- Invoice 3-way match workflow
- NCR investigation and closure workflow
- HSE incident investigation workflow

## Report Customizations
- Project status dashboard
- Cost and schedule performance reports
- Vendor scorecards
- Quality trend reports
- HSE metrics reports
- Material traceability reports

## API Customizations
- API for daily progress updates from field
- API for material receipt and issue
- API for inspection data entry
- API for cost/schedule actuals
- Webhook triggers for approvals

## Integration Points
- **Primavera P6:** Schedule import/export
- **BIM 360:** Document and collaboration integration
- **SAP/Oracle:** GL posting integration
- **IoT Sensors:** Real-time site data collection

## Related Documents
[35_Frappe_App_Architecture.md](35_Frappe_App_Architecture.md) - Technical architecture
