# Risk Register — Tri-State Health Initiative (TSHI)

**Document ID: TSHI-RISK-RR-001 Version: 1.0 Classification: Internal Use Only — Confidential Last Updated: August 2026 Owner: Chief Information Security Officer (CISO)**


**Purpose**
---

This Risk Register documents all information security risks identified during the TSHI risk assessment conducted in accordance with NIST SP 800-30 Rev. 1. Each risk entry combines an identified threat event with one or more vulnerabilities and affected assets to produce a complete risk record including likelihood, impact, overall risk rating, and recommended treatment.

The Risk Register serves as the primary output of the risk assessment and the primary input for security investment and remediation planning.



**Risk Rating Methodology**


Risk is determined by combining the **Likelihood** of a threat event occurring with the **Impact** it would cause if it did. Both are rated on a three-point qualitative scale.

**Likelihood Scale:**

| Rating | Definition |
|---|---|
| High | Threat source is highly motivated and capable; vulnerability is easily exploitable; exploitation is likely |
| Moderate | Threat source has some capability; exploitation is possible but requires effort or opportunity |
| Low | Threat source lacks motivation or capability; exploitation is unlikely given existing controls |

**Impact Scale:**

| Rating | Definition |
|---|---|
| High | Severe harm — significant ePHI exposure, major regulatory penalties, patient safety risk, extended operational disruption |
| Moderate | Significant harm — limited data exposure, operational disruption, reputational damage, manageable recovery |
| Low | Minor harm — minimal data exposure, limited operational impact, quickly recoverable |

**Risk Rating Matrix:**

| Likelihood \ Impact | High Impact | Moderate Impact | Low Impact |
|---|---|---|---|
| High Likelihood | **Critical** | **High** | **Moderate** |
| Moderate Likelihood | **High** | **Moderate** | **Low** |
| Low Likelihood | **Moderate** | **Low** | **Low** |

**Risk Treatment Options:**

| Treatment | Definition |
|---|---|
| Mitigate | Implement controls to reduce likelihood or impact |
| Accept | Formally acknowledge and accept the risk with documented approval |
| Transfer | Shift the risk to a third party through insurance or outsourcing |
| Avoid | Eliminate the activity or system that introduces the risk |



**Risk Register**
---

**Critical Risks***


**TSHI-RISK-001 — Ransomware Attack via Phishing**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-001 |
| **Risk Title** | Ransomware Attack via Phishing Leading to EHR Encryption and Patient Data Inaccessibility |
| **Affected Assets** | SYS-001 (Epic EHR), INF-001 (Data Center), INF-003 (SAN), DA-001 (ePHI), DA-002 (Patient Demographics) |
| **Threat Event** | TE-C-001 (Ransomware Attack), TE-C-002 (Phishing Attack) |
| **Vulnerabilities** | VT-001 (No MFA on EHR), VT-003 (No SIEM), VT-004 (No EDR), VT-013 (Basic Email Security), VA-002 (IR Plan Untested), VA-006 (Backup Integrity Untested), VH-001 (Phishing Susceptibility) |
| **Likelihood** | High |
| **Impact** | High |
| **Risk Rating** | **Critical** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
A threat actor sends a phishing email to a TSHI staff member. The staff member clicks a malicious link and unknowingly installs ransomware. With no EDR to detect the malware and no SIEM to correlate suspicious behavior, the ransomware propagates across the network via Active Directory, encrypting the Epic EHR system, the SAN, and clinical workstations. Patient care is disrupted across all four facilities. Recovery is complicated by untested backups and an unexercised incident response plan.

**Likelihood Justification:**
Healthcare is the most ransomware-targeted sector. TSHI lacks MFA on EHR, EDR on endpoints, and advanced email filtering — making phishing-initiated ransomware highly probable.

**Impact Justification:**
Encryption of the EHR system directly threatens patient safety, triggers HIPAA breach notification obligations, and could result in regulatory penalties. Extended downtime affects 85,000 patients across four facilities.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Deploy MFA on Epic EHR | Enforce MFA for all clinical and administrative EHR users | Immediate |
| Implement EDR Solution | Replace basic antivirus with EDR for behavioral detection and response | Immediate |
| Upgrade Email Security | Enable advanced phishing, impersonation, and attachment sandboxing protection | Immediate |
| Deploy SIEM | Implement centralized log aggregation and real-time alerting | Short-term |
| Test Backup Restoration | Conduct quarterly backup restoration tests to validate recoverability | Immediate |
| Exercise Incident Response Plan | Conduct tabletop exercise simulating a ransomware scenario | Short-term |
| Role-Specific Phishing Training | Implement phishing simulations and role-specific security awareness training | Short-term |



