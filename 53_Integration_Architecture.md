# 53. Integration Architecture

## Overview
Integration strategy for external project systems (P6, BIM, SAP/ERP, IoT).

## Integration Types
- **Schedulers:** Primavera P6 (API-based sync)
- **CAD/BIM:** BIM 360 (Document link integration)
- **Finance/ERP:** SAP/Oracle (GL posting interface)
- **Logistics:** Transport service portals
- **IoT Sensors:** Site sensors (API/Webhook)

## Integration Patterns
- **Webhooks:** Push data changes immediately to external systems.
- **Scheduled Sync:** Pull data from external systems periodically.
- **Direct API:** Real-time communication for specific actions.
