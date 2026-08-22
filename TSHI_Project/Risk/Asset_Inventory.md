# Asset Inventory 

*Document ID: TSHI-RISK-AI-001 Version: 1.0 Classification: Internal Use Only — Confidential Last Updated: August 2026 Owner: IT Director / Information Security Team*

**Purpose**
--- 

This document provides a comprehensive inventory of information assets owned, operated, or managed by Tri-State Health Initiative. Assets are categorized by type, assigned a data classification, and rated by their criticality to TSHI's operations. 

The asset inventory serves the following purposes within the risk assessment: 
- Establishes what must be protected and why
- Provides the foundation for threat and vulnerability identification
- Supports prioritization of risks based on asset criticality
- Enables accurate scoping of security controls and remediation efforts

**Asset Classification Schema** 
--- 

**Data Sensitivity Classification** 

|Classification Level|Description|Examples|
|:---|:---:|---:|
|Critical|Highly sensitive data; exposure causes severe regulatory, financial, or patient safety harm|ePHI, patient diagnoses, medication records|
|Confidential|Sensitive internal data; exposure causes significant harm but is limited in scope|Employee records, financial data, system configurations|
|Internal|Data intended for internal use only; limited harm if exposed externally|Internal policies, operational procedures, meeting records|
|Public|Data intended for public consumption; no harm if disclosed|Public website content, published press releases| 

**Asset Criticality Rating** 

|Criticality Rating|Description|
|:---|---:|
|Critical|Asset is essential to patient care or core operations; loss causes immediate and severe impact|
|High|Asset is important to operations; loss causes significant disruption but workarounds exist|
|Moderate|Asset supports operations; loss causes inconvenience and reduces efficiency|
|Low|Asset is supplementary; loss has minimal operational impact| 

**Data Assets** 
--- 

|Asset ID|Asset Name|Description|Data Classification|Criticality|Regulatory Requirement|Primary Location|
|:---|:---:|:---:|:---:|:---:|:---:|---:|
|DA-001|Electronic Protected Health Information (ePHI)|Patient medical records including diagnoses, medications, treatment history, lab results, and clinical notes|Critical|Critical|HIPAA Security Rule, HITECH|Epic EHR, PACS, LIS|
|DA-002|Patient Demographic Information|Patient names, addresses, dates of birth, Social Security numbers, contact information|Critical|Critical|HIPAA Privacy Rule, NJ Identity Theft Prevention Act|Epic EHR, Patient Scheduling System|
|DA-003|Medical Imaging Data|Radiology images including X-rays, MRIs, and CT scans linked to patient records|Critical|Critical|HIPAA Security Rule|PACS System|
|DA-004|Laboratory Results|Patient lab test orders, processing data, and results reports|Critical|High|HIPAA Security Rule|Laboratory Information System|
|DA-005|Pharmacy Records|Medication orders, dispensing records, and patient prescription history|Critical|Critical|HIPAA Security Rule, DEA regulations|Pharmacy Management System|
|DA-006|Patient Payment and Billing Data|Insurance information, payment card data, billing records, and claims data|Confidential|High|HIPAA, PCI-DSS|Billing System, Payment Processing|
|DA-007|Employee Records|HR files, payroll data, benefits information, personnel records|Confidential|High|Privacy Act, NJ/NY state law|HRIS System|
|DA-008|Network and System Configuration Data|Firewall rules, network diagrams, server configurations, Active Directory structure|Confidential|High|Internal; no specific regulation|IT Infrastructure|
|DA-009|Security Logs and Audit Trails|System logs, access logs, authentication records, security event data|Confidential|High|HIPAA Audit Controls|Windows Event Logs, Application Logs|
|DA-010|Vendor and Contract Data|Business Associate Agreements, vendor contracts, service level agreements|Confidential|Moderate|HIPAA Business Associate Requirements|Administrative File Systems|
|DA-011|Financial and Operational Data|General ledger, budget data, accounts payable and receivable records|Confidential|High|Internal financial controls|Financial Management System|
|DA-012|Public Website Content|Patient-facing website, provider directories, public health information|Public|Low|None|Public Web Server| 