**TSHI-RISK-002 — Unauthorized Access to EHR via Compromised Credentials**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-002 |
| **Risk Title** | Unauthorized Access to Epic EHR via Stolen or Weak Credentials Leading to ePHI Breach |
| **Affected Assets** | SYS-001 (Epic EHR), DA-001 (ePHI), DA-002 (Patient Demographics), DA-003 (Medical Imaging) |
| **Threat Event** | TE-C-003 (Unauthorized EHR Access), TE-C-002 (Phishing — Credential Theft) |
| **Vulnerabilities** | VT-001 (No MFA on EHR), VT-002 (No MFA on Internal Systems), VH-001 (Phishing Susceptibility), VH-002 (Weak Password Practices), VA-004 (No Formal Access Review) |
| **Likelihood** | High |
| **Impact** | High |
| **Risk Rating** | **Critical** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
A threat actor obtains valid EHR credentials through a phishing attack or by exploiting weak/reused passwords. With no MFA protecting the EHR system, the stolen credentials provide direct, unrestricted access to patient records for all 85,000 TSHI patients. The attacker exfiltrates ePHI for sale on criminal marketplaces. No SIEM is in place to detect the anomalous access pattern. HIPAA breach notification is triggered.

**Likelihood Justification:**
Credential theft via phishing is the most common initial access method in healthcare breaches. The absence of MFA on the EHR means a single compromised password is sufficient for full access.

**Impact Justification:**
Unauthorized access to ePHI for 85,000 patients triggers mandatory HIPAA breach notification, potential OCR investigation, and significant reputational harm. Patient identity theft and medical fraud may follow.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Deploy MFA on Epic EHR | Immediate enforcement of MFA for all EHR users | Immediate |
| Implement Password Policy Enforcement | Enforce minimum complexity, length, and prohibit credential reuse | Immediate |
| Deploy SIEM with UBA | User Behavior Analytics to detect anomalous EHR access patterns | Short-term |
| Conduct Access Reviews | Quarterly review of EHR user accounts and access levels | Short-term |
| Implement SSO | Reduce credential sprawl and improve authentication management | Medium-term |



**TSHI-RISK-003 — Medical Device Exploitation as Network Pivot Point**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-003 |
| **Risk Title** | Exploitation of Vulnerable Networked Medical Device Used as Pivot to Clinical Network and EHR |
| **Affected Assets** | MED-001 (Patient Monitors), MED-002 (Imaging Systems), MED-003 (Infusion Pumps), SYS-001 (Epic EHR), DA-001 (ePHI) |
| **Threat Event** | TE-C-005 (Medical Device Exploitation), TE-C-010 (Privilege Escalation) |
| **Vulnerabilities** | VT-006 (Outdated Medical Device Firmware), VT-007 (No Medical Device Network Segmentation), VA-008 (No Medical Device Security Policy) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Rating (Elevated)** | **Critical** — elevated due to potential patient safety impact |
| **Risk Treatment** | Mitigate |

**Risk Description:**
An attacker identifies a networked medical device running outdated firmware with a known vulnerability. Because medical devices share the clinical network with EHR workstations and are not segmented, the compromised device is used as a pivot point to reach the Epic EHR system and other clinical infrastructure. Beyond data exposure, device manipulation poses a direct patient safety risk — particularly for infusion pumps and patient monitoring systems.

**Likelihood Justification:**
Medical device vulnerabilities are well-documented and actively targeted. Outdated firmware and lack of segmentation make TSHI's devices accessible from within the clinical network.

**Impact Justification:**
Rated High elevated to Critical due to the dual impact: ePHI exposure AND potential patient safety risk from device manipulation. FDA and HHS have both issued warnings about medical device cybersecurity risks.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Implement Medical Device Network Segmentation | Isolate all medical devices onto a dedicated VLAN with strict access controls | Immediate |
| Develop Medical Device Security Policy | Establish procurement, configuration, and lifecycle security standards for all networked devices | Short-term |
| Inventory and Patch Medical Devices | Work with vendors to apply available firmware updates; document devices where patching is not possible | Short-term |
| Deploy Network Access Control (NAC) | Prevent unauthorized devices from connecting to clinical network segments | Medium-term |



