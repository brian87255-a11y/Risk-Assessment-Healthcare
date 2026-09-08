<!-- 
WHAT IS THIS FILE?
This is TSHI's Access Control Policy — the formal document that governs
how access to systems and data is granted, managed, and revoked.
Access control is one of the most fundamental security concepts
and one of the most heavily scrutinized areas in a HIPAA audit.
The HIPAA Security Rule requires access controls under both
Administrative Safeguards (164.308(a)(3) and 164.308(a)(4))
and Technical Safeguards (164.312(a)(1)).
This policy directly addresses several of the gaps identified
in the risk assessment — particularly the lack of formal access reviews,
inconsistent offboarding, and the absence of MFA on the EHR system.
In a real organization this policy would be reviewed and approved
by the CISO and signed by executive leadership before being distributed.
Policies without executive approval lack organizational authority
and may not be enforceable.
-->

# Access Control Policy — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-POL-AC-001
**Version:** 1.0
**Classification:** Internal Use Only
**Effective Date:** August 2026
**Review Date:** August 2027
**Owner:** Chief Information Security Officer (CISO)
**Approved By:** Chief Executive Officer (CEO)

---

## 1. Purpose

<!-- 
The purpose statement answers: why does this policy exist?
Access control policy exists because not everyone in an organization
should have access to everything.
The principle of least privilege — one of the most important concepts
in information security — says that users should have only the access
they need to do their job and nothing more.
This reduces the damage an attacker can do with a compromised account
and limits the harm an insider can cause intentionally or accidentally.
-->

The purpose of this policy is to establish the requirements for controlling access to Tri-State Health Initiative (TSHI) information systems, applications, and data. This policy ensures that access to electronic Protected Health Information (ePHI) and other sensitive organizational data is granted based on legitimate business need, managed throughout the user lifecycle, and revoked promptly when no longer required.

This policy supports compliance with:
- HIPAA Security Rule — 45 CFR § 164.308(a)(3), 164.308(a)(4), 164.312(a)(1)
- NIST SP 800-53 Rev. 5 — Access Control (AC) Control Family
- NIST Cybersecurity Framework 2.0 — Protect Function

---

## 2. Scope

This policy applies to:

| In Scope | Description |
|---|---|
| All workforce members | Employees, contractors, volunteers, and vendors with access to TSHI systems |
| All information systems | Clinical, administrative, and infrastructure systems across all four TSHI facilities |
| All data classifications | Systems containing ePHI, PII, Confidential, and Internal data |
| All access methods | On-site, remote, and third-party vendor access |

---

## 3. Access Control Principles

<!-- 
These four principles are the foundation of access control.
They are referenced throughout the policy and should be understood cold.
Least Privilege — only the access needed for the job, nothing more
Need to Know — even within an authorized role, access is limited to specific data needed
Separation of Duties — no single person controls an entire critical process
Account Lifecycle Management — access is actively managed from creation to termination
These principles appear constantly in security certifications,
job interviews, and real-world security work.
-->

All access control decisions at TSHI are governed by the following core principles:

| Principle | Definition | Application at TSHI |
|---|---|---|
| **Least Privilege** | Users are granted the minimum access rights necessary to perform their job duties | EHR access roles are defined by clinical function — a billing clerk does not have access to clinical notes |
| **Need to Know** | Access to specific information is granted only when required to perform an assigned task | A nurse at the North Clinic accesses only patients assigned to that clinic |
| **Separation of Duties** | No single individual controls an entire critical process end-to-end | System administrators cannot both approve and implement their own changes |
| **Account Lifecycle Management** | Access rights are actively managed from initial provisioning through modification to termination | All access changes follow a documented provisioning and deprovisioning process |

---

## 4. User Account Management

<!-- 
User account management covers the full lifecycle of a user account —
from creation when someone joins the organization
to modification when their role changes
to termination when they leave.
Each phase has specific requirements that must be followed
to ensure access is appropriate at every point in the lifecycle.
The most critical phase from a security perspective is termination —
former employee accounts that remain active are a known attack vector
and a HIPAA compliance issue.
-->

