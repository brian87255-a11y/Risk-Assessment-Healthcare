# Threat Identification — Tri-State Health Initiative 

*Document ID: TSHI-RISK-TI-001 Version: 1.0 Classification: Internal Use Only — Confidential Last Updated: August 2026 Owner: Information Security Team* 

**Purpose** 
--- 

This document identifies and categorizes threat sources and threat events relevant to Tri-State Health Initiative. Threat identification is the second step of the NIST SP 800-30 risk assessment conduct phase and establishes the threat landscape against which TSHI's vulnerabilities and risks are evaluated. 

Threats are based on: 
- Relevance — whether the threat realistically applies to a regional healthcare network
- Historical precedent — whether similar organizations have faced this threat
- Threat actor capability and intent — whether the threat source has the means and motivation to act against TSHI

**Threat Source Categories** 
--- 

|Threat Source Category|Description|Examples|
|:---|:---:|---:|
|Adversarial, External|Individuals or groups outside TSHI with malicious intent|Cybercriminals, ransomware groups, nation-state actors, hacktivists|
|Adversarial, Internal|Individuals inside TSHI with malicious or negligent intent|Malicious employees, disgruntled staff, negligent users|
|Adversarial, Third Party|Vendors, contractors, or partners who introduce risk|Compromised vendor accounts, malicious insiders at third parties|
|Non-Adversarial, Structural|Environmental or technical failures with no malicious actor|Hardware failure, software errors, power outages|
|Non-Adversarial, Environmental|Natural or physical events outside human control|Hurricanes, flooding, fires, severe weather| 

**Threat Sources** 
--- 

**External Adversarial Threat Sources**

|Threat Source ID|Threat Source|Motivation|Capability|Relevance to TSHI|
|:---|:---:|:---:|:---:|---:|
|TS-EXT-001|Ransomware Groups|Financial gain through extortion|High — well-funded, sophisticated tooling|Very High — healthcare is primary ransomware target|
|TS-EXT-002|Cybercriminals (Data Theft)|Financial gain through sale of ePHI and PII|High — established criminal marketplace|Very High — patient records are highly valuable|
|TS-EXT-003|Nation-State Actors|Espionage, disruption of critical infrastructure|Very High — state-sponsored resources|Moderate — regional healthcare less targeted than federal agencies|
|TS-EXT-004|Hacktivists|Ideological motivation, public embarrassment|Moderate — varies by group|Low to Moderate — healthcare targeted during political events|
|TS-EXT-005|Opportunistic Attackers|Financial gain through low-effort exploitation|Low to Moderate — rely on known vulnerabilities|High — unpatched systems attract automated scanning|
|TS-EXT-006|Phishing Operators|Credential theft, initial access brokering|Moderate — commodity tooling widely available|Very High — healthcare staff are frequent phishing targets| 

**Internal Adversarial Threat Sources** 

|Threat Source ID|Threat Source|Motivation|Capability|Relevance to TSHI|
|:---|:---:|:---:|:---:|---:|
|TS-INT-001|Malicious Employee|Financial gain, revenge, ideology|Moderate — has legitimate access|High — 1,200 staff with varying access levels|
|TS-INT-002|Negligent Employee|No malicious intent — accidental harm|N/A — unintentional|Very High — human error is leading cause of breaches|
|TS-INT-003|Disgruntled Employee|Revenge against organization|Moderate — depends on role and access|Moderate — elevated during staff transitions|
|TS-INT-004|Privileged User Abuse|Financial gain, curiosity|High — IT staff have broad system access| have broad system accessHigh — IT and clinical admin accounts have elevated privileges| 

**Third-Party Threat Sources** 

|Threat Source ID|Threat Source|Motivation|Capability|Relevance to TSHI|
|:---|:---:|:---:|:---:|---:|
|TS-TP-001|Compromised Vendor|Attacker uses vendor access as entry point to TSHI|High — leverages trusted relationships|High — multiple vendors have direct EHR and system access|
|TS-TP-002|Malicious Third-Party Contractor|Financial gain, espionage|Moderate — has temporary system access|Moderate — ~240 contractors with varying access|
|TS-TP-003|Software Supply Chain Attack|Compromise of software used by TSHI|High — sophisticated nation-state technique|Moderate — TSHI relies on multiple third-party software products| 

