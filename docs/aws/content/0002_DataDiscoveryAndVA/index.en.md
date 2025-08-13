---
title: "Data Discovery and  VA"
weight: 2
---


## 1. Data Discovery & Classification (Discover and Classify)
Core Purpose: Establish visibility into where sensitive or regulated data resides—across structured databases and unstructured data (files, flat files, etc.) in on‑prem and cloud environments .

Supported Platforms: Covers major environments such as AWS RDS (MySQL, PostgreSQL, SQL Server, Oracle), MongoDB, IBM Db2 (Linux/UNIX/Windows, z/OS, i), Informix, SAP HANA, Teradata, Netezza, FTP/SMB/HTTP repositories, and more.

For full details follow this link: https://ibm.github.io/guardium-supported-datasources/

### 1.1 Classification Workflow:

* Use Guardium appliance to connect via JDBC to data sources
* Enumerate tables, views, synonyms
* Sample data and match against classification rules (regex, exact-match, metadata)
* Trigger rule-specific actions (e.g. tagging, alerts, reporting)
* Repeat across defined data sources 

### 1.2 Rule Builder Tools

* End-to-end wizard brings a simplified and quicker setup
* Full Classification Policy Builder gives increased flexibility. Helping to define sources, rules, scheduling, actions. 

### 1.3 Accuracy & Machine Learning: 
Guardium Discover and Classify delivers high accuracy on structured and unstructured data, often enhanced by AI/ML pattern detection.

### 1.4 Deliverables:

* Inventory of sensitive columns/tables/files and locations
* Input into activity monitoring, generating sensitive‑object lists for DAM policies
* Classification reporting to support data governance and regulatory compliance 

## 2. Vulnerability Assessment (Guardium VA)
* Overview: Designed to assess security posture of data environments by identifying infrastructure and configuration vulnerabilities, and guiding remediation efforts 
* Deployment Options: Available as part of Guardium Data Protection suite or as a standalone module for purely infrastructure scanning use cases 
* Key Capabilities:  
  ** Scans databases, data warehouses and big‑data environments.  
  ** Tests for weaknesses such as missing patches, weak credentials, excessive privileges, unauthorized schema changes, and behavioral anomalies (e.g. unusual logins, account sharing)   
  ** Relies on benchmarks such as CIS, STIG, SCAP, and IBM-maintained rule sets   
  ** Supports behavior-based indicators (e.g. after‑hours activity, privilege anomalies)   
  ** Broader platform support   
  ** UI and performance improvements, expanded CIS/STIG coverage and improved scalability   
  ** Credentialed, read-only scans (minimal load on systems)  
  ** Produce detailed reports: risk scores, benchmark violations, remediation steps  
  ** Provide dashboards tracking risk posture.  
  ** Automate compliance reporting for standards like PCI DSS, HIPAA, SOX   

### 2.1 Synergy Between Discovery & VA
Guardium Discover and Classify equips VA with precise knowledge of where sensitive data resides, allowing prioritized vulnerability scanning on high-risk assets.

Combined, they support risk-based prioritization: vulnerabilities tied to sensitive data surfaced first, guiding effective remediation.

### 2.2 Best Practices

| Aspect         | Recommendation                        |
|:----------------|:-----------------------------------|
| Discovery-first            | Always scan and classify before vulnerability assessment—know what data exists and where            |
| Rule Management	        | Use well-defined regex or metadata-based rules; re-evaluate periodically for false positives        |
| Credentials       | Use least-privilege non-admin credentials for classification and VA to limit exposure    |
| Scan Frequency	            | Schedule discovery and VA regularly; use ad-hoc scans after changes (e.g. new DB rollout or patch)            |
| Benchmark Currency        | Keep DPS patches and benchmark definitions updated before each VA run        |
| Integration       | Leverage ServiceNow, SIEM, ITSM tools for automated ticketing and remediation workflows    |
| Governance Alignment            | Feed classification outputs into data governance and compliance frameworks (e.g. Collibra, Purview)           |

### 2.3 Why It Matters

* Foundation for Data Governance: Classification supplies actionable inventory of sensitive data—essential for risk-based controls.

* Proactive Risk Identification: VA spots vulnerabilities before they’re exploited—especially in high-risk data assets.

* Compliance Support: Automatically supports audit evidence for GDPR, HIPAA, PCI, SOX, and other regulatory standards.

* Operational Efficiency: Integrated dashboards and automated remediation guidance reduce manual effort.

### 2.4 Community Insights
In practice, Guardium VA is widely acknowledged to apply to data-layer infrastructure—it doesn’t target broader system assets (like middleware or endpoints) unless integrated with tools like QRadar for extended coverage  . Also, keep Guardium’s DPS patches updated to ensure your tests reflect the latest CVEs and benchmarks .

### 3. Workshop activities
* Guardium Discover & Classify: Automates sensitive data discovery across structured and unstructured sources, enabling accurate classification with high ML-backed accuracy.

* Guardium Vulnerability Assessment: Scans databases/data warehouses for infrastructure and behavioral vulnerabilities, benchmarked against CIS/STIG and CVE standards.

* Together, they provide a robust, integrated data security posture management system—combining visibility, risk assessment, compliance, and actionable remediation.

* For the purpose of this workshop we will explore a small fraction of these capabilities. It is important however that you are aware of what can be done. This workshop will leave you with a working version of GDP for a period of time, so you can ofcourse continue to experiment with some self paced study into the above topics. 
