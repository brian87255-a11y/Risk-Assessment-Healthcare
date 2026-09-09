<!-- 
WHAT IS THIS FILE?
This is TSHI's Data Classification Policy — the formal document that defines
how TSHI categorizes its data based on sensitivity and the handling
requirements that apply to each category.
Data classification is foundational to security because it answers
the question: how much protection does this data need?
Not all data is equally sensitive — a published press release and
a patient's psychiatric records should not be protected the same way.
Classification allows TSHI to apply the right level of security
to the right data rather than either over-protecting everything
(expensive and operationally impractical) or under-protecting everything
(a compliance and security disaster).
The gap identified in the risk assessment was that TSHI has a data
classification policy in draft form that is not consistently enforced —
staff may handle sensitive data without appropriate care.
This policy formalizes and operationalizes that classification.
HIPAA does not mandate a specific classification scheme
but it does require that ePHI be identified and appropriately protected —
this policy is how TSHI fulfills that obligation.
-->

# Data Classification Policy — Tri-State Health Initiative 

**Document ID: TSHI-POL-DC-001
Version: 1.0
Classification: Internal Use Only
Effective Date: August 2026
Review Date: August 2027
Owner: Chief Information Security Officer (CISO)
Approved By: Chief Executive Officer (CEO)**

---

## 1. Purpose

<!-- 
The purpose of data classification is to ensure that the right protections
are applied to the right data — not too much, not too little.
In healthcare this is especially important because ePHI requires
specific protections under HIPAA that other data types do not.
Having a clear classification policy also helps employees understand
how to handle the data they work with every day —
"is this something I can email to a vendor?" becomes answerable
once you know what classification the data falls into.
-->

This policy establishes TSHI's data classification framework — defining categories of data based on sensitivity, the handling requirements that apply to each category, and the roles responsible for classification and compliance.

Effective data classification enables TSHI to:
- Apply appropriate security controls based on data sensitivity
- Ensure staff understand how to handle different types of information
- Meet regulatory requirements for protecting ePHI, PII, and financial data
- Reduce the risk of accidental or intentional data exposure

This policy supports compliance with:
- HIPAA Privacy Rule — 45 CFR Part 164, Subpart E
- HIPAA Security Rule — 45 CFR Part 164, Subpart C
- HITECH Act — Breach Notification Requirements
- New Jersey Identity Theft Prevention Act
- New York SHIELD Act

---

## 2. Scope

This policy applies to all data created, received, maintained, transmitted, or stored by TSHI regardless of format or medium — including electronic files, physical documents, verbal communications, and data held by third-party vendors on TSHI's behalf.

---

## 3. Data Roles and Responsibilities

<!-- 
Data roles define who is responsible for what when it comes to data.
The three most important roles are Data Owner, Data Custodian, and Data User.
These roles are commonly tested on security certifications and
come up frequently in interviews because they represent a
fundamental governance concept.
Data Owner — the business person who decides how the data should be used
             and what classification it receives. Not necessarily IT.
Data Custodian — usually IT — responsible for technically protecting the data
                per the owner's instructions.
Data User — anyone who uses the data to do their job.
The distinction between owner and custodian is important.
A doctor is the data owner of patient records they create —
they decide who needs access. IT is the custodian —
they implement the technical controls to enforce that decision.
-->

| Role | Description | Responsibilities |
|---|---|---|
| **Data Owner** | The senior business or clinical leader responsible for a category of data | Assign and approve data classification; authorize access; ensure compliance with handling requirements |
| **Data Custodian** | Typically IT — the party responsible for technically storing and protecting data per the owner's instructions | Implement technical controls; maintain backup and recovery; enforce access controls defined by data owner |
| **Data User** | Any workforce member who accesses and uses data to perform their job duties | Handle data in accordance with its classification; report unauthorized disclosures; complete required training |
| **Compliance Officer** | Ensures data handling practices meet regulatory requirements | Monitor compliance; conduct audits; report violations; manage regulatory notifications |

**Data Ownership by Category:**

| Data Category | Data Owner | Primary Custodian |
|---|---|---|
| Electronic Protected Health Information (ePHI) | Chief Medical Officer | IT Director / Clinical Systems Team |
| Patient Demographic and Identity Information | Chief Medical Officer | IT Director |
| Financial and Billing Data | Chief Financial Officer | IT Director / Finance |
| Employee Records | HR Director | IT Director / HR |
| Network and System Configuration | IT Director | IT Infrastructure Team |
| Research and Operational Data | Department Heads | IT Director |

---

## 4. Data Classification Levels

<!-- 
TSHI uses four classification levels — Critical, Confidential, Internal, and Public.
These map to the sensitivity of the data and the harm that would result
from unauthorized disclosure.
The most important level for TSHI is Critical — which covers ePHI.
ePHI receives the highest classification because:
1. HIPAA specifically requires it to be protected with administrative,
   physical, and technical safeguards
2. Unauthorized disclosure triggers mandatory breach notification
3. Each exposed record represents direct harm to a patient
4. Penalties can reach $1.9 million per violation category per year
Understanding that ePHI = Critical = maximum protection
is fundamental for anyone working in healthcare security.
-->