**Non-Adversarial Threat Sources** 

|Threat Source ID|Threat Source|Type|Relevance to TSHI|
|:---|:---:|:---:|---:|
|TS-NA-001|Hardware Failure|Structural — technical|High — aging server infrastructure; some end-of-life hardware|
|TS-NA-002|Software Errors and Bugs|Structural — technical|High — complex clinical systems with interdependencies|
|TS-NA-003|Power Failure|Structural — environmental|High — loss of power affects all on-premise systems and patient care|
|TS-NA-004|Network Failure|Structural — technical|High — MPLS circuit failure isolates clinic locations|
|TS-NA-005|Human Error|Structural — human|Very High — misconfiguration, accidental deletion, improper handling of ePHI|
|TS-NA-006|Natural Disaster (Hurricane/Flooding)|Environmental|Moderate — New Jersey and New York are hurricane and flood risk areas|
|TS-NA-007|Fire|Environmental|Moderate — data center fire risk without full suppression system|
|TS-NA-008|Pandemic or Public Health Emergency|Environmental|Moderate — demonstrated impact on healthcare operations during COVID-19| 

**Threat Events** 
---

|Threat Event ID|Threat Event|Threat Source(s)|Assets Targeted|Description|
|:---|:---:|:---:|:---:|---:|
|TE-C-001|Ransomware Attack|TS-EXT-001, TS-EXT-005|SYS-001, INF-001, INF-003, DA-001|Malware encrypts TSHI systems and data, rendering them inaccessible until ransom is paid or systems are restored from backup|
|TE-C-002|Phishing Attack|TS-EXT-006, TS-EXT-002|HUM-001, HUM-002, SYS-008|Deceptive emails trick staff into revealing login credentials, enabling unauthorized access to TSHI systems and ePHI|
|TE-C-003|Unauthorized Access to EHR|TS-EXT-002, TS-INT-001, TS-TP-001|SYS-001, DA-001, DA-002|Attacker or insider gains unauthorized access to the Epic EHR system and exfiltrates patient records|
|TE-C-004|Business Email Compromise|TS-EXT-006, TS-EXT-002|HUM-004, SYS-008, DA-011|Attacker impersonates executive or trusted party via email to authorize fraudulent financial transactions|
|TE-C-005|Medical Device Exploitation|TS-EXT-001, TS-EXT-005|MED-001, MED-002, MED-003|Attacker exploits vulnerable networked medical devices to gain foothold in TSHI network or disrupt device operation|
|TE-C-006|Data Exfiltration of ePHI|TS-EXT-002, TS-INT-001, TS-TP-001|DA-001, DA-002, DA-003, DA-004|Sensitive patient data is copied and transmitted to unauthorized external parties for sale or leverage|
|TE-C-007|Denial of Service Attack|TS-EXT-001, TS-EXT-004|INF-004, INF-005, SYS-001|Network or system is flooded with traffic rendering clinical and administrative systems unavailable|
|TE-C-008|Supply Chain Attack|TS-TP-003, TS-EXT-003|SYS-001, INF-006, INF-002|Malicious code introduced through compromised vendor software or update mechanism affects TSHI systems|
|TE-C-009|Insider Data Theft|TS-INT-001, TS-INT-004|DA-001, DA-002, DA-007|Employee or privileged user deliberately exfiltrates patient records or sensitive organizational data|
|TE-C-010|Privilege Escalation|TS-EXT-001, TS-INT-004|INF-002, INF-006, SYS-001|Attacker exploits misconfiguration or vulnerability to gain elevated privileges — potentially full domain control|
|TE-C-011|Man-in-the-Middle Attack|TS-EXT-001, TS-EXT-005|INF-009, SYS-006, END-003|Attacker intercepts network communications between TSHI systems or between staff and cloud services|
|TE-C-012|Misconfiguration of Cloud Services|TS-NA-005, TS-INT-002|005, TS-INT-002	INF-010, SYS-008, DA-001|Incorrect configuration of Microsoft 365 or AWS S3 exposes sensitive data or creates unauthorized access paths|