**System Assets** 
--- 

**Clinical Systems** 

|Asset ID|Asset Name|System Type|Data Classification|Criticality|ontains ePHI|Primary Users|
|:---|:---:|:---:|:---:|:---:|:---:|---:|
|SYS-001|Epic EHR System|Electronic Health Record Platform|Critical|Critical|Yes|All clinical staff|
|SYS-002|PACS System|Medical Imaging Storage and Retrieval|Critical|Critical|Yes|Radiology, clinical staff|
|SYS-003|Laboratory Information System|Lab Test Management|Critical|Critical|Yes|Laboratory staff, clinicians|
|SYS-004|Pharmacy Management System|Medication Management|Critical|Critical|Yes|Pharmacy staff, clinicians|
|SYS-005|Patient Scheduling System|Appointment and Registration Management|Critical|High|Yes|Front desk, administrative staff|
|SYS-006|Telehealth Platform|Remote Patient Consultation|Confidential|High|Yes|Clinicians, patients|
|SYS-007|Medical Device Integration Engine|Connects bedside devices to EHR|Critical|Critical|Yes|IT, clinical engineering| 

**Administrative Systems** 

|Asset ID|Asset Name|System Type|Data Classification|Criticality|Contains Sensitive Data|Primary Users|
|:---|:---:|:---:|:---:|:---:|:---:|---:|
|SYS-008|Microsoft 365 (Exchange Online)|Email and Collaboration Platform|Confidential|High|Yes; internal communications|All staff|
|SYS-009|Billing and Revenue Cycle System|Medical Billing and Claims Processing|Confidential|High|Yes; financial, insurance data|Billing department|
|SYS-010|Human Resources Information System|HR and Payroll Management|Confidential|High|Yes; employee PII, payroll|HR department|
|SYS-011|Financial Management System|General Ledger and Accounting|Confidential|High|Yes; financial data|Finance department|
|SYS-012|Help Desk Ticketing System|IT Support Management|Internal|Moderate|Yes; system and user data|IT department| 

**Infrastructure Assets** 

|Asset ID|Asset Name|Asset Type|Data Classification|Criticality|Notes|
|:---|:---:|:---:|:---:|:---:|---:|
|INF-001|Primary Data Center|Physical Server Room|Confidential|Critical|Houses all on-premise servers and storage — main hospital Newark|
|INF-002|Active Directory Domain Controllers|Identity and Access Management|Confidential|Critical|Controls all user authentication and authorization across TSHI|
|INF-003|Primary Storage Area Network (SAN)|Data Storage Infrastructure|Critical|Critical|Stores all clinical and administrative data on-premise|
|INF-004|Core Network Switches and Routers|Network Infrastructure|Confidential|Critical|Backbone of TSHI network connectivity across all locations|
|INF-005|Perimeter Firewall (NGFW)|Network Security Device|Confidential|Critical|Primary barrier between TSHI internal network and internet|
|INF-006|VMware Virtualization Platform|Server Virtualization|Confidential|Critical|Hosts approximately 40 virtual machines; compromise affects all VMs|
|INF-007|VPN Gateway|Remote Access Infrastructure|Confidential|High|Provides remote access for staff; no MFA currently enforced|
|INF-008|Backup Infrastructure (Veeam)|Data Backup and Recovery|Critical|Critical|Daily and weekly backups of all servers; critical for ransomware recovery|
|INF-009|MPLS WAN Circuits|Wide Area Network Connectivity|Internal|High|Connects all four facility locations|
|INF-010|AWS S3 Cloud Backup|Cloud-Based Backup Storage|Critical|High|Offsite copy of all backup data| 

**Endpoint Assets** 

