<!-- 
WHAT IS THIS FILE?
The Compliance Matrix maps TSHI's regulatory requirements
to the specific security controls that satisfy them.
Think of it as a crosswalk between the law and the technical implementation.
It answers a very specific question that auditors and regulators ask:
"For each requirement you are subject to, what control do you have in place
to meet it, what evidence proves it is working, and who is responsible?"
Without this matrix, compliance is theoretical — you might HAVE controls
but you cannot PROVE which requirement each control satisfies.
With this matrix, every requirement has a named control, evidence source,
responsible party, and compliance status.
This is one of the most practically valuable documents in the entire project
because in a real organization this is exactly what you hand to an auditor
during a HIPAA compliance review or OCR investigation.
-->

# Compliance Matrix — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-MAT-CM-001
**Version:** 1.0
**Classification:** Internal Use Only — Confidential
**Last Updated:** August 2026
**Owner:** Compliance Officer / Information Security Team

---

## 1. Purpose

<!-- 
This document serves a dual purpose:
1. It demonstrates that TSHI has mapped every applicable regulatory requirement
   to a specific control — showing intentional compliance management
2. It identifies gaps where requirements exist but controls are missing or insufficient
   — which directly informs the remediation recommendations in the Risk Register
A compliance matrix is a standard deliverable in any mature security program.
It is the document that gets you through a HIPAA audit because
instead of scrambling to prove compliance on the spot,
you already have the mapping documented and ready.
-->

This Compliance Matrix maps applicable regulatory and framework requirements to TSHI's implemented or planned security controls. It identifies the compliance status of each requirement, the evidence that demonstrates compliance, and the responsible party for maintaining that compliance.

The matrix covers the following frameworks and regulations:

- HIPAA Security Rule — Administrative, Physical, and Technical Safeguards
- HITECH Act — Breach Notification Requirements
- NIST Cybersecurity Framework (CSF) 2.0 — Core Functions
- PCI-DSS — Key Requirements applicable to TSHI

---

## 2. Compliance Status Definitions

<!-- 
Before listing requirements we define what each status means.
Consistent status definitions are critical because
"compliant" means different things to different people.
Does compliant mean a control exists? Or that it works? Or that it is documented?
For this matrix we define it as: the control exists, is implemented,
and evidence can be produced to demonstrate it is working.
Partially Compliant means something exists but it is insufficient,
inconsistent, or undocumented.
Non-Compliant means nothing meaningful exists to address the requirement.
In Progress means remediation is underway as part of this risk assessment.
-->

| Status | Definition |
|---|---|
| ✅ Compliant | Control is fully implemented, documented, and evidence is available to demonstrate effectiveness |
| ⚠️ Partially Compliant | Control exists but is incomplete, inconsistently applied, or lacks sufficient documentation or evidence |
| ❌ Non-Compliant | No meaningful control exists to address the requirement — immediate remediation required |
| 🔄 In Progress | Remediation is planned or underway as a result of this risk assessment |

---

## 3. HIPAA Security Rule — Administrative Safeguards

<!-- 
Administrative safeguards are the policies, procedures, and management
controls that govern how TSHI protects ePHI.
They are the foundation of HIPAA compliance — HIPAA requires these
before it even asks about technical controls.
The risk assessment requirement (164.308(a)(1)) is the most important one
for our purposes — this entire project exists to satisfy it.
Note that HIPAA uses "required" and "addressable" specifications.
Required = must be implemented as stated.
Addressable = must be implemented if reasonable and appropriate,
or an equivalent alternative must be documented and justified.
This distinction is important — "addressable" does not mean optional.
-->

