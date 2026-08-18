# 52. API Design

## Overview
Design for REST and GraphQL APIs to support third-party integrations (P6, BIM, IoT).

## REST Endpoints
- `POST /api/method/epc_core.api.update_progress`: Updates WBS item progress from mobile devices.
- `GET /api/resource/Deliverable`: Retrieves status and version information.
- `POST /api/method/epc_core.api.submit_invoice`: Facilitates automated invoice submissions.

## GraphQL Schemas
- **ProjectQuery**: Query project progress, costs, and deliverables.
- **MaterialQuery**: Query material stock levels and location.

## Security
- API Key + Secret authentication.
- OAuth2 support for client integrations.
- Rate limiting to prevent abuse.
