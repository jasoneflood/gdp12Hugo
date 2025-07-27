---
title: "DAM & Policy Creation"
weight: 1
---

# DAM & Policy Creation
Guardium 12.1 supports DAM for new platforms, including Amazon Redshift, RDS for SQL Server, OpenSearch, Percona MySQL, YugabyteDB, PostgreSQL 16, Neo4j 5.x, MongoDB 7.x, and more via updated Linux UNIX STAPs.

DAM supports both agent-based (STAPs) and agentless monitoring using connectors for cloud streams and database event streams. It supports real-time alerting and recording of database access across multiple deployment topologies (on premise, hybrid, cloud) 


## Classification & Sensitive Data Discovery
Guardium provides resource discovery and classification via regex‑based, exact match, and metadata scanning across structured and unstructured data. Classification Process Builder (Discover → Classifications → Classification Process Builder) allows defining policies to discover sensitive values (e.g. credit card regex), assign data sources and schedule executions 
guardiumnotes.

## Policy Creation & Management
Policy Builder (DAM Policy Setup)Policies are constructed in the Policy Builder interface, which organizes criteria into session-level, SQL-level, and other categories for clarity and ordering 
guardiumnotes. You define rules by selecting triggers such as activity type (e.g. SELECT, INSERT, DDL), user, object, time-of-day, IP, and sensitive columns. Guardium includes prebuilt compliance templates for PCI DSS, GDPR, HIPAA, SOX, CCPA that can be customized 

## Rule Logic & Order
Rules execute in specified order; you can copy, import, and reorder them to optimize policy performance and reduce false positives . Policy Analyzer (introduced in Guardium v11 and available in 12.1) provides visibility into which rules fired, which never fired, and helps tune heading level and ordering .

## Actions & Alerts
You configure real‑time alert actions for rules: logs, email, SNMP, or integration to SIEM/SOAR. You can designate alert receivers and roles; after saving, notifications can be configured. For advanced deployments, Guardium supports Advanced DAM packages that add blocking/masking capabilities for prevention—not just detection.

## Analytics, Outlier Mining & Exclusions
Active Threat Analytics and Outlier Mining detect anomalies and flag unusual behavior (e.g. off-hours access, massive queries) leveraging UEBA models. You can exclude known benign activity or sources (e.g. trusted applications, temp tables) from analytics mining. Exclusions can be time‑bound (future date ranges).

## Vulnerability & Configuration Assessment (VA, CAS, ER)
Guardium VA scans databases for missing patches, weak configurations, excessive privilege use, failed logins, and compliance against standards (e.g. CIS, DISA STIG). Configuration Audit System (CAS) tracks changes to OS or DB config files, environment variables, scripts etc.
Entitlement Reports (ER) aggregate user rights across databases to help enforce least privilege and access governance.

## Central Management & Deployment
You manage multiple Collectors from a centralized Central Manager, including policy distribution, agent management, compliance schedules, and reports.

Deployment can be done on-prem, containerized or cloud; S‑TAPs can be deployed via GIM or Kubernetes; advanced scaling with container orchestration supports elasticity.

## Best Practices & Policy Tuning
Start with prebuilt templates, customize for your compliance frameworks, and refine using Policy Analyzer to remove idle rules and reorder high-volume triggers.

Use outlier exclusions proactively to reduce noise—for example, exclude non-sensitive application queries or known batch jobs .

Integrate Guardium with SIEM/SOAR tools to create actionable workflows and rapid incident response.

| Feature         | Key Aspects in Guardium 12.1                        |
|----------------|------------------------------------|
| Supported Platforms	| Expanded support: Redshift, RDS, YugabyteDB, OpenSearch, etc. |
| DAM Policy Builder       | Session/SQL criteria views, rule ordering, prebuilt templates       |
| Classification        | Sensitive-data discovery via regex/exact/metadata scanning       |
| Analytics       | Active Threat / Outlier mining with UEBA, exclusion management       |
| Alerting & Prevention        | Real-time rules, blocking/masking with Advanced DAM       |
| Vulnerability & Config Assessment       | VA, CAS, Entitlement Reports included       |
| Central Management	        | Policy distribution and analytics from Central Manager     |

