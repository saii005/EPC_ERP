# 49. Report Design

## Overview
Report design covering standard reports, custom reports, and export formats.

## Standard Reports

### Financial Reports
- **Project Profitability:** Budget vs. Actual, Variance, CPI
- **Cost Summary:** By category, by phase, by vendor
- **Cash Flow:** Monthly cash inflows/outflows
- **Aged Receivables:** Invoice aging, collections status

### Operational Reports
- **Project Status:** Schedule, cost, quality, HSE status
- **Weekly Timesheet:** Labor hours by project/activity
- **Material Movement:** Receipts, issues, on-hand inventory
- **Daily Progress Summary:** Cumulative weekly progress

### Quality Reports
- **Inspection Summary:** Completed vs. planned, pass rate
- **NCR Aging:** Open NCRs, age, assigned to
- **Quality Trend:** Defects by type, by phase, trending
- **Vendor Quality:** Quality rating by vendor

### HSE Reports
- **Incident Log:** All incidents, types, severity
- **Hazard Register:** Identified hazards, control measures
- **Training Record:** Training completed, due for renewal
- **HSE Metrics:** Lost-time incidents, near-misses rate

### Vendor Reports
- **Vendor Scorecard:** Monthly performance by vendor
- **PO Summary:** Open, closed, in-transit POs
- **Delivery Performance:** On-time %, late deliveries
- **Quality by Vendor:** Quality ratings, NCRs

## Report Features
- **Filters:** Date range, project, vendor, status, etc.
- **Grouping:** Group by category, phase, vendor
- **Sorting:** Sort by column ascending/descending
- **Subtotals:** Sub-group totals and grand total
- **Charts:** Visual representation of data
- **Export:** PDF, Excel, CSV formats
- **Schedule:** Auto-generate and email daily/weekly/monthly

## Custom Reports
- **Report Builder:** Drag-drop fields for custom reports
- **Query Reports:** SQL-based ad-hoc reports
- **Pivot Tables:** Cross-tabulation analysis
- **Dashboards:** Combine multiple reports

## Report Distribution
- **Email:** Auto-send to recipients on schedule
- **Portal:** Access via web dashboard
- **Mobile:** View on mobile devices
- **Alerts:** Notify when thresholds exceeded

## Report Performance
- Pre-calculate summary tables nightly
- Cache report results for 1 hour
- Optimize report queries with indexes
- Archive old report data annually

## Related Documents
[48_Dashboard_Design.md](48_Dashboard_Design.md) - Dashboard specifications
[49_Report_Design.md](49_Report_Design.md) - Report definitions
