<!-- 
WHAT IS THIS FILE?
This file maps the risks identified in the Risk Register
to specific security controls from NIST SP 800-53 Rev. 5 —
the federal government's comprehensive catalog of security and privacy controls.
Think of NIST SP 800-53 as a giant menu of security controls
organized into 20 control families covering every aspect of security.
The mapping answers the question: for each risk we identified,
which specific NIST controls would address it?
This is important for three reasons:
1. It gives TSHI a standards-based framework for remediation —
   instead of guessing what controls to implement,
   they follow the controls that NIST has determined are appropriate
2. It demonstrates to auditors and regulators that TSHI's security
   program is aligned with federal standards —
   particularly important for any organization that may work
   with federal agencies or seek federal contracts
3. It creates a direct link between risk findings and control recommendations —
   every recommendation can be traced back to a NIST control family
NIST SP 800-53 is the control catalog used in the Risk Management Framework (RMF)
which is mandatory for federal information systems.
For a healthcare organization that interacts with federal health agencies
(CMS, HHS, NIH) this alignment is practically valuable.
For your career goal of working in federal cybersecurity,
knowing 800-53 control families is essential —
they form the backbone of federal agency security programs.
-->

# Annex B — NIST SP 800-53 Control Mapping — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-ANX-NIST-001
**Version:** 1.0
**Classification:** Internal Use Only
**Last Updated:** August 2026
**Owner:** Information Security Team / CISO

---

## 1. Purpose

<!-- 
This document bridges the gap between risk findings and standardized controls.
A risk assessment without control recommendations is just a list of problems.
Control recommendations without traceability to a standard
are just opinions. This document combines both —
showing exactly which NIST 800-53 controls address which TSHI risks,
so that remediation decisions are grounded in federal standards.
-->

This document maps identified TSHI risks to applicable security controls from NIST SP 800-53 Rev. 5 — Security and Privacy Controls for Information Systems and Organizations. The mapping provides a standards-based framework for implementing the remediation actions recommended in the Risk Register.

---

## 2. NIST SP 800-53 Control Family Overview

<!-- 
NIST SP 800-53 organizes its controls into 20 control families.
Each family covers a specific domain of security.
Knowing these families and their two-letter abbreviations
is fundamental knowledge for federal cybersecurity work.
The families most relevant to TSHI's identified risks are:
AC (Access Control) — directly addresses TSHI's MFA and access management gaps
AU (Audit and Accountability) — addresses the SIEM and logging gaps
CA (Assessment, Authorization, and Monitoring) — covers the risk assessment program
CP (Contingency Planning) — addresses BC/DR gaps
IA (Identification and Authentication) — covers MFA and credential management
IR (Incident Response) — covers the incident response program
RA (Risk Assessment) — the core framework for this entire project
SC (System and Communications Protection) — covers network segmentation
SI (System and Information Integrity) — covers patching and malware
These are the families you should know cold going into any federal cybersecurity interview.
-->

| Control Family | Abbreviation | Description |
|---|---|---|
| Access Control | AC | Controls governing who can access systems and data |
| Awareness and Training | AT | Security awareness and specialized training for workforce |
| Audit and Accountability | AU | Logging, monitoring, and audit trail requirements |
| Assessment, Authorization, and Monitoring | CA | Ongoing monitoring, assessment, and system authorization |
| Configuration Management | CM | System configuration standards and change management |
| Contingency Planning | CP | Business continuity, backup, and disaster recovery |
| Identification and Authentication | IA | Identity verification, authentication, and credential management |
| Incident Response | IR | Incident response capability and procedures |
| Maintenance | MA | System maintenance and maintenance tools |
| Media Protection | MP | Protection of system media containing sensitive information |
| Physical and Environmental Protection | PE | Physical access controls and environmental safeguards |
| Planning | PL | Security planning and rules of behavior |
| Program Management | PM | Organization-wide security program governance |
| Personnel Security | PS | Workforce screening, access agreements, and termination |
| Personally Identifiable Information Processing | PT | Privacy controls for PII |
| Risk Assessment | RA | Risk assessment methodology and vulnerability monitoring |
| System and Services Acquisition | SA | Security in system procurement and development |
| System and Communications Protection | SC | Network architecture, encryption, and communications security |
| System and Information Integrity | SI | Malware protection, patching, and system monitoring |
| Supply Chain Risk Management | SR | Third-party and vendor security risk management |

---

## 3. Risk-to-Control Mapping

<!-- 
This section maps each identified TSHI risk to the specific NIST 800-53
controls that would address it.
The control ID format is: Family Abbreviation - Control Number
For example: AC-2 = Access Control family, control number 2 (Account Management)
Each control has a name and a brief description of how it addresses the risk.
In a full NIST 800-53 implementation each control also has
a set of control enhancements (sub-controls) that provide
additional specificity — we reference the base controls here.
This level of specificity — being able to say "we are implementing
AC-2, AC-3, and IA-5 to address TSHI-RISK-002" —
is what distinguishes a professional security program
from ad-hoc security decisions.
-->

