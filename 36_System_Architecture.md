# 36. System Architecture

## Overview
High-level system architecture showing layers, components, and communication patterns.

## Architectural Layers

### Presentation Layer
- **Frontend:** Vue.js web application
- **Mobile Apps:** React Native or Flutter (optional)
- **Third-Party:** Vendor portal, client portal
- **Devices:** Field mobile apps, tablets, IoT sensors

### Application Layer
- **Frappe Framework:** Core application framework
- **EPC Custom App:** Business logic and workflows
- **Background Workers:** Celery for async processing
- **Message Queue:** Redis for event processing
- **API Gateway:** REST and GraphQL endpoints

### Business Logic Layer
- **DocType Methods:** Business rules in Python
- **Workflow Engine:** State machine implementation
- **Approval Engine:** Multi-level approvals
- **Integration Engine:** External system connections
- **Reporting Engine:** Report generation and analytics

### Data Layer
- **Relational Database:** MariaDB/PostgreSQL
- **Cache Layer:** Redis for frequently accessed data
- **Search Index:** Elasticsearch for full-text search
- **Archive Storage:** Long-term document storage
- **File Storage:** S3-compatible object storage

### Infrastructure Layer
- **Web Server:** Nginx reverse proxy
- **App Servers:** Gunicorn or uWSGI workers
- **Database Server:** MariaDB/PostgreSQL cluster
- **Cache Server:** Redis cluster
- **Search Server:** Elasticsearch cluster
- **Load Balancer:** Distribute requests across servers

## Communication Patterns

### Synchronous
- User → Web Browser → Nginx → Gunicorn → Database
- Response returned immediately

### Asynchronous
- User → Queue Message → Background Worker → Task Execution
- User notified via email/notification when complete

### Real-Time
- WebSocket connection for live updates
- Push notifications to connected clients
- Broadcast to multiple users

## Integration Points

### External Systems
- **Primavera P6:** Schedule synchronization
- **CAD Tools:** Design document integration
- **ERP Systems:** GL posting, cost data
- **Email:** SMTP for email notifications
- **Cloud Storage:** Document backup and sharing

## Scalability
- **Horizontal:** Add web/app servers for load
- **Vertical:** Increase server resources
- **Database:** Replication and read replicas
- **Cache:** Distributed cache across servers

## High Availability
- **Redundancy:** Multiple servers for each tier
- **Failover:** Automatic failover on server failure
- **Load Balancing:** Distribute load evenly
- **Data Replication:** Real-time DB replication
- **Monitoring:** 24/7 system monitoring

## Related Documents
[52_API_Design.md](52_API_Design.md) - API endpoints and integration
[65_Deployment_Architecture.md](65_Deployment_Architecture.md) - Deployment strategy