**TSHI-RISK-004 — Insider Theft of ePHI**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-004 |
| **Risk Title** | Malicious Insider Exfiltrates Patient Records for Financial Gain |
| **Affected Assets** | DA-001 (ePHI), DA-002 (Patient Demographics), SYS-001 (Epic EHR) |
| **Threat Event** | TE-C-009 (Insider Data Theft) |
| **Vulnerabilities** | VT-003 (No SIEM), VA-004 (No Access Review), VA-009 (Data Classification Not Enforced), VH-003 (Clinical Staff Awareness Gap), VH-005 (Offboarding Gaps) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
A clinical staff member with legitimate EHR access deliberately exfiltrates patient records — potentially selling them to identity thieves or accessing records of specific individuals such as celebrities or personal acquaintances. With no SIEM or User Behavior Analytics in place, anomalous access patterns such as bulk record downloads or off-hours access go undetected. No formal access review process exists to detect overprivileged accounts.

**Likelihood Justification:**
Insider threats in healthcare are well-documented. The combination of broad clinical access, no behavioral monitoring, and no access review process elevates likelihood.

**Impact Justification:**
Patient record theft triggers HIPAA breach notification, potential criminal charges for the employee, and significant reputational damage to TSHI. Each compromised record represents a direct harm to a patient.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Deploy SIEM with User Behavior Analytics | Detect anomalous EHR access patterns including bulk downloads and off-hours access | Short-term |
| Implement Formal Access Reviews | Quarterly review and recertification of EHR access rights | Short-term |
| Apply Minimum Necessary Access in EHR | Restrict clinical staff access to only the patient records relevant to their role | Short-term |
| Strengthen Offboarding Process | Ensure immediate access revocation upon termination across all systems | Immediate |


**High Risks**


**TSHI-RISK-005 — Business Email Compromise Targeting Executive Accounts**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-005 |
| **Risk Title** | Business Email Compromise Leading to Fraudulent Financial Transfer |
| **Affected Assets** | HUM-004 (Executive Leadership), SYS-008 (Microsoft 365), DA-011 (Financial Data) |
| **Threat Event** | TE-C-004 (Business Email Compromise) |
| **Vulnerabilities** | VT-002 (No MFA on Internal Systems), VT-013 (Basic Email Security), VH-001 (Phishing Susceptibility), VH-004 (Privileged User Awareness Gap) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
An attacker compromises or spoofs an executive email account and instructs the finance department to initiate a fraudulent wire transfer. Basic email security does not detect the spoofed or compromised account. No MFA protects the Microsoft 365 tenant admin accounts. Funds are transferred before the fraud is detected.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Enforce MFA on Microsoft 365 | Mandatory MFA for all Microsoft 365 accounts especially executives and finance | Immediate |
| Enable Advanced Email Protection | Impersonation protection, DMARC, DKIM, and SPF enforcement | Short-term |
| Financial Transfer Verification Policy | Require out-of-band verbal confirmation for all wire transfer requests above a threshold | Short-term |
| Executive-Targeted Security Training | Spear phishing awareness training specifically for executive and finance staff | Short-term |


**TSHI-RISK-006 — Privilege Escalation via Unmanaged Admin Accounts**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-006 |
| **Risk Title** | Privilege Escalation Through Unmanaged Administrative Accounts Leading to Domain Compromise |
| **Affected Assets** | INF-002 (Active Directory), INF-006 (VMware), SYS-001 (Epic EHR), INF-001 (Data Center) |
| **Threat Event** | TE-C-010 (Privilege Escalation) |
| **Vulnerabilities** | VT-009 (No PAM Solution), VT-002 (No MFA on Internal Systems), VT-005 (Inconsistent Patching), VH-004 (Privileged User Awareness Gap) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
An attacker who gains initial access through phishing or a vulnerability exploit escalates privileges by targeting unmanaged administrative accounts in Active Directory. With no PAM solution controlling and monitoring privileged access, the attacker achieves domain administrator rights — effectively owning the entire TSHI network including the EHR system, virtualization platform, and backup infrastructure.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Implement Privileged Access Management | Deploy PAM solution to control, monitor, and audit all privileged account activity | Short-term |
| Enforce MFA for All Admin Accounts | Require MFA for all Active Directory and infrastructure admin accounts | Immediate |
| Implement Tiered Admin Model | Separate day-to-day user accounts from privileged admin accounts | Short-term |
| Privileged User Security Training | Role-specific training for IT staff on privileged account security | Short-term |



