# 56. Audit Log and Traceability Design

## Overview
Design for full audit logging of data changes, approvals, and system events.

## Audit Log Entries
- **Who:** User ID
- **What:** Event type, DocType, record ID
- **When:** Timestamp
- **Where:** IP Address, Device
- **Changes:** Before and after values

## Traceability
- **DocTrace:** Engineering deliverables linked to vendor/contract/materials.
- **Financial Traceability:** PO → Receipt → Invoice → GL Entry.
- **Inspection Traceability:** Activity → ITP → Inspection → NCR → Correction → Sign-off.