### Level 1 — Critical

| Field | Details |
|---|---|
| **Definition** | Highly sensitive data whose unauthorized disclosure, modification, or destruction would cause severe harm to patients, significant regulatory penalties, or serious operational damage to TSHI |
| **Examples** | Electronic Protected Health Information (ePHI), patient diagnoses, medication records, mental health records, HIV/AIDS status, substance abuse treatment records, medical imaging, lab results, genetic information |
| **Regulatory Requirement** | HIPAA Security Rule, HIPAA Privacy Rule, HITECH Act, 42 CFR Part 2 (substance abuse records) |
| **Default Access** | Strictly controlled — granted only to workforce members with a direct patient care or treatment relationship, or specific administrative need |

**Critical Data Handling Requirements:**

| Requirement | Standard |
|---|---|
| Storage | Must be stored on TSHI-approved encrypted systems only — personal devices prohibited without approved MDM enrollment |
| Transmission | Must be encrypted in transit using TLS 1.2 or higher — unencrypted email transmission is prohibited |
| Access Control | Role-based access with MFA required — access must be formally authorized and documented |
| Physical Security | Physical documents containing Critical data must be stored in locked cabinets — not left unattended |
| Printing | Minimize printing of Critical data — printed copies must be shredded using cross-cut shredder when no longer needed |
| Sharing | May only be shared with authorized workforce members, Business Associates with signed BAAs, or per patient authorization |
| Third-Party Transmission | Must use secure file transfer — no unencrypted email attachments or public file-sharing services |
| Disposal | Electronic: DOD 5220.22-M standard overwrite or physical destruction; Physical: cross-cut shredding or certified destruction |
| Retention | Minimum 6 years per HIPAA; longer per applicable state law |

### Level 2 — Confidential

| Field | Details |
|---|---|
| **Definition** | Sensitive organizational data whose unauthorized disclosure would cause significant harm to TSHI's operations, finances, reputation, or workforce members |
| **Examples** | Employee records, payroll data, financial statements, vendor contracts, system configuration data, security logs, audit reports, legal correspondence, unreleased organizational announcements |
| **Regulatory Requirement** | Privacy Act, NJ/NY state employment and privacy laws, PCI-DSS (financial data) |
| **Default Access** | Restricted — granted based on job role and documented business need |

**Confidential Data Handling Requirements:**

| Requirement | Standard |
|---|---|
| Storage | Must be stored on TSHI-approved systems — personal devices require CISO approval |
| Transmission | Encryption strongly recommended — must not be transmitted via unencrypted email if it contains financial account details or employee PII |
| Access Control | Role-based access — access authorization required from data owner or department head |
| Physical Security | Physical documents must not be left unattended in public or shared spaces |
| Sharing | May be shared internally on a need-to-know basis; external sharing requires management approval |
| Disposal | Electronic: secure deletion or overwrite; Physical: shredding |
| Retention | Per applicable regulatory or business retention requirements |

### Level 3 — Internal

| Field | Details |
|---|---|
| **Definition** | Data intended for internal TSHI use only — disclosure outside the organization would be inappropriate but would not cause significant harm |
| **Examples** | Internal policies and procedures, meeting minutes, general operational communications, non-sensitive project documentation, internal announcements, training materials |
| **Regulatory Requirement** | No specific regulatory requirement — general organizational confidentiality |
| **Default Access** | Available to all TSHI workforce members — not for external distribution |

**Internal Data Handling Requirements:**

| Requirement | Standard |
|---|---|
| Storage | May be stored on any TSHI-approved system or collaboration platform |
| Transmission | May be transmitted via TSHI email systems — care should be taken when sending externally |
| Access Control | Available to all workforce members by default — department-specific data may be restricted |
| Sharing | Not for distribution outside TSHI without management approval |
| Disposal | Standard deletion — no special disposal requirements |

### Level 4 — Public

| Field | Details |
|---|---|
| **Definition** | Data explicitly intended for public disclosure — no restriction on access or distribution |
| **Examples** | TSHI public website content, published press releases, provider directories, approved marketing materials, public health information |
| **Regulatory Requirement** | None — subject to TSHI communications and brand standards only |
| **Default Access** | Available to anyone |

**Public Data Handling Requirements:**

| Requirement | Standard |
|---|---|
| Authorization | Must be explicitly approved for public release by TSHI communications or relevant department head |
| Accuracy | Must be accurate and current — outdated public information must be removed or corrected |
| No Embedding | Public materials must not embed or reference Critical or Confidential data |

---

## 5. Special Data Categories

<!-- 
Some types of ePHI receive additional protections beyond standard HIPAA requirements.
These special categories carry heightened stigma and legal protections
because disclosure can cause unique harms — discrimination, lost employment,
damaged relationships, or safety risks.
For example, mental health records in New Jersey are protected
by state law that is MORE restrictive than HIPAA — meaning HIPAA compliance
alone is not sufficient for mental health data.
Similarly, substance abuse treatment records are governed by
42 CFR Part 2 which has stricter disclosure requirements than HIPAA.
Knowing that some data receives extra-extra protection is important
for anyone working in healthcare security.
-->