|Asset ID|Asset Type|Quantity|Operating System|Criticality|Notes|
|:---|:---:|:---:|:---:|:---:|---:|
|END-001|Clinical Workstations|~450|Windows 10/11|High|Mix of OS versions; some approaching end of support|
|END-002|Administrative Workstations|~280|Windows 10/11|Moderate|Primarily current OS versions|
|END-003|Staff Laptops|~120|Windows 11|High|Used for remote access; VPN dependent|
|END-004|Clinical Tablets|~80|iOS/Android|High|Bedside documentation; access EHR directly|
|END-005|Thin Clients|~60|Windows IoT|Moderate|Nursing station EHR access|
|END-006|Multifunction Printers|~95|Various Firmware|Low|Firmware not consistently updated; potential entry point| 

**Medical Device Assets** 

|Asset ID|Asset Type|Quantity|Network Connected|Firmware Status|Criticality|
|:---|:---:|:---:|:---:|:---:|---:|
|MED-001|Patient Monitoring Systems|~85|Yes|Mixed; some outdated|Critical|
|MED-002|Imaging Systems (MRI, CT, X-ray)|~12|Yes|Vendor-managed; not all current|Critical|
|MED-003|Infusion Pumps|~140|Yes|Outdated on older units|Critical|
|MED-004|Laboratory Analyzers|~20|Yes|Vendor-managed|High|
|MED-005|Building Management Systems|~8|Yes|Varies|Moderate|
|MED-006|IP Security Cameras|~65|Yes|Mixed; not consistently updated|Moderate|

**Human Assets**
---

|Asset ID|Role Category|Count|Access to ePHI|Criticality|Risk Notes|
|:---|:---:|:---:|:---:|:---:|---:|
|HUM-001|Clinical Staff (Physicians, Nurses, Allied Health)|~600|Yes; broad  access|Critical|High-value phishing targets; access to full patient records|
|HUM-002|Administrative Staff|~300|Limited; demographic and billing data|High|Access to financial and PII data; billing fraud risk|
|HUM-003|IT Staff|~45|Yes; privileged system access|Critical|Privileged accounts; compromise has organization-wide impact|
|HUM-004|Executive Leadership|~15|Yes; summary level|High|High-value targets for spear phishing and business email compromise|
|HUM-005|Third-Party Vendors and Contractors|~240|Varies by contract|High|External access to internal systems; vendor risk management critical| 

**Facility Assets**
---

|Asset ID|Facility|Location|Critically|Physical Security Status|
|:---|:---:|:---:|:---:|---:|
|FAC-001|TSHI Main Hospital|Newark, NJ|Critical|Badge access control; adequate|
|FAC-002|TSHI North Clinic|Paterson, NJ|High|Traditional key locks; inadequate|
|FAC-003|TSHI East Clinic|Jersey City, NJ|High|Traditional key locks; inadequate|
|FAC-004|TSHI Metro Clinic|Bronx, NY|High|Traditional key locks; inadequate|
|FAC-005|Primary Data Center|Newark, NJ (Main Hospital)|Critical|Badge access; limited monitoring| 

**Asset Summary**
---

|Asset Category|Total Assets Identified|Critical Assets|High Assets|
|:---|:---:|:---:|---:|
|Data Assets|12|5|5|
|Clinical Systems|7|5|2|
|Administrative Systems|5|0|4|
|Infrastructure Assets|10|6|3|
|Endpoint Assets|6 categories(~1085 devices)|0|3|
|Medical Device Assets|6 categories(~330 devices)|3|2|
|Human Assets|5 categories(~1200 individual)|2|3|
|Facility Assets|5|2|3| 

**Related Documents** 
|Document|Path|
|:---|---:|
|IT Environment|[IT Environment](../Organization/IT_Environment.md)|
|Organization Profile|[Organization Profile](../Organization/Organization_Profile.md)|
|Threat Identification|[Threat Identification](Threat_Identification.md)|
|Vulnerability Identification|[Vulnerability Identification](Vulnerability_Identification.md)|
|Risk Register|[Risk Register](Risk_Register.md)|

*Document ID: TSHI-RISK-AI-001 | Version: 1.0 | Classification: Internal Use Only — Confidential | Case Study — Tri-State Health Initiative (TSHI)*