| Requirement ID | HIPAA Standard | Specification | Requirement Description | Implemented Control | Evidence | Responsible Party | Status |
|---|---|---|---|---|---|---|---|
| HIPAA-AS-001 | 164.308(a)(1) | Required | Risk Analysis — Conduct accurate and thorough assessment of potential risks to ePHI | NIST SP 800-30 Risk Assessment — this document set | Risk Register, Threat and Vulnerability documentation | CISO / Information Security Team | 🔄 In Progress |
| HIPAA-AS-002 | 164.308(a)(1) | Required | Risk Management — Implement security measures to reduce risks to ePHI to a reasonable level | Risk treatment plan documented in Risk Register | Risk Register remediation sections | CISO / IT Director | 🔄 In Progress |
| HIPAA-AS-003 | 164.308(a)(1) | Required | Sanction Policy — Apply appropriate sanctions to workforce members who fail to comply with security policies | HR disciplinary policy references security violations | HR Policy, Employee Handbook | HR Director / CISO | ⚠️ Partially Compliant |
| HIPAA-AS-004 | 164.308(a)(1) | Required | Information System Activity Review — Regularly review records of information system activity | Windows Event Logs reviewed periodically — no SIEM | IT review logs — inconsistent | IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-005 | 164.308(a)(2) | Required | Assigned Security Responsibility — Designate a security official responsible for security policies | CISO designated and active | Organizational chart, job description | CEO | ✅ Compliant |
| HIPAA-AS-006 | 164.308(a)(3) | Addressable | Authorization and Supervision — Implement procedures for authorization of access to ePHI | Active Directory access controls; no formal access review process | AD group policies | IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-007 | 164.308(a)(3) | Addressable | Workforce Clearance — Determine appropriate access for workforce members | HR background checks at hiring; access provisioning inconsistent | HR records | HR Director / IT | ⚠️ Partially Compliant |
| HIPAA-AS-008 | 164.308(a)(3) | Addressable | Termination Procedures — Implement procedures for terminating access of former workforce members | IT performs account disabling — no formal documented process | IT tickets — inconsistent | IT Director / HR | ⚠️ Partially Compliant |
| HIPAA-AS-009 | 164.308(a)(4) | Addressable | Access Authorization — Implement policies for granting access to ePHI | Role-based access in Epic EHR — not formally reviewed | Epic access logs | IT Director / Clinical Leads | ⚠️ Partially Compliant |
| HIPAA-AS-010 | 164.308(a)(5) | Addressable | Security Awareness Training — Train all workforce members on security policies | Annual generic security training provided | Training completion records | CISO / HR | ⚠️ Partially Compliant |
| HIPAA-AS-011 | 164.308(a)(5) | Addressable | Security Reminders — Periodic security reminders to workforce | Ad hoc email reminders — no formal program | Email records — inconsistent | CISO | ⚠️ Partially Compliant |
| HIPAA-AS-012 | 164.308(a)(5) | Addressable | Malicious Software Protection — Implement procedures for guarding against malicious software | Microsoft Defender deployed on all Windows endpoints | Defender management console | IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-013 | 164.308(a)(5) | Addressable | Log-in Monitoring — Implement procedures for monitoring log-in attempts | Windows Event Logs capture login attempts — not centrally monitored | Event logs — not alerting | IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-014 | 164.308(a)(5) | Addressable | Password Management — Implement procedures for creating, changing, and safeguarding passwords | Active Directory password policy enforced — MFA not universally deployed | AD password policy | IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-015 | 164.308(a)(6) | Required | Security Incident Procedures — Implement policies and procedures to address security incidents | Basic incident response plan exists — untested | IR Plan document | CISO | ⚠️ Partially Compliant |
| HIPAA-AS-016 | 164.308(a)(7) | Required | Contingency Plan — Establish policies for responding to emergencies affecting ePHI systems | BCP and DR plan exist — not fully tested | BCP document, DR plan | CIO / CISO | ⚠️ Partially Compliant |
| HIPAA-AS-017 | 164.308(a)(7) | Addressable | Data Backup Plan — Create and maintain retrievable exact copies of ePHI | Veeam daily incremental and weekly full backups — restoration untested | Veeam backup logs | IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-018 | 164.308(a)(7) | Addressable | Disaster Recovery Plan — Restore lost data in the event of emergency | DR plan exists — no secondary site — partially tested | DR Plan document | CIO / IT Director | ⚠️ Partially Compliant |
| HIPAA-AS-019 | 164.308(a)(8) | Required | Evaluation — Perform periodic technical and non-technical evaluations | This risk assessment — first formal evaluation | Risk Assessment documentation | CISO | 🔄 In Progress |
| HIPAA-AS-020 | 164.308(b)(1) | Required | Business Associate Contracts — Obtain satisfactory assurances from business associates | BAAs in place with all ePHI-handling vendors | Executed BAA documents | Compliance Officer / Legal | ✅ Compliant |