### 4.1 Account Provisioning

| Requirement | Description |
|---|---|
| Authorization | All new accounts must be formally requested and approved by the user's direct manager and the IT department before creation |
| Role Assignment | Access must be assigned based on job role — access requests must specify the business justification for each system and permission level |
| Minimum Access | Initial access must follow the principle of least privilege — additional access may be requested separately with documented justification |
| Documentation | All provisioning requests must be documented and retained for a minimum of six years in accordance with HIPAA retention requirements |
| Unique Accounts | All users must be assigned unique individual accounts — shared accounts are prohibited except for emergency access accounts specifically designated for that purpose |

### 4.2 Account Modification

| Requirement | Description |
|---|---|
| Role Change | When a user changes roles, access must be reviewed within five business days — access appropriate to the old role must be removed and new role-appropriate access provisioned |
| Access Escalation | Requests for access beyond standard role permissions require written approval from the department head and CISO |
| Temporary Access | Temporary access grants must specify an expiration date and be automatically revoked upon expiration |

### 4.3 Account Termination

<!-- 
This section is one of the most important in the entire policy
because terminated employee accounts are one of the most exploited
vulnerabilities in real-world breaches.
An ex-employee who knows their credentials still work
can cause significant damage — and they already know the systems.
The 24-hour requirement for voluntary terminations
and immediate requirement for involuntary terminations
reflect real industry best practices.
Involuntary terminations (firings) are treated differently
because a disgruntled employee who knows they are being fired
has both the motive and the window to cause harm
if access is not cut immediately.
-->

| Termination Type | Access Revocation Requirement |
|---|---|
| Voluntary Resignation | All system access must be revoked within 24 hours of the effective termination date |
| Involuntary Termination | All system access must be revoked immediately upon notification of termination — prior to or simultaneous with the employee being informed |
| Contractor / Vendor Offboarding | All access must be revoked within 24 hours of contract end or relationship termination |
| Role Transfer | Access associated with the previous role must be revoked within 5 business days of role change |

**Termination Checklist — IT Responsibilities:**

| Action | Responsible Party | Timeline |
|---|---|---|
| Disable Active Directory account | IT Help Desk | Immediate / 24 hours |
| Revoke Epic EHR access | IT / Clinical Systems Team | Immediate / 24 hours |
| Revoke Microsoft 365 license and access | IT Help Desk | Immediate / 24 hours |
| Revoke VPN credentials | IT Infrastructure Team | Immediate / 24 hours |
| Revoke physical badge access | Facilities / Security | Immediate / 24 hours |
| Recover TSHI-issued devices | HR / IT | Within 5 business days |
| Review and transfer data ownership | IT / Department Manager | Within 5 business days |
| Document completion in HR system | HR | Within 5 business days |

### 4.4 Privileged Accounts

<!-- 
Privileged accounts are accounts with elevated permissions —
system administrators, database administrators, network engineers.
These accounts are the highest-value targets in any network
because compromising one gives an attacker broad access
to systems and the ability to cover their tracks.
Privileged accounts require stronger controls than standard user accounts
because the consequences of compromise are much more severe.
The use of separate privileged accounts (not using the same account
for daily email as for system administration) is a fundamental
principle of privileged access management.
-->

| Requirement | Description |
|---|---|
| Separate Accounts | All IT staff with administrative privileges must maintain separate standard user accounts for daily tasks and dedicated privileged accounts for administrative work |
| MFA Enforcement | Multi-factor authentication is required for all privileged account logins without exception |
| Privileged Account Logging | All privileged account activity must be logged and retained for a minimum of 90 days |
| No Shared Admin Accounts | Shared administrative accounts are prohibited — each privileged user must have their own individually identified privileged account |
| Just-In-Time Access | Where technically feasible privileged access should be granted on a just-in-time basis and automatically revoked after the task is complete |
| Annual Review | All privileged accounts must be reviewed and reauthorized annually by the CISO |

