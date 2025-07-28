---
title: "Integrations & Automation"
weight: 1
---

Here’s a detailed overview of Integrations and Automation in IBM Security Guardium 12.1, focusing on how Guardium connects with other tools, and how you can streamline workflows using built-in or external automation.

## Guardium Integrations
Guardium integrates with a wide range of enterprise security, operations, and governance platforms to centralize and extend data security operations.

### Core Integration Types

| Feature         | Description                        |
|:----------------|:-----------------------------------|
|SIEM (e.g., QRadar)	|Send real-time policy violations, VA findings, and audit data via syslog|
|ITSM (e.g., ServiceNow)|	Open, update, and close tickets based on alerts or VA results|
|IAM (e.g., LDAP/AD)|	Sync users/groups for access control and reporting|
|Data Governance (e.g., Collibra, WKC)|	Share classification/tagging insights with governance catalogs|
|Data Lakes & Analytics (e.g., Splunk, ELK)|	Export logs for long-term storage or advanced analytics|
|Cloud Monitoring (e.g., AWS CloudTrail, Azure Monitor)|	Correlate Guardium findings with cloud-native logs|

### Integration with IBM Ecosystem
* IBM QRadar SIEM
Guardium can:
** Send real-time alerts via syslog
** Share vulnerability scan results and classifications
** Enrich QRadar offenses with data-risk context

* IBM Security Verify / ISIM
Can link user access provisioning/de-provisioning workflows to policy enforcement in Guardium.

* IBM Security Guardium Insights
** Cloud-native companion product
** Collects long-term Guardium logs for scalable analytics, policy management, and regulatory reporting

* Watson Knowledge Catalog (WKC)
** Share sensitive data findings for enterprise governance
** Enables central lineage, data quality, and compliance mapping

### External API Integrations
Guardium provides REST APIs and CLI interfaces for automating:

* Policy install/update
* Data classification scans
* VA scans and exports
* User creation and access role updates
* Report generation and download

Full API docs are accessible via:
https://<your-guardium-ip>/api-docs
## Guardium Automation Features


| Feature         | Description                        |
|:----------------|:-----------------------------------|
|Scheduler	|Run scans, install policies, export reports at defined intervals|
|Email Alerts|	Trigger emails for policy violations or scan failures|
|Syslog Forwarding|	Send events to SIEM or log collector in real time|
|Ticketing (ServiceNow)|	Create tickets from policy alerts or VA issues, then track remediation|
|Anomaly Detection|	Automatically detect behavioral anomalies (e.g. off-hours access)|
|Audit Process Automation|	Use pre-built compliance workflows (e.g., PCI, GDPR) for faster reporting|

## Integration with External Automation Tools
* Ansible / Terraform
Automate provisioning of Guardium agents, config files, and integration endpoints.

* Jenkins / CI/CD Pipelines
Trigger Guardium scans or data masking tasks post-deployment.

* ServiceNow Integration

** Guardium VA creates vulnerabilities in ServiceNow 
** Security teams can resolve and trigger Guardium to rescan
** Enables closed-loop remediation

* SOAR (e.g., IBM SOAR, Splunk Phantom)

** Use Guardium alerts as incident triggers
** Automate threat enrichment and response actions

## Real-World Automation Examples

| Scenario         | Automation Outcome                        |
|:----------------|:-----------------------------------|
|New database goes live	|Terraform script registers it with Guardium, schedules discovery + VA|
|Policy violation (PHI access)	|Guardium sends alert to QRadar → triggers SOAR playbook → notify SecOps|
|Vulnerability found in Oracle server|	Ticket created in ServiceNow → VA rescans after patch → ticket auto-closes|
|User removed from AD group|	Guardium auto-updates role access and disables monitoring for that user|

## Security of Integrations
* Supports TLS encryption, mutual authentication, API keys, and role-based access control for all integration points.
* All API activity is logged and auditable via standard Guardium audit trails.

## Best Practices
| Area         | tip                      |
|:----------------|:-----------------------------------|
|Centralize Alerts|	Forward all real-time alerts to a SIEM like QRadar for incident correlation|
|Automate Discovery|	Use scheduler or CI/CD triggers to classify data with every DB or schema change|
|Policy Deployment|	Automate policy install via CLI/API after rules change or patch deployment|
|SOAR Readiness|	Normalize alert formats and ensure metadata tagging for downstream enrichment|
|Security Review|	Regularly audit API keys and credentials used in automation pipelines|

## Summary
* Integrations connect Guardium to SIEMs, SOAR, ITSM, IAM, and governance tools for full-stack visibility and response.
* Automation features help you classify, assess, alert, and report with minimal human effort—crucial for large-scale compliance.
* Guardium supports REST APIs, CLI, scheduler, and ServiceNow workflows for flexible orchestration across your SecOps and DevOps pipelines.