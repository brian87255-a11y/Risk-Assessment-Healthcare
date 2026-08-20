# IT Environment - Tri-State Health Initiative (TSHI)

*Document ID: TSHI-ORG-IT-001 Version: 1.0 Classification: Internal Use Only — Confidential Last Updated: August 2026 Owner: IT Director*

**Overview** 
--- 

Tri-State Health Initiative (TSHI) operates a distributed IT environment spanning four facilities across New Jersey and New York. The environment supports clinical operations, administrative functions, patient-facing services, and corporate infrastructure. TSHI uses a combination of on-premise infrastructure at the main hospital campus and cloud-hosted services for select applications and data storage. 

**Network Architecture** 
--- 

**Network Topology**

TSHI operates a hub-and-spoke model with the main hospital campus in Newark seeing as the central hub. All three outpatient clinics connect back to the main campus via dedicated MPLS circuits with VPN failover

|Location |Connection Type |Bandwidth |Failover|
|:---|:---:|:---:|---:|
|TSHI Main Hospital (Newark)|Core Data Center |N/A |Redundant ISP |
|TSHI North Clinic (Paterson) |MPLS Circuit |500 Mbps |VPN over broadband |
|TSHI East Clinic (Jersey City)) |MPLS Circuit |500 Mbps |VPN over broadband |
|TSHI Metro Clinic (Bronx, NY)) |MPLS Circuit |1 Gbps  |VPN over broadband |

**Network Segmentation** 

TSHI currently maintains the following networks segments: 

|Network Segment |Purpose |Segmentation Status |
|:---|:---:|---:|
|Clinical Network| EHR systems, medical devices, clinical workstations |Partially segmented from administrative network |
|Administrative Network |Email, billing, HR systems, office workstations |Partially segmented from clinical network |
|Guest/Patient Wi-Fi |Patient and visitor wireless access |Fully isolated from internal networks |
|Medical Device Network |IoT medical devices, imaging systems |Not fully segmented; shared with clinical network |
|Management Network|IT infrastructure management, server access |Partially segmented |

**Internet Access and Perimeter Security** 

|Control |Details |
|:---|---:|
|Firewall |Next generation firewall (NGFW) deployed at main campus perimeter |
|Web Filtering |Content filter applied to administrative network |
|Email Security |Spam filtering and basic phishing protection place |
|Remote Access |VPN with username and password; MFA not yet enforced  |
|DNS Security |Standard DNS; no DNS filtering or monitoring solution deployed |

**Core Infrastructure** 
--- 

**Server Infrastructure**


|Component|Details|Locations|
|:---|:---:|---:|
|Primary Data Center |On-premise server room at main hospital campus |Newark, NJ |
|Server Virtualization |VMware vSphere; approximately 40 virtual machines |On-premise |
|Physical Servers |Dell PowerEdge - mix of generations, some end-of-life |On-premise |
|Storage Area Network (SAN) |Dell EMC SAN for primary clinical and administrative data |On-premise |
|Backup Infrastructure |Veeam Backup; daily incremental, weekly full backups |On-premise + cloud copy |
|Secondary Data Center |None; no fully redundant secondary site |N/A | 


**Directory Services and Identity Management** 


|Component|Details|
|:---|---:|
|Directory Service |Microsoft Active Directory (on-premise) |
|Identity Management |Active Directory; no dedicated Identity Governance tool |
|Multi-Factor Authentication |Deployed for VPN access only; not enforced for internal systems or EHR |
|Privileged Access |No dedicated PAM solution; admin accounts managed manually |
|Single Sign-On |Not deployed; users maintain separate credentials per system | 

**Endpoint Infrastructure** 

|Component|Quantity|Operating Systems|Notes|
|:---|:---:|:---:|---:|
|Clinical Workstations |~450 |Windows 10/11 |Mix of versions; some running Windows 10 past mainstream support|
|Administrative Workstations |~280|Windows 10/11|Mostly current|
|Laptops|~120 |Windows 11|Issued to management and clinical staff for remote access|
|Tablets|~80|iOS/Android|Used by nursing staff for bedside documentation|
|Thin Clients|~60|Windows IoT|Used at nursing stations for EHR access|
|Printers/MFDs|~95|Various firmware|Mix of ages; firmware not consistently updated| 

**Clinical Systems** 
---

**Electronic Health Record (EHR) System** 

|Field|Details|
|:---|---:|
|EHR Platform|Epic Systems (cloud-assisted, on-premise hosted modules)|
|Deployment Model|Hybrid; core modules on-premise, some features cloud-hosted via Epic|
|Users|All clinical staff across all four faculties|
|Data Hosted|Patient demographics, medical history, diagnoses, medications, lab results, clinical notes|
|Interpretation|Interfaces with lab systems, pharmacy, imaging and billing|
|Access Method|Web browser and dedicated client application|
|MFA Enforced|No| 

