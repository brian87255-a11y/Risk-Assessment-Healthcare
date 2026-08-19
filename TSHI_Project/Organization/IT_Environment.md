**IT Environment - Tri-State Health Initiative (TSHI)** 

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
| | | | |
| | | | |
| | | | |
| | | | |
| | | | |
| | | | |






