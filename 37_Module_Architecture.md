# 37. Module Architecture

## Overview
Module-level architecture showing how different functional modules are organized and integrate.

## Core Modules

### EPC Core Module
- Base module with common utilities
- Shared data models and fields
- Common API methods
- Shared workflows

### Project Module
- Project master data management
- WBS hierarchy management
- Budget and cost tracking
- Schedule management

### Engineering Module
- Engineering deliverables (specs, drawings)
- Design review workflows
- Technical query management
- Change order management

### Procurement Module
- Vendor management and qualification
- Requisition and RFQ management
- Purchase order lifecycle
- Bid evaluation

### Materials Module
- Material master data
- Warehouse operations
- Inventory tracking
- Material traceability

### Construction Module
- Daily progress reporting
- Labor and resource tracking
- Equipment management
- Site logistics

### Quality Module
- Inspection and Test Plans (ITP)
- Inspection execution and reporting
- Non-Conformance Reports (NCR)
- Quality metrics and trending

### HSE Module
- Incident reporting and investigation
- Training and certification tracking
- Audit management
- HSE metrics and reporting

### Finance Module
- Cost tracking and control
- Invoice and payment management
- General ledger integration
- Financial reporting

## Module Dependencies
```
EPC Core
├── Project Module
│   ├── Engineering Module
│   │   └── Procurement Module
│   │       └── Materials Module
│   ├── Construction Module
│   │   ├── Quality Module
│   │   ├── HSE Module
│   │   └── Materials Module
│   └── Finance Module
```

## Inter-Module Communication
- **Events:** DocType events (create, update, submit)
- **Methods:** Direct Python method calls
- **Webhooks:** HTTP callbacks between modules
- **Message Queue:** Asynchronous event processing

## Extensibility
- Plugin architecture for add-ons
- Custom fields for client-specific data
- Custom workflows for business logic
- Custom reports for analytics

## Related Documents
[38_DocType_Architecture.md](38_DocType_Architecture.md) - DocType design