### TSHI-RISK-001 — Ransomware Attack via Phishing

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| SI-3 | Malicious Code Protection | Requires deployment and maintenance of malware protection tools — addresses the need for EDR |
| SI-4 | System Monitoring | Requires monitoring of information systems for attacks — addresses the need for SIEM |
| AT-2 | Literacy Training and Awareness | Requires security awareness training for all users — addresses phishing susceptibility |
| AT-3 | Role-Based Training | Requires specialized training based on role — addresses need for role-specific phishing training |
| IR-2 | Incident Response Training | Requires training on incident response procedures — addresses untested IR plan |
| CP-9 | System Backup | Requires backup of system-level information — addresses untested backup integrity |
| CP-10 | System Recovery and Reconstitution | Requires recovery procedures for systems — addresses recovery gap |
| IA-5 | Authenticator Management | Requires management of authenticators including passwords — addresses weak credential practices |
| SC-7 | Boundary Protection | Requires monitoring of communications at system boundaries — addresses perimeter security |
| RA-5 | Vulnerability Monitoring and Scanning | Requires vulnerability scanning — addresses inconsistent patching |

---

### TSHI-RISK-002 — Unauthorized Access to EHR via Compromised Credentials

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| IA-2 | Identification and Authentication — Organizational Users | Requires unique identification and authentication for all users — addresses lack of MFA |
| IA-2(1) | MFA for Privileged Accounts | Requires MFA for privileged account access — addresses admin account exposure |
| IA-2(2) | MFA for Non-Privileged Accounts | Requires MFA for non-privileged account access — directly addresses EHR MFA gap |
| AC-2 | Account Management | Requires formal account lifecycle management — addresses access review and offboarding gaps |
| AC-3 | Access Enforcement | Requires enforcement of approved authorizations — addresses access control gap |
| AC-17 | Remote Access | Requires controls for remote access sessions — addresses VPN and remote EHR access |
| AU-2 | Event Logging | Requires logging of security-relevant events — addresses absence of comprehensive audit logging |
| AU-6 | Audit Record Review, Analysis, and Reporting | Requires review of audit records — addresses absence of SIEM for log correlation |
| SI-4 | System Monitoring | Requires monitoring for unauthorized access — addresses behavioral detection gap |

---

### TSHI-RISK-003 — Medical Device Exploitation

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| SC-7 | Boundary Protection | Requires monitoring and control of communications — addresses medical device network segmentation gap |
| SC-39 | Process Isolation | Requires isolation of processes to prevent unauthorized information transfer — supports device segmentation |
| CM-6 | Configuration Settings | Requires configuration settings for security — addresses medical device firmware management |
| CM-7 | Least Functionality | Requires devices be configured to provide only essential capabilities — applies to medical device hardening |
| SA-9 | External System Services | Requires controls for externally provided systems — addresses vendor-managed medical device security |
| RA-5 | Vulnerability Monitoring and Scanning | Requires vulnerability scanning — addresses medical device vulnerability identification |
| SR-3 | Supply Chain Controls and Processes | Requires supply chain security controls — addresses medical device vendor security |

---

### TSHI-RISK-004 — Insider Theft of ePHI

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| AC-2 | Account Management | Requires formal access review and termination procedures — addresses overprivileged insider access |
| AC-6 | Least Privilege | Requires minimum necessary access — directly addresses insider access scope |
| AU-2 | Event Logging | Requires logging of user activity — addresses lack of insider behavior monitoring |
| AU-6 | Audit Record Review | Requires review of audit records for suspicious activity — addresses absence of behavioral monitoring |
| SI-4 | System Monitoring | Requires monitoring for unauthorized access — addresses insider threat detection gap |
| PS-4 | Personnel Termination | Requires access revocation upon termination — addresses offboarding gap |
| PS-7 | External Personnel Security | Requires security controls for external workers — addresses contractor access management |
| AC-17 | Remote Access | Requires monitoring of remote access — addresses remote insider threat |

---

### TSHI-RISK-005 — Business Email Compromise

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| IA-2(2) | MFA for Non-Privileged Accounts | Requires MFA — directly addresses Microsoft 365 MFA gap |
| SC-5 | Denial of Service Protection | Requires protection against attack types including email-based attacks | 
| SC-8 | Transmission Confidentiality and Integrity | Requires protection of transmitted information — supports email security |
| AT-2 | Literacy Training and Awareness | Requires awareness training — addresses executive phishing susceptibility |
| AT-3 | Role-Based Training | Requires role-specific training — addresses need for executive-targeted training |
| SI-8 | Spam Protection | Requires spam and malicious email protection — addresses basic email security gap |
| AC-2 | Account Management | Requires account management controls — addresses executive account security |