---

## 4. HIPAA Security Rule — Physical Safeguards

<!-- 
Physical safeguards protect the physical systems and facilities
where ePHI is stored and processed.
HIPAA does not just care about cybersecurity —
it requires that the physical spaces housing ePHI are also controlled.
TSHI's biggest physical safeguard gap is at the outpatient clinics
where traditional key locks provide no audit trail and
access cannot be revoked without changing locks.
-->

| Requirement ID | HIPAA Standard | Specification | Requirement Description | Implemented Control | Evidence | Responsible Party | Status |
|---|---|---|---|---|---|---|---|
| HIPAA-PS-001 | 164.310(a)(1) | Required | Facility Access Controls — Limit physical access to systems containing ePHI | Badge access at main hospital; key locks at outpatient clinics | Badge system logs — main campus only | Facilities Manager / IT | ⚠️ Partially Compliant |
| HIPAA-PS-002 | 164.310(a)(2) | Addressable | Contingency Operations — Allow facility access to support restoration of lost data | Contingency access procedures exist for data center | DR Plan — contingency access section | IT Director | ⚠️ Partially Compliant |
| HIPAA-PS-003 | 164.310(a)(2) | Addressable | Facility Security Plan — Safeguard facility and equipment from unauthorized physical access | Security plan exists for main campus — not documented for clinics | Facilities security documentation | Facilities Manager | ⚠️ Partially Compliant |
| HIPAA-PS-004 | 164.310(a)(2) | Addressable | Access Control and Validation — Control and validate persons' access to facilities based on role | Badge access with role-based authorization at main campus only | Badge system records | Facilities Manager | ⚠️ Partially Compliant |
| HIPAA-PS-005 | 164.310(b) | Required | Workstation Use — Implement policies for proper use of workstations accessing ePHI | Acceptable use policy exists — not consistently enforced | AUP document | CISO / IT Director | ⚠️ Partially Compliant |
| HIPAA-PS-006 | 164.310(c) | Required | Workstation Security — Implement physical safeguards for workstations accessing ePHI | Screen locks enforced via AD policy — clean desk not formally enforced | AD Group Policy | IT Director | ⚠️ Partially Compliant |
| HIPAA-PS-007 | 164.310(d)(1) | Required | Device and Media Controls — Implement policies for hardware and media containing ePHI | Media disposal policy exists — portable media encryption inconsistent | Policy document — partial evidence | IT Director | ⚠️ Partially Compliant |
| HIPAA-PS-008 | 164.310(d)(2) | Addressable | Media Disposal — Implement policies for final disposal of ePHI | Certified media destruction for decommissioned hardware | Destruction certificates | IT Director | ✅ Compliant |
| HIPAA-PS-009 | 164.310(d)(2) | Addressable | Media Re-use — Implement procedures for removal of ePHI before media re-use | Sanitization procedures documented for storage media | IT sanitization records | IT Director | ✅ Compliant |
| HIPAA-PS-010 | 164.310(d)(2) | Addressable | Accountability — Maintain records of hardware and media movement | Asset tracking system in use — not consistently updated | Asset inventory records | IT Director | ⚠️ Partially Compliant |

---

## 5. HIPAA Security Rule — Technical Safeguards

