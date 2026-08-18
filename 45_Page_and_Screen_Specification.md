# 45. Page and Screen Specification

## Overview
Detailed specifications for key pages and screens in the system.

## Dashboard Screens

### Project Dashboard
- Project status (on-track, at risk, delayed)
- Key metrics (budget, schedule, quality, HSE)
- Recent activities
- Upcoming milestones
- Quick actions (update progress, create order, etc.)

### Executive Dashboard
- Portfolio view (all projects)
- Financial summary (total cost, profitability)
- Resource utilization
- Risk register highlights
- Alerts and escalations

### Quality Dashboard
- Inspection completion % (vs. plan)
- Defect trends (by type, severity)
- Non-conformance status
- Quality metrics
- Vendor quality ratings

## Detail Screens

### Project Details
- Project information tab
- WBS hierarchy tree view
- Schedule Gantt chart
- Budget vs. actual bar chart
- Team member list
- Recent documents

### Purchase Order Details
- PO header (vendor, amount, date)
- Line items table
- Delivery status
- 3-way match status
- Attached documents
- Payment status

### Daily Progress Report
- Report summary
- Activities completed (expandable)
- Labor hours table
- Material consumption table
- Photos/attachments
- Comments section

## List Screens

### Projects List
- Columns: Project ID, Name, Status, %Complete, Manager
- Filters: By status, manager, date range
- Sorting: By name, date, status
- Actions: Create new, view details, edit, delete

### Purchase Orders List
- Columns: PO#, Vendor, Amount, Delivery Date, Status
- Filters: By vendor, status, date range, amount
- Sorting: By date, amount, vendor
- Actions: Create, view, amend, receive

### Inspections List
- Columns: Inspection#, Activity, Inspector, Date, Status
- Filters: By activity, status, date range
- Sorting: By date, status
- Actions: Perform inspection, view results

## Form Screens

### Requisition Form
- Basic Info section: Item, quantity, needed date
- Attachment section: Drawings, specifications
- Approval workflow: Show approval status
- Save/Submit/Reject buttons

### RFQ Form
- Header: RFQ#, vendors to quote
- Items section: Table of items, specs
- Terms section: Payment, delivery, quality
- Upload section: Attachments
- Distribution section: Track responses

## Report Screens

### Cost Report
- Filter by: Project, cost type, period
- Table: Description, budget, actual, variance, %
- Chart: Budget vs. actual trend
- Summary: Total variance, forecast

### Schedule Report
- Gantt chart: Activities, dates, dependencies
- Filter: By phase, status, date range
- Table: Activity, planned, actual, variance, %complete
- Critical path highlighted

## Related Documents
[46_Form_Design.md](46_Form_Design.md) - Form field specifications
[47_List_View_Design.md](47_List_View_Design.md) - List view specifications