---

### TSHI-RISK-006 — Privilege Escalation via Admin Accounts

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| AC-6 | Least Privilege | Requires minimum necessary privilege — directly addresses over-privileged admin accounts |
| AC-6(1) | Authorize Access to Security Functions | Requires explicit authorization for security function access — addresses admin account management |
| AC-6(5) | Privileged Accounts | Requires restrictions on privileged accounts — directly addresses PAM gap |
| IA-2(1) | MFA for Privileged Accounts | Requires MFA for privileged access — addresses admin account authentication gap |
| AU-9 | Protection of Audit Information | Requires protection of audit logs — addresses risk of attackers covering tracks |
| CM-5 | Access Restrictions for Change | Requires access restrictions for system changes — supports change management |
| AC-2(6) | Dynamic Privilege Management | Supports just-in-time privileged access — addresses need for PAM solution |

---

### TSHI-RISK-007 — Supply Chain Attack via Vendor

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| SR-2 | Supply Chain Risk Management Plan | Requires a supply chain risk management plan — addresses absence of vendor risk program |
| SR-3 | Supply Chain Controls and Processes | Requires controls for supply chain — addresses vendor security assessment gap |
| SR-6 | Supplier Assessments and Reviews | Requires assessment of suppliers — directly addresses inconsistent vendor security reviews |
| AC-20 | Use of External Systems | Requires controls for use of external systems — addresses vendor remote access gap |
| AU-12 | Audit Record Generation | Requires audit record generation for all relevant events — addresses vendor session logging gap |
| SA-9 | External System Services | Requires security requirements for external services — addresses third-party security management |
| IA-2(2) | MFA for Non-Privileged Accounts | Requires MFA — addresses vendor account authentication gap |

---

### TSHI-RISK-008 — Unauthorized Physical Access at Clinics

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| PE-2 | Physical Access Authorizations | Requires maintaining lists of authorized physical access — addresses visitor management gap |
| PE-3 | Physical Access Control | Requires physical access control systems — directly addresses key lock gap at clinics |
| PE-6 | Monitoring Physical Access | Requires monitoring physical access — addresses absence of physical monitoring |
| PE-8 | Visitor Access Records | Requires records of visitor access — addresses visitor management gap |
| MP-4 | Media Storage | Requires protection of physical media — addresses physical data security |
| SC-28 | Protection of Information at Rest | Requires protection of stored information — addresses unencrypted device risk |
| MP-5 | Media Transport | Requires controls for media transport — addresses device theft risk |

---

### TSHI-RISK-009 — Silent Data Exfiltration

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| SI-4 | System Monitoring | Requires monitoring for unauthorized activity — directly addresses absence of SIEM and DLP |
| AU-2 | Event Logging | Requires logging of data access events — addresses logging gap |
| AU-6 | Audit Record Review | Requires review of audit records — addresses absence of monitoring analysis |
| SC-7 | Boundary Protection | Requires monitoring at network boundaries — addresses exfiltration detection gap |
| SC-28 | Protection of Information at Rest | Requires encryption at rest — addresses unencrypted data risk |
| AC-4 | Information Flow Enforcement | Requires enforcement of information flow policies — supports DLP implementation |
| RA-5 | Vulnerability Monitoring and Scanning | Requires vulnerability scanning — addresses security gaps enabling exfiltration |

---

### TSHI-RISK-010 — Extended Downtime — No Secondary Site

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| CP-2 | Contingency Plan | Requires a contingency plan — addresses untested BCP |
| CP-4 | Contingency Plan Testing | Requires testing of contingency plans — directly addresses untested BCP gap |
| CP-6 | Alternate Storage Site | Requires alternate storage site for backup — addresses absence of secondary site |
| CP-7 | Alternate Processing Site | Requires alternate processing site — directly addresses single data center risk |
| CP-9 | System Backup | Requires regular system backup — addresses backup program requirements |
| CP-10 | System Recovery and Reconstitution | Requires recovery procedures — addresses recovery capability gap |
| CP-9(1) | Testing for Reliability and Integrity | Requires testing backup reliability — directly addresses untested backup gap |

---

### TSHI-RISK-011 — Cloud Misconfiguration

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| CM-6 | Configuration Settings | Requires security configuration settings — addresses cloud misconfiguration risk |
| CM-7 | Least Functionality | Requires minimum necessary functionality — applies to cloud service configuration |
| CM-8 | System Component Inventory | Requires inventory of system components — supports cloud asset management |
| CA-7 | Continuous Monitoring | Requires continuous security monitoring — addresses need for CSPM |
| AC-20 | Use of External Systems | Requires controls for cloud service use — addresses cloud governance gap |
| RA-5 | Vulnerability Monitoring and Scanning | Requires vulnerability scanning — applies to cloud configuration scanning |