---

## 5. Authentication Requirements

<!-- 
Authentication is the process of verifying that a user is who they claim to be.
This section defines the minimum authentication standards for all TSHI systems.
The most important requirement here is MFA — multi-factor authentication.
MFA is the single most effective control against credential-based attacks
because even if an attacker steals a password,
they cannot authenticate without the second factor.
Microsoft reports that MFA blocks over 99% of automated credential attacks.
The fact that TSHI does not have MFA on the EHR is the most critical
technical gap identified in this entire assessment.
-->

### 5.1 Password Requirements

| Requirement | Standard |
|---|---|
| Minimum Length | 12 characters |
| Complexity | Must contain at least one uppercase letter, one lowercase letter, one number, and one special character |
| Password History | Cannot reuse the last 12 passwords |
| Maximum Age | Passwords must be changed every 90 days for standard accounts; 60 days for privileged accounts |
| Account Lockout | Account must be locked after 5 consecutive failed login attempts; lockout duration minimum 15 minutes |
| Prohibited Passwords | Common passwords, dictionary words, and passwords containing the user's name or username are prohibited |

### 5.2 Multi-Factor Authentication Requirements

<!-- 
MFA combines two or more authentication factors from different categories:
Something you know (password, PIN)
Something you have (hardware token, smartphone app, smart card)
Something you are (fingerprint, face scan, retina)
Requiring two factors from different categories means an attacker
needs to compromise both — significantly harder than stealing one password.
The phased rollout approach here is realistic —
deploying MFA to all 1,200 users simultaneously is operationally complex.
Prioritizing the highest-risk access points first (EHR, admin accounts, VPN)
is the right security strategy.
-->

MFA is required for the following access points — phased implementation based on risk priority:

| Phase | Systems Requiring MFA | Timeline | Priority |
|---|---|---|---|
| Phase 1 — Immediate | Epic EHR, all Active Directory privileged accounts, Microsoft 365 admin accounts | Within 30 days | Critical |
| Phase 2 — Short-term | VPN remote access (already partially deployed — expand to all users), Microsoft 365 all users | Within 90 days | High |
| Phase 3 — Medium-term | All remaining internal systems, vendor remote access accounts | Within 6 months | Moderate |

Acceptable MFA methods at TSHI:

| MFA Method | Acceptable | Notes |
|---|---|---|
| Authenticator App (TOTP) | ✅ Yes | Preferred method — Microsoft Authenticator or equivalent |
| Hardware Security Key | ✅ Yes | Recommended for privileged accounts |
| SMS One-Time Password | ⚠️ Conditional | Acceptable as secondary option — not preferred due to SIM-swap risk |
| Email One-Time Password | ❌ No | Not acceptable — email account may itself be compromised |
| Security Questions | ❌ No | Not acceptable — does not constitute a true second factor |

---

## 6. Access Reviews

<!-- 
Access reviews are periodic audits of who has access to what
to ensure that access rights remain appropriate over time.
Without regular access reviews organizations accumulate
"access creep" — users accumulate permissions over time
as roles change but old access is never removed.
A user who started in billing, moved to clinical, and then became a manager
might still have billing system access, clinical records access,
AND manager-level admin rights — far more than any one role needs.
Access reviews catch and correct this.
HIPAA requires periodic evaluation of access rights
under the Workforce Security and Information Access Management standards.
-->

| Review Type | Scope | Frequency | Responsible Party |
|---|---|---|---|
| EHR Access Review | All Epic user accounts and access levels | Quarterly | CISO / Clinical Systems Team |
| Privileged Account Review | All Active Directory admin and privileged accounts | Quarterly | CISO / IT Director |
| General System Access Review | All standard user accounts across major systems | Annually | IT Director / Department Managers |
| Vendor Access Review | All third-party vendor accounts with system access | Semi-annually | CISO / Compliance Officer |
| Terminated User Audit | Verify all terminated user accounts have been fully revoked | Monthly | IT Help Desk / HR |