<!-- 
Technical safeguards are the technology-based controls that protect ePHI.
This is where the most significant TSHI gaps exist —
no MFA on EHR, no SIEM, inconsistent encryption at rest,
and no User Behavior Analytics.
These gaps map directly to the Critical and High risks in the Risk Register.
The technical safeguards section is typically the most scrutinized
by OCR during a HIPAA investigation because it involves
the most objectively measurable controls.
You either have MFA or you do not.
You either encrypt data at rest or you do not.
There is less room for interpretation than in administrative safeguards.
-->

| Requirement ID | HIPAA Standard | Specification | Requirement Description | Implemented Control | Evidence | Responsible Party | Status |
|---|---|---|---|---|---|---|---|
| HIPAA-TS-001 | 164.312(a)(1) | Required | Access Control — Implement technical policies allowing only authorized access to ePHI | Active Directory RBAC; no MFA on EHR | AD access logs; Epic access logs | IT Director | ⚠️ Partially Compliant |
| HIPAA-TS-002 | 164.312(a)(2) | Addressable | Unique User Identification — Assign unique identifiers to each user | Unique AD accounts for all users — shared accounts prohibited by policy | AD user records | IT Director | ✅ Compliant |
| HIPAA-TS-003 | 164.312(a)(2) | Addressable | Emergency Access Procedure — Establish procedures for emergency access to ePHI | Emergency access accounts defined in DR plan | DR Plan — emergency access section | IT Director / CISO | ⚠️ Partially Compliant |
| HIPAA-TS-004 | 164.312(a)(2) | Addressable | Automatic Logoff — Implement procedures to terminate sessions after inactivity | AD Group Policy enforces screen lock — session timeout in Epic configured | AD policy; Epic configuration | IT Director | ✅ Compliant |
| HIPAA-TS-005 | 164.312(a)(2) | Addressable | Encryption and Decryption — Implement mechanism to encrypt and decrypt ePHI | Encryption in transit (TLS) — encryption at rest inconsistent | TLS certificates; partial disk encryption evidence | IT Director | ⚠️ Partially Compliant |
| HIPAA-TS-006 | 164.312(b) | Required | Audit Controls — Implement hardware and software to record and examine system activity | Windows Event Logs; Epic audit trail — no centralized SIEM | Event log exports; Epic audit reports | IT Director | ⚠️ Partially Compliant |
| HIPAA-TS-007 | 164.312(c)(1) | Required | Integrity Controls — Protect ePHI from improper alteration or destruction | File integrity monitoring partial — no dedicated solution | Limited evidence | IT Director | ⚠️ Partially Compliant |
| HIPAA-TS-008 | 164.312(c)(2) | Addressable | Authentication Mechanism — Implement electronic mechanism to corroborate ePHI authenticity | Digital signatures on select clinical documents — not comprehensive | Epic document signature records | IT Director | ⚠️ Partially Compliant |
| HIPAA-TS-009 | 164.312(e)(1) | Required | Transmission Security — Implement security measures guarding against unauthorized ePHI access during transmission | TLS 1.2+ enforced for all ePHI transmission; VPN for remote access | TLS certificates; VPN logs | IT Director | ✅ Compliant |
| HIPAA-TS-010 | 164.312(e)(2) | Addressable | Encryption of ePHI in Transit — Implement encryption for ePHI transmitted over open networks | TLS encryption enforced for all external ePHI transmission | TLS configuration records | IT Director | ✅ Compliant |

---

## 6. HITECH — Breach Notification Requirements

<!-- 
HITECH requires healthcare organizations to notify affected individuals,
HHS, and in some cases the media when a breach of unsecured ePHI occurs.
The key word is "unsecured" — if ePHI is encrypted and the encryption key
is not compromised, it may qualify as a safe harbor and not require notification.
This is why encryption is so important in healthcare —
beyond protecting patient data, it can determine whether a breach
triggers the expensive and reputationally damaging notification process.
The 60-day notification window starts from the date of DISCOVERY,
not the date the breach occurred. Breaches are often discovered
weeks or months after they happen, so the clock does not start until
the organization becomes aware.
-->