**TSHI-RISK-007 — Supply Chain Attack via Compromised Vendor**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-007 |
| **Risk Title** | Supply Chain Attack Through Compromised Vendor Access Leading to TSHI Network Breach |
| **Affected Assets** | SYS-001 (Epic EHR), INF-002 (Active Directory), DA-001 (ePHI) |
| **Threat Event** | TE-C-008 (Supply Chain Attack) |
| **Vulnerabilities** | VA-003 (Vendor Assessments Inconsistent), VA-010 (Vendor Remote Access Not Audited), VT-016 (Cloud Misconfiguration Risk) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
An attacker compromises a vendor with privileged access to TSHI systems — such as the EHR vendor or managed service provider. The vendor's remote access credentials are used to move laterally through TSHI's environment. Because vendor remote access sessions are not audited, the intrusion is not detected until significant damage is done.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Implement Vendor Risk Assessment Program | Annual security assessments of all vendors with access to TSHI systems or ePHI | Short-term |
| Audit Vendor Remote Access Sessions | Log and review all vendor remote access sessions — enable just-in-time access where possible | Short-term |
| Enforce MFA for Vendor Accounts | Require MFA for all vendor accounts with access to TSHI systems | Immediate |
| Review and Limit Vendor Access Scope | Ensure vendor access is limited to only what is required for their service | Short-term |



**TSHI-RISK-008 — Unauthorized Physical Access at Outpatient Clinics**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-008 |
| **Risk Title** | Unauthorized Physical Access to Outpatient Clinic Leading to System Access or Device Theft |
| **Affected Assets** | FAC-002, FAC-003, FAC-004 (Outpatient Clinics), END-001 (Clinical Workstations), END-003 (Laptops), DA-001 (ePHI) |
| **Threat Event** | TE-P-001 (Unauthorized Physical Access), TE-P-002 (Device Theft) |
| **Vulnerabilities** | VP-001 (Key Locks at Clinics), VP-003 (No Clean Desk Policy), VP-004 (Unencrypted Portable Devices), VP-005 (No Visitor Management) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
An unauthorized individual gains physical access to one of the three outpatient clinics through a door left unlocked or by tailgating staff. They access an unattended clinical workstation with an active EHR session or steal a laptop containing unencrypted patient data. Traditional key locks provide no audit trail and keys cannot be remotely revoked.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Upgrade to Electronic Badge Access | Replace key locks with badge readers at all three outpatient clinic locations | Short-term |
| Enforce Full Disk Encryption | Ensure all laptops and tablets have verified full disk encryption enabled | Immediate |
| Implement Clean Desk Policy | Require staff to lock workstations and secure paper records when stepping away | Short-term |
| Deploy Visitor Management System | Log all visitor access at all four facility locations | Medium-term |



**TSHI-RISK-009 — Data Exfiltration Due to Limited Monitoring**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-009 |
| **Risk Title** | Silent Data Exfiltration of ePHI Due to Absence of Security Monitoring |
| **Affected Assets** | DA-001 (ePHI), DA-002 (Patient Demographics), DA-004 (Lab Results), SYS-001 (Epic EHR) |
| **Threat Event** | TE-C-006 (Data Exfiltration of ePHI) |
| **Vulnerabilities** | VT-003 (No SIEM), VT-004 (No EDR), VT-011 (Inconsistent Encryption at Rest), VA-009 (Data Classification Not Enforced) |
| **Likelihood** | Moderate |
| **Impact** | High |
| **Risk Rating** | **High** |
| **Risk Treatment** | Mitigate |

