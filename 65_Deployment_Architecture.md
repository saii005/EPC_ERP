# 65. Deployment Architecture

## Overview
Architecture for deploying the system using Docker, Kubernetes, Nginx, and Gunicorn.

## Stack Components
- **Nginx:** Reverse proxy, load balancer, and SSL termination.
- **Gunicorn:** Application server running Frappe workers.
- **Docker:** Containerized runtime for application, workers, and scheduler.
- **Kubernetes:** Orchestrates services, manages replicas, scaling, and self-healing.
- **NFS/Shared Vol:** Storage for uploaded attachments across replicas.
