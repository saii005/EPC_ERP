# 31. Database Design

## Overview
Physical database design specifying tables, columns, indexes, and optimization strategies.

## Design Principles
- **Normalization:** 3NF (Third Normal Form) to reduce redundancy
- **Performance:** Indexes on frequently queried columns
- **Scalability:** Partition large tables by date
- **Archival:** Archive old data to maintain performance
- **Backup:** Daily backups with redundancy

## Database Technology
- **Primary DB:** MariaDB 10.6+ or PostgreSQL 13+
- **Caching:** Redis for frequently accessed data
- **Search:** Elasticsearch for full-text search on documents
- **Data Warehouse:** Separate analytics database for reporting

## Table Sizing
- Projects table: ~1000 rows
- WBS Items: ~100,000 rows
- Materials: ~50,000 rows
- Purchase Orders: ~20,000 rows
- Daily Progress Reports: ~1,000,000 rows
- Transactions: ~10,000,000+ rows

## Partitioning Strategy
- Projects: No partitioning
- Daily Progress Reports: Partition by date
- Transactions: Partition by date
- Archive: Move completed projects to archive DB

## Indexing
- Primary key indexes (automatic)
- Foreign key indexes
- Search indexes (Project ID, PO #, Material ID)
- Date indexes for time-based queries
- Composite indexes for common join queries

## Performance Targets
- Row insertion: <100ms
- Query response: <2 seconds
- Report generation: <30 seconds
- Concurrent users: 500+

## Backup Strategy
- Daily full backups
- Hourly incremental backups
- 30-day retention of daily backups
- 12-month retention of monthly backups
- Test restores monthly

## Related Documents
[32_Relational_DB_Schema.md](32_Relational_DB_Schema.md) - Detailed schema
