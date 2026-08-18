# 46. Form Design

## Overview
Form design specifications including field layout, validation, and interactions.

## Form Design Principles
- **Grouping:** Organize fields logically in sections
- **Labels:** Clear, concise labels above fields
- **Validation:** Real-time and on-submit validation
- **Errors:** Clear error messages, highlight problematic fields
- **Help:** Contextual help text and tooltips
- **Progressive Disclosure:** Show only relevant fields
- **Consistency:** Consistent field styles and layouts

## Common Field Types
- **Text Input:** Single-line text (name, description)
- **Text Area:** Multi-line text (comments, notes)
- **Number:** Numeric input (quantities, prices)
- **Currency:** Formatted currency input
- **Date:** Date picker
- **Select:** Dropdown list (status, type)
- **Checkbox:** True/false (yes/no options)
- **Link:** Reference to another DocType
- **Table:** Child rows with multiple fields
- **Attachment:** File upload
- **Read-only:** Display-only fields

## Form Sections
- **Basic Info:** Primary identifying information
- **Details:** Detailed data specific to type
- **Relationships:** Links to related documents
- **Attachments:** Supporting documents/files
- **History:** Read-only history/audit trail
- **Approval:** Approval workflow status (if applicable)
- **Metadata:** Created by, date, modified by, date

## Form Actions
- **Save:** Save draft without submitting
- **Submit:** Finalize and lock document
- **Amend:** Modify submitted document
- **Cancel:** Reverse submitted document
- **Print:** Generate printable version
- **Email:** Send via email
- **Delete:** Remove document (if draft)

## Validation Rules
- Required fields marked with asterisk (*)
- Format validation (email, phone, currency)
- Business rule validation (e.g., end date > start date)
- Cross-field validation (e.g., total = sum of items)
- Real-time validation feedback

## Mobile Form Considerations
- Single column layout (not side-by-side)
- Larger touch targets (min 44px height)
- Keyboard-friendly input order
- Minimal horizontal scrolling
- Simplified tables (key columns only)

## Related Documents
[45_Page_and_Screen_Specification.md](45_Page_and_Screen_Specification.md) - Screen layouts
[48_Dashboard_Design.md](48_Dashboard_Design.md) - Dashboard specifications