**Risk Description:**
An attacker who has gained access to TSHI systems — through any initial access vector — exfiltrates large volumes of patient data over an extended period. Without a SIEM, EDR, or data loss prevention tool, the exfiltration goes undetected until the data appears for sale or an external party notifies TSHI of the breach.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Deploy SIEM | Centralized log aggregation and alerting for anomalous data transfer activity | Short-term |
| Implement DLP Solution | Monitor and block unauthorized transfer of ePHI outside TSHI systems | Medium-term |
| Enforce Encryption at Rest | Verify and enforce full disk encryption across all systems storing ePHI | Immediate |
| Enable DNS Filtering | Block access to known data exfiltration and command-and-control domains | Short-term |

**TSHI-RISK-010 — Extended Downtime Due to No Secondary Data Center**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-010 |
| **Risk Title** | Extended Clinical System Downtime Due to Primary Data Center Failure with No Failover Capability |
| **Affected Assets** | INF-001 (Data Center), INF-003 (SAN), SYS-001 (Epic EHR), DA-001 (ePHI) |
| **Threat Event** | TE-NA-001 (Unplanned System Outage), TE-NA-005 (Natural Disaster) |
| **Vulnerabilities** | VT-015 (No Secondary Data Center), VA-005 (BCP Not Fully Tested), VA-006 (Backup Integrity Untested) |
| **Likelihood** | Low |
| **Impact** | High |
| **Risk Rating** | **Moderate** |
| **Risk Rating (Elevated)** | **High** — elevated due to patient safety impact of extended EHR downtime |
| **Risk Treatment** | Mitigate |

**Risk Description:**
A significant hardware failure, power event, or natural disaster affects the primary data center in Newark. With no geographically redundant secondary site, TSHI has no failover capability. EHR access is lost across all four facilities. Clinical staff revert to paper-based processes but downtime-procedure documentation is incomplete. Recovery time extends significantly beyond the RTO due to untested restoration procedures.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Evaluate Secondary Site or Cloud DR | Assess feasibility of a warm or hot DR site or cloud-based failover for critical systems | Medium-term |
| Test Business Continuity Plan | Conduct full BCP exercise including EHR downtime procedures | Short-term |
| Test Backup Restoration | Quarterly restoration tests from both on-premise and cloud backups | Immediate |
| Document Downtime Procedures | Develop and distribute paper-based downtime procedures for all clinical departments | Short-term |

---

**Moderate Risks**

**TSHI-RISK-011 — Cloud Service Misconfiguration Exposing ePHI**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-011 |
| **Risk Title** | Misconfiguration of Cloud Services Resulting in Unauthorized Exposure of ePHI |
| **Affected Assets** | INF-010 (AWS S3), SYS-008 (Microsoft 365), DA-001 (ePHI) |
| **Threat Event** | TE-C-012 (Cloud Misconfiguration) |
| **Vulnerabilities** | VT-016 (Cloud Misconfiguration Risk), VA-007 (No Change Management) |
| **Likelihood** | Moderate |
| **Impact** | Moderate |
| **Risk Rating** | **Moderate** |
| **Risk Treatment** | Mitigate |

**Risk Description:**

An IT administrator misconfigures an AWS S3 bucket or Microsoft 365 sharing setting, inadvertently making ePHI or sensitive organizational data publicly accessible. Cloud misconfigurations are among the most common causes of healthcare data exposures.

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Implement Cloud Security Posture Management | Automated scanning of cloud configurations for misconfigurations and policy violations | Medium-term |
| Establish Cloud Configuration Standards | Document and enforce baseline security configurations for all cloud services | Short-term |
| Implement Change Management Process | Require review and approval for all changes to cloud service configurations | Short-term |



**TSHI-RISK-012 — Accidental Data Deletion Due to No Change Management**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-012 |
| **Risk Title** | Accidental Deletion or Corruption of Clinical Data Due to Uncontrolled System Changes |
| **Affected Assets** | DA-001 (ePHI), INF-003 (SAN), SYS-001 (Epic EHR) |
| **Threat Event** | TE-NA-003 (Accidental Data Deletion or Corruption) |
| **Vulnerabilities** | VA-006 (Backup Integrity Untested), VA-007 (No Change Management), VH-003 (Clinical Staff Awareness Gap) |
| **Likelihood** | Moderate |
| **Impact** | Moderate |
| **Risk Rating** | **Moderate** |
| **Risk Treatment** | Mitigate |

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Implement Change Management Process | Require documented approval for all changes to production systems | Short-term |
| Test Backup Restoration Regularly | Validate ability to restore specific records and full systems from backup | Immediate |
| Enable Recycle Bin and Versioning | Enable soft-delete and versioning on all storage systems and cloud services where available | Short-term |