| Requirement ID | HITECH Standard | Requirement Description | Implemented Control | Evidence | Responsible Party | Status |
|---|---|---|---|---|---|---|
| HITECH-BN-001 | 45 CFR 164.400 | Individual Notification — Notify affected individuals within 60 days of breach discovery | Breach notification procedure in IR Plan | IR Plan — breach notification section | CISO / Compliance Officer / Legal | ⚠️ Partially Compliant |
| HITECH-BN-002 | 45 CFR 164.406 | Media Notification — Notify media for breaches affecting 500+ residents of a state | Procedure documented — not tested | IR Plan | CISO / Communications | ⚠️ Partially Compliant |
| HITECH-BN-003 | 45 CFR 164.408 | HHS Notification — Notify HHS of all breaches; immediately for 500+ affected | HHS notification procedure in IR Plan | IR Plan | Compliance Officer / Legal | ⚠️ Partially Compliant |
| HITECH-BN-004 | 45 CFR 164.412 | Law Enforcement Delay — Procedures for delaying notification at law enforcement request | Procedure referenced in IR Plan | IR Plan | Legal / CISO | ⚠️ Partially Compliant |
| HITECH-BN-005 | 45 CFR 164.530(j) | Breach Log — Maintain log of all breaches of unsecured ePHI | Incident log maintained by IT — not formally structured as breach log | IT incident records | CISO / Compliance Officer | ⚠️ Partially Compliant |

---

## 7. NIST Cybersecurity Framework 2.0 — Core Functions

<!-- 
The NIST CSF is voluntary but TSHI has adopted it as a guiding framework.
Mapping to CSF functions shows how TSHI's security program
covers each area of cybersecurity practice.
The CSF 2.0 has six functions — the new Govern function was added in 2024.
Remember: Govern, Identify, Protect, Detect, Respond, Recover.
TSHI's weakest areas are Detect and Govern —
no SIEM means limited detection capability,
and governance practices are not fully mature.
-->

| CSF Function | Description | TSHI Implementation | Key Gaps | Status |
|---|---|---|---|---|
| **Govern** | Establish cybersecurity risk management strategy, policies, and accountability | CISO designated; security policies partially developed; risk assessment initiated | Governance framework not formalized; Board reporting not established | ⚠️ Partially Compliant |
| **Identify** | Understand assets, risks, and vulnerabilities | Asset inventory developed; risk assessment conducted | Asset inventory not previously maintained; continuous monitoring absent | 🔄 In Progress |
| **Protect** | Implement safeguards to protect critical services | AD access controls; Defender AV; TLS encryption; badge access at main campus | No MFA on EHR; no EDR; no PAM; weak physical controls at clinics | ⚠️ Partially Compliant |
| **Detect** | Identify cybersecurity events | Windows Event Logs; Epic audit trail | No SIEM; no behavioral analytics; no real-time alerting | ❌ Non-Compliant |
| **Respond** | Take action on detected incidents | Basic IR plan exists | IR plan untested; no formal CSIRT; limited forensic capability | ⚠️ Partially Compliant |
| **Recover** | Maintain resilience and restore after incidents | Veeam backups; BCP and DR plan exist | No secondary site; backups untested; BCP not exercised | ⚠️ Partially Compliant |

---

## 8. PCI-DSS — Key Requirements

<!-- 
PCI-DSS applies because TSHI accepts credit and debit card payments
for patient services. Failure to comply can result in losing
the ability to process card payments — devastating for revenue.
We document the most relevant requirements here rather than all 12
because full PCI compliance is outside the primary scope of this assessment
but its intersection with TSHI's security program is important to document.
-->