**Physical Threat Event** 

|Threat Event ID|Threat Event|Threat Source(s)|Assets Targeted|Description|
|:---|:---:|:---:|:---:|---:|
|TE-P-001|Unauthorized Physical Access|TS-EXT-002, TS-INT-001|FAC-002, FAC-003, FAC-004, END-001|Unauthorized individual gains physical access to a clinic or workstation area and accesses systems or steals equipment|
|TE-P-002|Theft of Endpoint Device|TS-EXT-002, TS-INT-001|END-003, END-004, DA-001|Laptop or tablet containing ePHI is stolen from staff or facility|
|TE-P-003|Unauthorized Access to Data Center|TS-EXT-002, TS-INT-001|FAC-005, INF-001, INF-003|Unauthorized individual gains physical access to the primary data center| 

**Non-Adversarial Threat Events** 

|Threat Event ID|Threat Event|Threat Source(s)|Assets Targeted|Description|
|:---|:---:|:---:|:---:|---:|
|TE-NA-001|Unplanned System Outage|TS-NA-001, TS-NA-002|SYS-001, INF-001, INF-003|Hardware failure or software error causes unplanned downtime of critical clinical systems|
|TE-NA-002|Extended Power Failure|TS-NA-003|INF-001, SYS-001, MED-001|Extended loss of power beyond UPS and generator capacity disrupts all on-premise systems and medical devices|
|TE-NA-003|Accidental Data Deletion or Corruption|TS-NA-005, TS-INT-002|DA-001, DA-002, INF-003|Staff error or software bug results in unintentional deletion or corruption of critical patient data|
|TE-NA-004|Network Connectivity Loss|TS-NA-004|INF-009, SYS-001, SYS-005|MPLS circuit failure isolates one or more clinic locations from central systems and EHR access|
|TE-NA-005|Natural Disaster Impacting Facilities|TS-NA-006, TS-NA-007|FAC-001, FAC-002, FAC-003, FAC-004, INF-001|Hurricane, flooding, or fire damages TSHI facilities or the primary data center| 

**Threat Prioritization Summary**
---

|Threat Event ID|Threat Event|Overall Priority|Primary Reason|
|:---|:---:|:---:|---:|
|TE-C-001|Ransomware Attack|Very High|Healthcare is most targeted sector; TSHI lacks SIEM and EDR|
|TE-C-002|Phishing Attack|Very High|No MFA on most systems; staff not role-specifically trained|
|TE-C-003|Unauthorized Access to EHR|Very High|No MFA on Epic; high value ePHI target|
|TE-C-006|Data Exfiltration of ePHI|High|High value data; limited monitoring capability|
|TE-C-009|Insider Data Theft|High|1,200 staff; limited access monitoring|
|TE-C-005|Medical Device Exploitation|High|Outdated firmware; limited network segmentation|
|TE-C-008|Supply Chain Attack|High|Multiple vendors with direct system access|
|TE-C-004|Business Email Compromise|High|Executive accounts targeted; no advanced email filtering|
|TE-C-010|Privilege Escalation|High|No PAM solution; AD admin accounts not tightly controlled|
|TE-NA-001|Unplanned System Outage|Moderate|Aging infrastructure; no secondary data center|
|TE-P-001|Unauthorized Physical Access|Moderate|Weak physical controls at three outpatient clinics|
|TE-C-007|Denial of Service Attack|Moderate|Perimeter firewall provides some mitigation|
|TE-NA-002|Extended Power Failure|Moderate|UPS and generators present but not tested regularly|
|TE-NA-005|Natural Disaster|Low to Moderate|Geographic risk present; DR plan partially developed|

**Related Documents** 
--- 

|Document|Path|
|:---|---:|
|Asset Inventory|[Asset Inventory]{Asset_Inventory.md}|
|Vulnerability Identification|[Vulnerability Identification]{Vulnerability_Identification.md}|
|Risk Register|[Risk Register]{Risk_Register.md}|
|IT Environment|[IT Environment]{../Organization/IT_Environment.md}|
|Likelihood and Impact Matrix|[Likelihood and Impact Matrix]{../Matrices/Likelihood_Impact_Matrix.md}|
