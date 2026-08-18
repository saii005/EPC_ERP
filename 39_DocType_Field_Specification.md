# 39. DocType Field Specification

## Overview
Detailed specification of fields for all custom EPC DocTypes.

## Engineering Deliverable DocType

```
name: Engineering Deliverable
Fields:
├── Basic Info
│   ├── deliverable_id (String, unique)
│   ├── title (String, required)
│   ├── description (Text)
│   ├── deliverable_type (Select: Specification/Drawing/BOM/Calculation)
│   ├── discipline (Select: Mechanical/Electrical/Process/I&C)
│
├── Ownership
│   ├── project (Link to Project)
│   ├── owner (Link to Employee)
│   ├── qc_reviewer (Link to Employee)
│   ├── client_reviewer (Link to Employee)
│
├── Status
│   ├── status (Select: Draft/IFR/IFA/IFC/Closed)
│   ├── version (String)
│   ├── release_date (Date)
│   ├── supersedes (Link to Deliverable - optional)
│
├── Reviews
│   ├── reviews (Table - Review Cycle)
│   │   ├── review_stage (Select: IFR/IFA/IFC)
│   │   ├── reviewer (Link)
│   │   ├── review_date (Date)
│   │   ├── status (Select: Approved/Pending/Rejected)
│   │   └── comments (Text)
│
├── Attachments
│   ├── main_document (Attach)
│   ├── related_documents (Table)
│   │   ├── document_title (String)
│   │   ├── document_file (Attach)
│   │   └── document_type (Select)
│
└── Metadata
    ├── created_by (Link to User, auto)
    ├── created_date (DateTime, auto)
    ├── modified_by (Link to User, auto)
    └── modified_date (DateTime, auto)
```

## Daily Progress Report DocType
```
name: Daily Progress Report
Fields:
├── Report Date
│   ├── report_date (Date, required)
│   ├── project (Link to Project)
│   ├── location (String)
│
├── Work Summary
│   ├── activities (Table)
│   │   ├── activity (Link to WBS Item)
│   │   ├── description (Text)
│   │   ├── % complete (Float)
│   │   └── actual_hours (Float)
│
├── Resources
│   ├── crew_size (Integer)
│   ├── total_hours (Float, auto calculated)
│   ├── equipment (Table)
│   │   ├── equipment_type (String)
│   │   └── hours_used (Float)
│
├── Materials
│   ├── materials_received (Table)
│   │   ├── material (Link)
│   │   ├── quantity (Float)
│   │   └── location (String)
│   ├── materials_used (Table)
│   │   ├── material (Link)
│   │   └── quantity_used (Float)
│
├── Quality & Safety
│   ├── safety_incidents (Integer)
│   ├── near_misses (Integer)
│   ├── inspections_completed (Table)
│   │   ├── inspection_type (String)
│   │   └── result (Select: Pass/Fail)
│
├── Issues & Changes
│   ├── issues (Text)
│   ├── delays (Text)
│   ├── change_requests (Table)
│   │   ├── change_description (Text)
│   │   └── impact (Text)
│
├── Photos
│   ├── photos (Table)
│   │   ├── photo (Attach)
│   │   └── description (String)
│
└── Approval
    ├── status (Select: Draft/Submitted)
    ├── submitted_by (Link to Employee)
    ├── reviewed_by (Link to Employee)
    └── reviewed_date (Date)
```

## Inspection & Test Plan DocType
```
name: Inspection & Test Plan (ITP)
Fields:
├── Plan Information
│   ├── itp_number (String, unique)
│   ├── project (Link to Project)
│   ├── created_date (Date)
│
├── Scope
│   ├── description (Text)
│   ├── specification_reference (Link to Deliverable)
│   ├── applicable_standards (Table)
│   │   ├── standard (String)
│   │   └── requirement (Text)
│
├── Inspection Points (Table)
│   ├── hold_point_number (Integer)
│   ├── description (String)
│   ├── activity_trigger (String)
│   ├── acceptance_criteria (Text)
│   ├── sampling_plan (String)
│   ├── witness_required (Checkbox)
│   ├── assigned_inspector (Link to Employee)
│   └── estimated_date (Date)
│
├── Status
│   ├── status (Select: Draft/Active/Completed)
│   ├── approval_status (Link to Approver)
│   └── approved_date (Date)
│
└── Execution Tracking
    ├── execution_records (Table - ReadOnly)
    │   ├── hold_point_number (Integer)
    │   ├── inspection_date (Date)
    │   ├── inspector (Link)
    │   ├── result (Select: Pass/Fail/Conditional)
    │   ├── findings (Text)
    │   └── certificate_link (Link to Certificate)
```

## Non-Conformance Report (NCR) DocType
```
name: Non-Conformance Report
Fields:
├── Basic Info
│   ├── ncr_number (String, auto)
│   ├── project (Link to Project)
│   ├── discovery_date (Date)
│   ├── discovered_by (Link to Employee)
│
├── Defect Details
│   ├── activity (Link to WBS Item)
│   ├── description (Text)
│   ├── severity (Select: Critical/Major/Minor)
│   ├── specification_reference (Link)
│   ├── non_conformance_type (Select: Quality/HSE/Schedule/Cost)
│
├── Investigation
│   ├── root_cause (Text)
│   ├── investigation_date (Date)
│   ├── investigated_by (Link to Employee)
│   ├── immediate_action (Text)
│
├── Corrective Action
│   ├── corrective_actions (Table)
│   │   ├── action_description (Text)
│   │   ├── owner (Link to Employee)
│   │   ├── target_date (Date)
│   │   ├── actual_date (Date)
│   │   └── status (Select: Open/Completed)
│
├── Verification
│   ├── verification_method (Text)
│   ├── verification_date (Date)
│   ├── verified_by (Link to Employee)
│   └── verification_result (Select: Accepted/Rejected)
│
└── Status
    └── ncr_status (Select: Open/Closed/Re-opened)
```

## Related Documents
[38_DocType_Architecture.md](38_DocType_Architecture.md) - DocType design patterns
