# 33. ERPNext Standard Module Mapping

## Overview
Mapping of EPC business domains to ERPNext standard modules and customizations needed.

## Module Mapping

| Business Domain | ERPNext Module | Customizations |
|-----------------|----------------|-----------------|
| **Project** | Projects | Add EPC-specific fields (WBS, phase) |
| **Engineering** | Quality, Document Mgmt | Create Engineering Deliverable DocType |
| **Procurement** | Buying | Extend with RFQ evaluation |
| **Vendors** | Buying | Extend with scorecard tracking |
| **Materials** | Stock | Add material traceability fields |
| **Construction** | Projects, HR | Add daily progress & labor tracking |
| **Quality** | Quality | Extend with ITP and inspection tracking |
| **HSE** | HR | Add HSE incident tracking |
| **Finance** | Accounting | Extend with project-specific GL posting |
| **HR** | HR | Extend with skills and utilization |

## ERPNext Modules Used
- **Projects:** Project management, task tracking
- **Buying:** Vendor management, purchase orders
- **Stock:** Material management, inventory
- **Quality:** Quality inspections and testing
- **Accounting:** General ledger, invoicing
- **HR:** Employee management, training
- **Utilities:** Document management, workflow

## Customizations Required
- Custom DocTypes for EPC-specific entities
- Custom fields on standard DocTypes
- Custom workflows and approvals
- Custom reports and dashboards
- API customizations for integrations
- Automated workflows using Frappe methods

## Related Documents
[34_ERPNext_Customization_Strategy.md](34_ERPNext_Customization_Strategy.md) - Detailed customization