| Requirement ID | PCI-DSS Requirement | Requirement Description | Implemented Control | Status |
|---|---|---|---|---|
| PCI-001 | Requirement 1 | Install and maintain a firewall to protect cardholder data | NGFW deployed at perimeter | ✅ Compliant |
| PCI-002 | Requirement 2 | Do not use vendor-supplied defaults for passwords and security parameters | Default password change policy exists — not consistently enforced | ⚠️ Partially Compliant |
| PCI-003 | Requirement 3 | Protect stored cardholder data | Cardholder data not stored beyond processing — verified with payment vendor | ✅ Compliant |
| PCI-004 | Requirement 4 | Encrypt transmission of cardholder data across open networks | TLS encryption for all payment transactions | ✅ Compliant |
| PCI-005 | Requirement 5 | Use and regularly update anti-virus software | Microsoft Defender deployed and updated | ⚠️ Partially Compliant |
| PCI-006 | Requirement 6 | Develop and maintain secure systems and applications | Patch management inconsistent — gaps in third-party application patching | ⚠️ Partially Compliant |
| PCI-007 | Requirement 7 | Restrict access to cardholder data by business need to know | Access restricted to billing department — not formally reviewed | ⚠️ Partially Compliant |
| PCI-008 | Requirement 8 | Assign a unique ID to each person with computer access | Unique AD accounts enforced — MFA not deployed for payment systems | ⚠️ Partially Compliant |
| PCI-009 | Requirement 10 | Track and monitor all access to network resources and cardholder data | Access logging exists — not centrally monitored | ⚠️ Partially Compliant |
| PCI-010 | Requirement 12 | Maintain a policy that addresses information security | Information security policy partially developed | ⚠️ Partially Compliant |

---

## 9. Compliance Summary

<!-- 
This summary gives leadership and auditors a single-page view
of TSHI's overall compliance posture across all frameworks.
The numbers here tell a clear story — TSHI has more partial compliance
than full compliance, and several non-compliant areas.
This is realistic for a mid-size healthcare organization
that has not previously conducted a formal risk assessment.
The good news is that most gaps are Partially Compliant rather than Non-Compliant —
controls exist but need strengthening, documentation, or testing.
That is a much better starting point than having no controls at all.
-->

| Framework | Total Requirements | ✅ Compliant | ⚠️ Partially Compliant | ❌ Non-Compliant | 🔄 In Progress |
|---|---|---|---|---|---|
| HIPAA Administrative Safeguards | 20 | 2 | 14 | 0 | 4 |
| HIPAA Physical Safeguards | 10 | 3 | 7 | 0 | 0 |
| HIPAA Technical Safeguards | 10 | 4 | 6 | 0 | 0 |
| HITECH Breach Notification | 5 | 0 | 5 | 0 | 0 |
| NIST CSF 2.0 | 6 | 0 | 4 | 1 | 1 |
| PCI-DSS (Key Requirements) | 10 | 3 | 7 | 0 | 0 |
| **Total** | **61** | **12 (20%)** | **43 (70%)** | **1 (2%)** | **5 (8%)** |

**Key Finding:** TSHI has no fully non-compliant administrative or physical safeguards — controls exist but require strengthening, consistent application, and documentation. The most significant non-compliant area is the NIST CSF Detect function due to the absence of a SIEM. Remediation actions documented in the Risk Register will move the majority of Partially Compliant items toward full compliance.

---

## 10. Related Documents

| Document | Path |
|---|---|
| Risk Register | [../Risk/Risk_Register.md](../Risk/Risk_Register.md) |
| Regulatory Framework | [../Organization/Regulatory_Framework.md](../Organization/Regulatory_Framework.md) |
| Risk Rating Matrix | [Risk_Rating_Matrix.md](Risk_Rating_Matrix.md) |
| NIST Control Mapping | [../Annexes/Annex_B_NIST_Control_Mapping.md](../Annexes/Annex_B_NIST_Control_Mapping.md) |
| Risk Assessment Policy | [../Docs/Risk_Assessment_Policy.md](../Docs/Risk_Assessment_Policy.md) |

---

*Document ID: TSHI-MAT-CM-001 | Version: 1.0 | Classification: Internal Use Only — Confidential | Case Study — Tri-State Health Initiative (TSHI)*
