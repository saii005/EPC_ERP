# 48. Dashboard Design

## Overview
Dashboard design for executive, manager, and operational dashboards.

## Dashboard Types

### Executive Dashboard
- Portfolio KPIs (total projects, total value, profitability)
- Financial metrics (revenue, costs, margins)
- Risk summary (red, yellow, green status)
- Resource utilization (% billable)
- Alerts (escalations, critical issues)

### Project Dashboard
- Project status (schedule, cost, quality, HSE)
- WBS completion (% complete by phase)
- Budget tracking (actual vs. plan)
- Schedule tracking (actual vs. plan)
- Quality metrics (inspections complete %)
- Team list and roles
- Recent activities
- Documents list
- Upcoming milestones

### Operational Dashboard (Construction)
- Daily progress (hours, activities, materials)
- Work completed this week
- Crew utilization
- Equipment on-site
- Upcoming work
- Safety incidents this month
- Quality issues to address

## Dashboard Components

### KPI Cards
- Metric name, current value, trend
- Color-coded status (green, yellow, red)
- Drill-down link to details
- Variance from plan (actual vs. budget)

### Charts
- **Bar Chart:** Comparing values (budget vs. actual)
- **Line Chart:** Trends over time (cost curve, schedule progress)
- **Pie Chart:** Composition (% by type, by phase)
- **Gantt Chart:** Schedule with dependencies
- **Heat Map:** Status matrix (by phase, by vendor)

### Tables
- Recent transactions (invoices, POs, inspections)
- Top items (top vendors, top costs, top issues)
- Sorted and filterable

### Alerts
- Critical issues requiring attention
- Items past due date
- Non-conformances awaiting action
- Approvals pending

## Dashboard Customization
- Save personal dashboard views
- Rearrange widgets/components
- Select which metrics to display
- Define date ranges for filters
- Share custom dashboards with team

## Performance
- Load KPI data from cached summary tables
- Refresh dashboard every 5 minutes
- Pre-calculate trend calculations
- Lazy-load charts below fold

## Related Documents
[45_Page_and_Screen_Specification.md](45_Page_and_Screen_Specification.md) - Screen layouts
[48_Dashboard_Design.md](48_Dashboard_Design.md) - Detailed dashboard specs