**Additional Clinical Systems** 
 
|System|Purpose|Hosting|Contains ePHI|
|:---|:---:|:---:|---:|
|Microsoft 365 (Exchange Online)|Email, calendar, collaboration (Teams, SharePoint)|Cloud |Yes; internal communications, some ePHI in email |
|Billing and Revenue Cycle System|Medical billing, insurance claims, payment processing|On-premise|Yes; financial data, insurance information |
|Human Resources Information System (HRIS)|Employee records, payroll, benefits|Cloud hosted (SaaS)|Yes; PII, payroll data|
|Financial Management System|General ledger, accounts payable/receivable, budgeting|On-premise|Yes; financial data|
|Help Desk Ticketing System|IT support request management|Cloud hosted (SaaS)|Yes; system information, user data| 

**Medical Devices and IoT** 
--- 

TSHI operates a range of networked medical devices and IoT equipment across all facilities:



|Device Category|Examples|Network Connected|OS/Firmware Status|Security Controls|
|:---|:---:|:---:|---:|---:|
|Patient Monitoring Systems|Vital signs monitors, telemetry units|Yes|Mixed; some outdated firmware|Limited|
|Imaging Systems|MRI, CT, X-ray machines|Yes|Vendor-managed; not all current|Limited|
|Infusion Pumps|IV medication delivery systems|Yes|Outdated firmware on older units|Minimal|
|Laboratory Analyzers|Blood analyzers, diagnostic equipment|Yes|Vendor-managed|Limited|
|Building Management Systems|HVAC, access control, elevators|Yes|Varies|Minimal|
|Security Cameras (IP)|Physical surveillance across all locations|Yes|Mixed firmware versions|Minimal|

**Cloud Services** 
--- 
|Service|Provider|Purpose|Data Classification|MFA Enforced|
|:---|:---:|:---:|:---:|---:|
|Microsoft 365|Microsoft Azure|Email, collaboration, productivity|Internal / some ePHI|Partially|
|Epic Cloud Services|Epic Systems|EHR cloud-hosted modules|ePHI|Yes|
|Cloud Backup|AWS S3|Offsite backup storage|ePHI/All data types|Yes|
|Telehealth Platform|Third-party SaaS|Remote patient visits|ePHI|Yes|
|HR System|Third-party SaaS|Employee records and payroll|PII/HR data|Yes|
|Patient Scheduling|Third-party SaaS|Appointment management|ePHI/PII|Partially|


 **Security Tools Currently Deployed** 
 --- 
 
|Tool Category|Tool/Solution|Coverage|Notes|
|:---|:---:|:---:|---:|
|Antivirus / Endpoint Protection|Microsoft Defender|All Windows endpoints|No EDR (Endpoint Detection and Response) capability|
|Firewall|Next-Gen Firewall (NGFW)|Perimeter only|No internal network segmentation firewall|
|Email Security|Microsoft Defender for Office 365 (Basic)|All staff email|Basic tier — limited advanced threat protection|
|VPN|Cisco AnyConnect|Remote access|MFA not enforced|
|Patch Management|Microsoft WSUS|Windows endpoints only|Medical devices and third-party apps patched inconsistently|
|Log Management|Windows Event Logs|Endpoints and servers|Logs collected but no centralized SIEM for correlation|
|Data Backup|Veeam|Servers and workstations|Backup integrity testing not performed regularly|
|Physical Access Control|Badge readers|Main hospital only|Outpatient clinics use traditional key locks|


**Notable Security Gaps:** 

|Gap|Risk Implication|
|:---|---:|
|No SIEM deployed|Security events are logged but not correlated or alerted on in real time|
|MFA not enforced for EHR or internal systems|Compromised credentials provide direct access to ePHI|
|No EDR solution|Limited visibility into endpoint threats and attacker behavior post-compromise|
|No Privileged Access Management|Admin accounts not monitored or controlled beyond standard AD policies|
|Inconsistent patch management for medical devices|Known vulnerabilities may exist on networked clinical devices|
|No DNS filtering|Malicious domains accessible from internal network| 


**Related Documents** 
--- 

|Document|Path|
|:---|---:|
|Organization Profile|[Organization Profile](Organization_Profile.md)|
|Regulatory Framework|[Regulatory Framework](Regulatory_Framework.md)|
|Asset Inventory|[Asset Inventory](../Risk/Asset_Inventory.md)|
|Vulnerability Identification|[Vulnerability Identification](../Risk/Vulnerability_Identification.md)|
|Network Topology Diagram|[Network Topology Diagram](../Diagrams/Network_Topology.md)|

*Document ID: TSHI-ORG-IT-001 | Version: 1.0 | Classification: Internal Use Only — Confidential | Case Study — Tri-State Health Initiative (TSHI)*