Certain categories of ePHI receive heightened protection beyond standard Critical data requirements due to the sensitive nature of the information and additional regulatory protections:

| Special Category | Additional Regulation | Extra Handling Requirements |
|---|---|---|
| Mental Health Records | NJ Mental Health Records Law; HIPAA | Requires specific patient authorization for most disclosures — more restrictive than standard HIPAA |
| Substance Abuse Treatment Records | 42 CFR Part 2 | Stricter consent requirements than HIPAA — separate authorization required for disclosure |
| HIV/AIDS Status | NJ AIDS Assistance Act | Disclosure requires specific written consent in most circumstances |
| Genetic Information | GINA (Genetic Information Nondiscrimination Act) | Cannot be used for employment or insurance discrimination |
| Minor Patient Records | HIPAA + NJ/NY state law | Parents' rights to access minor records vary by age and situation |
| Psychotherapy Notes | HIPAA Privacy Rule | Requires separate authorization from general medical record release |

---

## 6. Data Classification in Practice

<!-- 
Knowing classifications exist is not enough — staff need to know
how to apply them in their daily work.
This section gives practical guidance for common scenarios.
The "when in doubt" rule is important — if you are not sure
what classification something is, treat it as one level higher
than you think it might be. It is better to over-protect
than to under-protect and cause a breach.
-->

### 6.1 How to Classify Data

```
Step 1: Identify what type of information the data contains
        → Does it contain patient health information? → Critical
        → Does it contain employee or financial data? → Confidential
        → Is it for internal use only? → Internal
        → Is it approved for public release? → Public

Step 2: If multiple types are present, use the highest classification
        → A document containing both Internal meeting notes and ePHI = Critical

Step 3: When uncertain, classify one level higher than you think
        → Treat uncertain data as more sensitive until confirmed otherwise

Step 4: Apply the handling requirements for that classification level
        → Storage, transmission, access, sharing, disposal
```

### 6.2 Common Scenarios

| Scenario | Correct Classification | Rationale |
|---|---|---|
| Patient lab results emailed to a physician | Critical | Contains ePHI — must be encrypted |
| Employee salary information in HR system | Confidential | Contains employee PII and financial data |
| TSHI's annual report published on website | Public | Explicitly approved for public release |
| Internal IT infrastructure diagram | Confidential | System configuration data — security sensitive |
| Patient appointment reminder sent via portal | Critical | Contains patient identity and appointment linked to health condition |
| TSHI staff meeting agenda | Internal | Internal operational data — not sensitive |
| Vendor contract containing pricing | Confidential | Sensitive business data — not for external distribution |
| Patient discharge instructions | Critical | Contains ePHI — treatment information |

---

## 7. Data Handling During Incidents

| Situation | Required Action |
|---|---|
| Lost or stolen device containing Critical data | Report immediately to IT Help Desk and CISO — incident response procedures are activated |
| Accidental email of Critical data to wrong recipient | Report immediately to CISO — HIPAA breach assessment required |
| Discovery of Critical data in an unsecured location | Secure the data immediately — report to CISO for breach assessment |
| Vendor requesting data beyond their BAA scope | Deny the request — escalate to CISO and Legal |

---

## 8. Training and Awareness

| Requirement | Details |
|---|---|
| Initial Training | All new workforce members must complete data classification training before accessing TSHI systems |
| Annual Refresher | All workforce members must complete annual data classification refresher training |
| Role-Specific Training | Clinical staff, IT staff, and administrative staff receive role-specific training on handling data relevant to their work |
| Acknowledgment | All workforce members must sign an annual acknowledgment confirming they have read, understood, and will comply with this policy |

---

## 9. Policy Violations

| Violation | Consequence |
|---|---|
| Transmitting Critical data via unencrypted email | Disciplinary action; potential HIPAA breach investigation |
| Storing Critical data on personal devices without authorization | Disciplinary action; mandatory device review |
| Sharing Confidential data with unauthorized parties | Disciplinary action; potential legal action |
| Failure to report a known or suspected data exposure | Disciplinary action up to and including termination |
| Deliberate misclassification of data to bypass controls | Disciplinary action up to and including termination |

---

## 10. Related Documents

| Document | Path |
|---|---|
| Access Control Policy | [Access_Control_Policy.md](Access_Control_Policy.md) |
| Incident Response Policy | [Incident_Response_Policy.md](Incident_Response_Policy.md) |
| Regulatory Framework | [../Organization/Regulatory_Framework.md](../Organization/Regulatory_Framework.md) |
| Asset Inventory | [../Risk/Asset_Inventory.md](../Risk/Asset_Inventory.md) |
| Compliance Matrix | [../Matrices/Compliance_Matrix.md](../Matrices/Compliance_Matrix.md) |

---

*Document ID: TSHI-POL-DC-001 | Version: 1.0 | Classification: Internal Use Only | Effective: August 2026 | Case Study — Tri-State Health Initiative (TSHI)*