**TSHI-RISK-013 — Network Connectivity Loss Isolating Clinic Locations**

| Field | Details |
|---|---|
| **Risk ID** | TSHI-RISK-013 |
| **Risk Title** | MPLS Circuit Failure Isolating Outpatient Clinic from Central EHR System |
| **Affected Assets** | INF-009 (MPLS Circuits), SYS-001 (Epic EHR), SYS-005 (Patient Scheduling), HUM-001 (Clinical Staff) |
| **Threat Event** | TE-NA-004 (Network Connectivity Loss) |
| **Vulnerabilities** | VT-015 (No Secondary Data Center), VA-005 (BCP Not Fully Tested) |
| **Likelihood** | Moderate |
| **Impact** | Moderate |
| **Risk Rating** | **Moderate** |
| **Risk Treatment** | Mitigate |

**Recommended Controls:**

| Control | Description | Priority |
|---|---|---|
| Validate VPN Failover | Test VPN failover capability for all clinic locations and document RTO | Short-term |
| Develop Clinic Downtime Procedures | Create and distribute EHR downtime procedures specific to each clinic location | Short-term |
| Evaluate Local EHR Caching | Assess feasibility of local read-only EHR caching at clinic locations | Medium-term |



**Risk Register Summary**
---

| Risk ID | Risk Title | Rating | Treatment | Remediation Priority |
|---|---|---|---|---|
| TSHI-RISK-001 | Ransomware via Phishing | **Critical** | Mitigate | Immediate / Short-term |
| TSHI-RISK-002 | Unauthorized EHR Access via Credentials | **Critical** | Mitigate | Immediate |
| TSHI-RISK-003 | Medical Device Exploitation | **Critical** | Mitigate | Immediate / Short-term |
| TSHI-RISK-004 | Insider Theft of ePHI | **High** | Mitigate | Short-term |
| TSHI-RISK-005 | Business Email Compromise | **High** | Mitigate | Immediate / Short-term |
| TSHI-RISK-006 | Privilege Escalation via Admin Accounts | **High** | Mitigate | Immediate / Short-term |
| TSHI-RISK-007 | Supply Chain Attack via Vendor | **High** | Mitigate | Short-term |
| TSHI-RISK-008 | Unauthorized Physical Access at Clinics | **High** | Mitigate | Short-term |
| TSHI-RISK-009 | Silent Data Exfiltration | **High** | Mitigate | Short-term |
| TSHI-RISK-010 | Extended Downtime — No Secondary Site | **High** | Mitigate | Short-term / Medium-term |
| TSHI-RISK-011 | Cloud Misconfiguration | **Moderate** | Mitigate | Short-term |
| TSHI-RISK-012 | Accidental Data Deletion | **Moderate** | Mitigate | Short-term |
| TSHI-RISK-013 | Network Connectivity Loss at Clinics | **Moderate** | Mitigate | Short-term |

**Risk Count by Rating:**

| Rating | Count |
|---|---|
| Critical | 3 |
| High | 7 |
| Moderate | 3 |
| Low | 0 |
| **Total** | **13** |

---

## 5. Related Documents

| Document | Path |
|---|---|
| Asset Inventory | [Asset Inventory](Asset_Inventory.md) |
| Threat Identification | [Threat Identification](Threat_Identification.md) |
| Vulnerability Identification | [Vulnerability Identification](Vulnerability_Identification.md) |
| Likelihood and Impact Matrix | [Likelihood Impact Matrix](../Matrices/Likelihood_Impact_Matrix.md) |
| Risk Rating Matrix | [Risk Rating Matrix](../Matrices/Risk_Rating_Matrix.md) |
| NIST Control Mapping | [Annex B NIST Control Mapping](../Annexes/Annex_B_NIST_Control_Mapping.md) |
| Compliance Matrix | [Compliance Matrix](../Matrices/Compliance_Matrix.md) |


*Document ID: TSHI-RISK-RR-001 | Version: 1.0 | Classification: Internal Use Only — Confidential | Case Study — Tri-State Health Initiative (TSHI)*
