# 35. Frappe App Architecture

## Overview
Frappe framework application architecture and custom EPC app structure.

## App Structure
```
epc_app/
├── epc_core/              # Main app folder
│   ├── public/            # Static files (CSS, JS, images)
│   ├── epc_core/
│   │   ├── doctype/       # Custom DocTypes
│   │   │   ├── engineering_deliverable/
│   │   │   ├── daily_progress_report/
│   │   │   ├── inspection_test_plan/
│   │   │   └── ncr/
│   │   ├── page/          # Custom Pages
│   │   ├── report/        # Custom Reports
│   │   ├── api.py         # Custom API methods
│   │   ├── hooks.py       # App hooks and permissions
│   │   └── __init__.py
│   ├── fixtures/          # Initial data
│   └── setup.py           # Package configuration
```

## Key Components

### DocTypes (Custom Data Models)
- Define using JSON schema
- Fields with types (Link, Table, String, Float, etc.)
- Validations and calculated fields
- Methods for custom business logic
- Permissions and sharing rules

### Pages (UI Components)
- Single Page Applications (SPAs)
- Vue.js based interface
- Real-time updates via WebSockets
- Responsive design for mobile

### Reports
- Report Builder for ad-hoc reports
- Query Report for SQL-based reports
- Dashboard tiles for KPI visualization
- Export to PDF, Excel, CSV

### API Methods
- Python methods exposed as REST endpoints
- Input validation and error handling
- Permission checks
- Database transaction management

### Workflows
- Approval workflows with state machine
- Automatic email notifications
- Workflow transitions based on approvals
- Audit trail of all transitions

## Technology Stack
- **Backend:** Python 3.10+, Frappe Framework
- **Frontend:** Vue.js, Frappe UI components, Bootstrap
- **Database:** MariaDB/PostgreSQL
- **Cache:** Redis
- **Queue:** Celery/Redis for background jobs
- **Search:** Elasticsearch (optional)

## Security
- Role-based access control (RBAC)
- Field-level security
- Audit logging
- Encrypted passwords
- CSRF protection

## Performance
- Database indexes on key fields
- Query optimization
- Caching strategy
- Lazy loading of data
- Pagination for large result sets

## Related Documents
[36_System_Architecture.md](36_System_Architecture.md) - High-level system architecture
