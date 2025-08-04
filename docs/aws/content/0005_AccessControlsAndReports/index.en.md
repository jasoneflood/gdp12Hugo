---
title: "Access Controls & Reports"
weight: 5
---


## Access Controls in Guardium 12.1
Guardium Access Control doesn’t act like a traditional firewall or identity manager—instead, it monitors and enforces data access policies based on observed activity across databases and other data stores.

### Core Capabilities

| Feature         | Description                        |
|:----------------|:-----------------------------------|
| Access Policies           | Define rules to allow/block actions based on user, object, time, location          |
| Policy Enforcement		        | Uses STAP (S-TAP, G-TAP) agents to inspect traffic inline or out-of-band        |
| Exception Handling       | Supports granular exceptions, allowlisting, and auditing-only actions    |
| Role Segregation	            | Assigns Guardium UI/admin access using built-in role-based access control           |
| LDAP / AD Integration        | Supports importing users/groups for policy enforcement and authentication       |
	

### Example Use Cases
* Block DBA access to HR tables during non-business hours
* Alert on unauthorized access to credit card or PHI data
* Enforce least privilege across outsourced development environments
* Monitor contractor access to sensitive production data

### Policy Components
Guardium Access policies are made up of:
* Rule sets: Conditions (who, what, where, when, how)
* Actions: Block, alert, log, quarantine, notify
* Exceptions: Whitelist logic for trusted access
* Classification: Used to create "sensitive object groups" in policies

These are managed via the Policy Builder UI, and policies are assigned to Inspection Engines on database servers via Install Policy operations.

### Guardium Reporting Overview
Reporting in Guardium gives you visibility into all monitored activities, violations, risks, and trends. It’s a critical part of compliance, audit, and incident response.

Types of Reports
| Report Type         | Description                        |
|:----------------|:-----------------------------------|
| Predefined Reports           | Out-of-the-box templates for compliance, activity, violations, access, etc. |
| Custom Reports		        | Built using Query Builder or SQL-based methods   |
| Scheduled Reports       |Sent automatically via email or stored on file systems   |
| Real-Time Alerts            | Alert reports tied to policy violations, shown in UI or sent externally          |
	
	
### Key Report Categories
* Access Reports: Who accessed what, when, from where
* Exception Reports: Failed logins, denied access, policy violations
* User Activity: Login/logout reports, user privilege reports
* Sensitive Data Access: Based on classification policy tagging
* Policy Violation Logs: Triggered rule matches with context
* Vulnerability Assessment: Risk scoring and misconfiguration reports

### Custom Report Creation
* Go to Reports > Report Builder
* Choose Domain (e.g. Access, Session, Exceptions)
* Add columns and filters
* Save and publish report
* Add to Dashboards or schedule for delivery

Advanced users can write SQL-based reports using Guardium’s GDM Schema, or export results in PDF, CSV, HTML, Excel formats.

### Role-Based Access Control (RBAC)
Guardium's internal user management allows you to assign:



| Role         | Access Priviledges                    |
|:----------------|:-----------------------------------|
|Administrator|	Full access to configuration, policies, reports|
|Auditor|	View reports, cannot modify configuration|
|Policy Manager|	Create/edit policies, no admin access|
|Report Manager|	Create/edit custom reports, manage schedules|

You can also integrate with Active Directory or LDAP to map user groups to these roles via Admin Console > Access Management.