---

### TSHI-RISK-012 — Accidental Data Deletion

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| CM-3 | Configuration Change Control | Requires change control for system configurations — addresses change management gap |
| CP-9 | System Backup | Requires backup of critical data — addresses data recovery capability |
| CP-9(1) | Testing for Reliability and Integrity | Requires backup testing — addresses untested backup gap |
| SI-12 | Information Management and Retention | Requires information management and retention — addresses data preservation |
| AT-2 | Literacy Training and Awareness | Requires security awareness — addresses human error contributing to accidental deletion |

---

### TSHI-RISK-013 — Network Connectivity Loss at Clinics

| NIST Control | Control Name | How It Addresses This Risk |
|---|---|---|
| CP-2 | Contingency Plan | Requires contingency plan including network failure scenarios | 
| CP-4 | Contingency Plan Testing | Requires testing of contingency plans — addresses need to test VPN failover |
| CP-8 | Telecommunications Services | Requires alternate telecommunications services — supports MPLS failover planning |
| CP-2(1) | Coordinate with Related Plans | Requires coordination of contingency planning — addresses clinic-specific downtime procedures |
| SC-7 | Boundary Protection | Requires boundary protection — supports network resilience |

---

## 4. Control Family Coverage Summary

<!-- 
This summary shows which NIST 800-53 control families are most heavily
implicated in TSHI's risk profile.
The top three families — IA, AC, and SI — reflect the most
critical gaps: no MFA, weak access controls, and limited monitoring.
For anyone pursuing federal cybersecurity work,
knowing these families and being able to discuss specific controls
within them is foundational knowledge.
Many federal job postings reference 800-53 control families directly.
-->

| Control Family | Controls Referenced | Risks Addressed | Priority |
|---|---|---|---|
| Identification and Authentication (IA) | IA-2, IA-2(1), IA-2(2), IA-5 | RISK-001, 002, 005, 006, 007 | Critical — MFA gaps are the most urgent remediation |
| Access Control (AC) | AC-2, AC-3, AC-4, AC-6, AC-6(1), AC-6(5), AC-17, AC-20 | RISK-002, 004, 005, 006, 007, 008 | Critical — access management gaps across multiple risks |
| System and Information Integrity (SI) | SI-3, SI-4, SI-8, SI-12 | RISK-001, 002, 004, 009 | Critical — monitoring and malware protection gaps |
| Contingency Planning (CP) | CP-2, CP-4, CP-6, CP-7, CP-8, CP-9, CP-9(1), CP-10 | RISK-001, 010, 012, 013 | High — BC/DR capability gaps |
| Audit and Accountability (AU) | AU-2, AU-6, AU-9, AU-12 | RISK-002, 004, 007, 009 | High — logging and monitoring gaps |
| Supply Chain Risk Management (SR) | SR-2, SR-3, SR-6 | RISK-007 | High — vendor risk management |
| Physical and Environmental Protection (PE) | PE-2, PE-3, PE-6, PE-8 | RISK-008 | High — physical security at clinics |
| System and Communications Protection (SC) | SC-7, SC-8, SC-28, SC-39 | RISK-003, 008, 009, 011, 013 | High — network segmentation and encryption |
| Awareness and Training (AT) | AT-2, AT-3 | RISK-001, 004, 005, 012 | High — security training gaps |
| Configuration Management (CM) | CM-3, CM-5, CM-6, CM-7, CM-8 | RISK-003, 011, 012 | Moderate — configuration and change management |
| Incident Response (IR) | IR-2 | RISK-001 | Moderate — IR training and exercise |
| Risk Assessment (RA) | RA-5 | RISK-001, 003, 007, 009, 011 | Moderate — vulnerability management |
| System and Services Acquisition (SA) | SA-9 | RISK-003, 007 | Moderate — third-party security requirements |
| Personnel Security (PS) | PS-4, PS-7 | RISK-004 | Moderate — workforce security |

---

## 5. Related Documents

| Document | Path |
|---|---|
| Risk Register | [../Risk/Risk_Register.md](../Risk/Risk_Register.md) |
| Compliance Matrix | [../Matrices/Compliance_Matrix.md](../Matrices/Compliance_Matrix.md) |
| Risk Rating Matrix | [../Matrices/Risk_Rating_Matrix.md](../Matrices/Risk_Rating_Matrix.md) |
| NIST 800-30 Methodology | [../Docs/NIST_800-30_Methodology.md](../Docs/NIST_800-30_Methodology.md) |
| RACI Matrix | [Annex_A_RACI_Matrix.md](Annex_A_RACI_Matrix.md) |

---

*Document ID: TSHI-ANX-NIST-001 | Version: 1.0 | Classification: Internal Use Only | Case Study — Tri-State Health Initiative (TSHI)*
