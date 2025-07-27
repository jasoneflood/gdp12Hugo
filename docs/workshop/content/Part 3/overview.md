---
title: "Data Discovery & VA"
weight: 1
---

## Data Discovery & Classification (Discover and Classify)
Core Purpose: Establish visibility into where sensitive or regulated data resides—across structured databases and unstructured data (files, flat files, etc.) in on‑prem and cloud environments .

Supported Platforms: Covers major environments such as AWS RDS (MySQL, PostgreSQL, SQL Server, Oracle), MongoDB, IBM Db2 (Linux/UNIX/Windows, z/OS, i), Informix, SAP HANA, Teradata, Netezza, FTP/SMB/HTTP repositories, and more.

### Classification Workflow:

* Use Guardium appliance to connect via JDBC to data sources
* Enumerate tables, views, synonyms
* Sample data and match against classification rules (regex, exact-match, metadata)
* Trigger rule-specific actions (e.g. tagging, alerts, reporting)
* Repeat across defined data sources 

### Rule Builder Tools: Use either:

* End-to-end wizard (simplified, quicker setup)
* Full Classification Policy Builder (max flexibility: define sources, rules, scheduling, actions) 

### Accuracy & Machine Learning: 
Guardium Discover and Classify delivers ~98.6% accuracy on structured data and ~100% on unstructured, often enhanced by AI/ML pattern detection .

### Deliverables:

* Inventory of sensitive columns/tables/files and locations
* Input into activity monitoring, generating sensitive‑object lists for DAM policies
* Classification reporting to support data governance and regulatory compliance 

## Vulnerability Assessment (Guardium VA)
* Overview: Designed to assess security posture of data environments by identifying infrastructure and configuration vulnerabilities, and guiding remediation efforts 
* Deployment Options: Available as part of Guardium Data Protection suite or as a standalone module for purely infrastructure scanning use cases 
* Key Capabilities:
** Scans databases, data warehouses, big‑data environments (on-prem and cloud)
** Tests for weaknesses: missing patches, weak credentials, excessive privileges, unauthorized schema changes, and behavioral anomalies (e.g. unusual logins, account sharing) 
** Relies on benchmarks such as CIS, STIG, SCAP, and IBM-maintained rule sets 
** Supports behavior-based indicators (e.g. after‑hours activity, privilege anomalies) 

* Recent Enhancements (late 2024 / early 2025):
** Broader platform support: YugabyteDB 2.21, Neo4j 5.24, IBM Db2 13 for z/OS with CIS benchmarking, plus Oracle, Percona MySQL, Apache Cassandra, Postgres 15 etc. 
** Deeper ServiceNow integration enabling on‑demand rescans from ServiceNow UI 
** UI and performance improvements, expanded CIS/STIG coverage, improved scalability 

* Workflow:
** Credentialed, read-only scans (minimal load on systems)
** Produce detailed reports: risk scores, benchmark violations, remediation steps
** Provide dashboards tracking risk posture over time
** Automate compliance reporting for standards like PCI DSS, HIPAA, SOX 

## Synergy Between Discovery & VA
Guardium Discover and Classify equips VA with precise knowledge of where sensitive data resides, allowing prioritized vulnerability scanning on high-risk assets.

Combined, they support risk-based prioritization: vulnerabilities tied to sensitive data surfaced first, guiding effective remediation.

## Best Practices

| Aspect         | Recommendation                        |
|:----------------|:-----------------------------------|
| Discovery-first            | Always scan and classify before vulnerability assessment—know what data exists and where            |
| Rule Management	        | Use well-defined regex or metadata-based rules; re-evaluate periodically for false positives        |
| Credentials       | Use least-privilege non-admin credentials for classification and VA to limit exposure    |
| Scan Frequency	            | Schedule discovery and VA regularly; use ad-hoc scans after changes (e.g. new DB rollout or patch)            |
| Benchmark Currency        | Keep DPS patches and benchmark definitions updated before each VA run        |
| Integration       | Leverage ServiceNow, SIEM, ITSM tools for automated ticketing and remediation workflows    |
| Governance Alignment            | Feed classification outputs into data governance and compliance frameworks (e.g. Collibra, Purview)           |

	

	
	
	

## Why It Matters

* Foundation for Data Governance: Classification supplies actionable inventory of sensitive data—essential for risk-based controls.

* Proactive Risk Identification: VA spots vulnerabilities before they’re exploited—especially in high-risk data assets.

* Compliance Support: Automatically supports audit evidence for GDPR, HIPAA, PCI, SOX, and other regulatory standards.

* Operational Efficiency: Integrated dashboards and automated remediation guidance reduce manual effort.

## Community Insights
In practice, Guardium VA is widely acknowledged to apply to data-layer infrastructure—it doesn’t target broader system assets (like middleware or endpoints) unless integrated with tools like QRadar for extended coverage  . Also, keep Guardium’s DPS patches updated to ensure your tests reflect the latest CVEs and benchmarks .

## Summary
* Guardium Discover & Classify: Automates sensitive data discovery across structured and unstructured sources, enabling accurate classification with high ML-backed accuracy.

* Guardium Vulnerability Assessment: Scans databases/data warehouses for infrastructure and behavioral vulnerabilities, benchmarked against CIS/STIG and CVE standards.

* Together, they provide a robust, integrated data security posture management system—combining visibility, risk assessment, compliance, and actionable remediation.