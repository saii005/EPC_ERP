# 71. Performance Testing

## 1. Performance Objectives
Given that large-scale EPC projects involve tens of thousands of Work Breakdown Structure (WBS) nodes and extensive Bill of Materials (BOM) revisions, performance benchmarks are critical:
* **API Response Time:** < 200ms for standard resource queries; < 1.5s for complex Earned Value Management (EVM) rollups.
* **Concurrent Users:** Support for 500+ active field and office users simultaneously logging Daily Progress Reports (DPR).
* **Background Job Queuing:** Asynchronous processing of heavy reports and milestone billing calculations via Redis/Celery workers.

## 2. Testing Methodologies
* **Load Testing:** Simulating normal peak operational loads using tools like Locust or JMeter.
* **Stress Testing:** Pushing system limits to identify breaking points in database indexing and cache invalidation.