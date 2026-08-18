# 51. Backend Interface Specification

## Overview
This document specifies the backend interfaces, including Python methods, Frappe hooks, and background tasks required for the EPC ERP system.

## Key Interface Components

### API Controllers
- **`epc_core.api.get_project_summary`**: Retrieves high-level project KPIs and dashboard metrics.
- **`epc_core.api.submit_dpr`**: Endpoint for submitting Daily Progress Reports from mobile field devices.
- **`epc_core.api.trigger_ncr_workflow`**: Handles NCR initiation and status transitions.
- **`epc_core.api.calculate_earned_value`**: Trigger for automated EVM data processing.

### Hooks & Events
- **`on_submit` (PO):** Triggers vendor notification emails.
- **`before_save` (Deliverable):** Validates specification compliance.
- **`on_update` (Material Receipt):** Triggers warehouse and finance stock updates.
- **`cron` (Nightly):** Triggers project status snapshots and report generation.

### Background Workers
- **`epc_core.tasks.send_reminders`**: Daily task for approaching deadlines.
- **`epc_core.tasks.generate_reports`**: Asynchronous report generation for large data sets.
- **`epc_core.tasks.sync_primavera`**: Periodically syncs schedule data from external sources.

## Data Validation
- All inputs are validated against schema definitions.
- Mandatory field checks are enforced in the API layer.
- Authorization checks are performed on every API request.