**Access Review Process:**

```
Step 1: Generate access report for the system under review
Step 2: Distribute report to relevant department managers for validation
Step 3: Department managers certify that each user's access is appropriate
        for their current role or flag accounts for modification/removal
Step 4: IT implements all changes within 5 business days of certification
Step 5: Document completion and retain records for 6 years
```

---

## 7. Remote Access

<!-- 
Remote access — accessing TSHI systems from outside the network —
introduces additional risk because traffic travels over untrusted networks.
The COVID-19 pandemic dramatically accelerated remote work in healthcare,
and with it, the attack surface for credential theft and VPN exploitation.
TSHI uses Cisco AnyConnect VPN for remote access —
this is appropriate but must be combined with MFA
which is currently only partially deployed.
-->

| Requirement | Description |
|---|---|
| VPN Required | All remote access to TSHI internal systems must be conducted through the approved VPN — direct internet-facing system access is prohibited |
| MFA Required | MFA must be enforced for all VPN connections — password-only VPN access is not permitted |
| Approved Devices Only | Remote access must be conducted from TSHI-issued devices or personally-owned devices that have been registered and approved by IT |
| No Split Tunneling | VPN must be configured to route all traffic through the TSHI network — split tunneling that allows simultaneous internet browsing is prohibited |
| Session Logging | All remote access sessions must be logged including user identity, duration, and systems accessed |

---

## 8. Third-Party and Vendor Access

<!-- 
Vendors often need remote access to TSHI systems to provide support.
This is legitimate and necessary — but it must be controlled.
Unmonitored vendor access is a primary supply chain attack vector.
The attacker in the 2013 Target breach gained initial access
through credentials stolen from an HVAC vendor.
Healthcare has seen similar attacks where EHR vendor access
was used as a pathway into hospital networks.
Just-in-time access — granting access only when needed
and automatically revoking it afterward — is the gold standard
for vendor access management.
-->

| Requirement | Description |
|---|---|
| Formal Request | All vendor access requests must be formally submitted, reviewed, and approved by the CISO before access is granted |
| MFA Required | All vendor accounts must use MFA — password-only vendor access is prohibited |
| Minimum Access | Vendor access must be limited to only the systems and functions required to perform the contracted service |
| Session Monitoring | All vendor remote access sessions must be logged and available for audit review |
| Time-Limited Access | Vendor access must be granted for a defined period and automatically expire — standing permanent access is prohibited except where operationally required with CISO approval |
| Business Associate Agreement | All vendors with access to systems containing ePHI must have a signed BAA on file prior to access being granted |

---

## 9. Policy Violations

| Violation | Consequence |
|---|---|
| Sharing login credentials | Disciplinary action up to and including termination |
| Accessing ePHI without authorization | Disciplinary action up to and including termination; potential criminal referral |
| Failure to report unauthorized access | Disciplinary action |
| Circumventing MFA or access controls | Disciplinary action up to and including termination; potential criminal referral |
| Vendor providing access to unauthorized parties | Immediate termination of vendor contract and BAA; potential legal action |

---

## 10. Related Documents

| Document | Path |
|---|---|
| Risk Assessment Policy | [../Docs/Risk_Assessment_Policy.md](../Docs/Risk_Assessment_Policy.md) |
| Data Classification Policy | [Data_Classification_Policy.md](Data_Classification_Policy.md) |
| Incident Response Policy | [Incident_Response_Policy.md](Incident_Response_Policy.md) |
| RACI Matrix | [../Annexes/Annex_A_RACI_Matrix.md](../Annexes/Annex_A_RACI_Matrix.md) |
| Compliance Matrix | [../Matrices/Compliance_Matrix.md](../Matrices/Compliance_Matrix.md) |

---

*Document ID: TSHI-POL-AC-001 | Version: 1.0 | Classification: Internal Use Only | Effective: August 2026 | Case Study — Tri-State Health Initiative (TSHI)*
