<!-- 
WHAT IS THIS FILE?
This is the RACI Matrix — a governance tool that defines
who is Responsible, Accountable, Consulted, and Informed
for every major security activity in TSHI's risk assessment program.
RACI stands for:
R — Responsible: the person or team who DOES the work
A — Accountable: the person who OWNS the outcome and is answerable for it
    (there should be only ONE accountable person per activity)
C — Consulted: people whose input is sought BEFORE decisions are made
    (two-way communication)
I — Informed: people who are kept updated AFTER decisions are made
    (one-way communication)
The RACI matrix solves one of the most common organizational problems:
"I thought YOU were doing that."
When roles are ambiguous, tasks fall through the cracks.
When everyone is accountable, no one is accountable.
The RACI matrix makes accountability explicit and unambiguous.
In the context of a risk assessment this matters because
security activities span multiple departments —
IT, clinical operations, compliance, legal, HR, and executive leadership
all have roles to play.
Without a RACI, each group assumes someone else is handling it.
This is a standard deliverable in professional security governance programs
and appears in the reference repo you used as a model.
-->

# Annex A — RACI Matrix — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-ANX-RACI-001
**Version:** 1.0
**Classification:** Internal Use Only
**Last Updated:** August 2026
**Owner:** Chief Information Security Officer (CISO)

---

## 1. Purpose

<!-- 
This document provides clarity on who does what across TSHI's
information security and risk management program.
It prevents the two most common governance failures:
1. Duplication — multiple teams doing the same thing independently
2. Gaps — no one doing something because everyone assumed someone else was
In a real organization the RACI matrix is often the output
of a governance workshop where key stakeholders negotiate and agree
on their respective roles. That negotiation process is itself valuable
because it surfaces assumptions and disagreements before they become problems.
-->

This RACI Matrix defines roles and responsibilities across TSHI's information security risk assessment program and ongoing security governance activities. It ensures that every significant security activity has a clearly identified owner, executor, and set of stakeholders.

---

## 2. Role Definitions

<!-- 
These are the specific roles referenced throughout the RACI matrix.
Note that roles are organizational positions, not individuals.
If the CISO leaves, the role and its responsibilities remain —
only the person filling the role changes.
This is an important distinction in governance documentation.
-->

| Role | Title | Description |
|---|---|---|
| CEO | Chief Executive Officer | Ultimate organizational authority — accountable for organizational risk posture |
| COO | Chief Operating Officer | Responsible for operational continuity and facility management |
| CIO | Chief Information Officer | Responsible for overall IT strategy and investment |
| CISO | Chief Information Security Officer | Owns the information security program — primary accountability for security governance |
| IT Director | IT Director | Responsible for IT operations, infrastructure, and technical implementation |
| IST | Information Security Team | Technical security analysts responsible for assessment and monitoring activities |
| CO | Compliance Officer | Responsible for regulatory compliance and breach notification |
| CMO | Chief Medical Officer | Clinical leadership — accountable for patient safety during system disruptions |
| HR | HR Director | Responsible for workforce security and personnel actions |
| Legal | General Counsel | Advises on legal obligations and regulatory requirements |
| DH | Department Heads | Responsible for security within their respective departments |
| All Staff | All Workforce Members | Responsible for following security policies in daily work |

---

## 3. RACI — Risk Assessment Activities

<!-- 
This section covers the specific activities that make up
the NIST SP 800-30 risk assessment process.
Note that the CISO is Accountable for most activities —
meaning they own the outcome and are answerable to executive leadership
even when other teams do the actual work.
This is appropriate because the CISO is the designated security official
required by HIPAA Security Rule 45 CFR § 164.308(a)(2).
-->

| Activity | CEO | COO | CIO | CISO | IT Director | IST | CO | CMO | HR | Legal | DH |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Approve risk assessment policy | A | | | R | | | C | | | C | |
| Define assessment scope and objectives | | | C | A | C | R | C | C | | | |
| Conduct asset inventory | | | I | A | C | R | | C | C | | C |
| Identify threat sources and events | | | I | A | C | R | C | | | | |
| Identify vulnerabilities | | | I | A | R | R | | | | | |
| Determine likelihood ratings | | | | A | C | R | | | | | |
| Determine impact ratings | | | C | A | C | R | C | C | | | |
| Calculate risk ratings | | | I | A | C | R | C | | | | |
| Develop remediation recommendations | | | C | A | R | R | C | C | | | |
| Present risk assessment findings to leadership | I | I | I | R | C | C | C | I | | I | |
| Approve risk treatment decisions | A | C | C | R | | | C | | | | |
| Formally accept residual risks | A | | | R | | | C | | | C | |
| Maintain and update risk register | | | | A | C | R | C | | | | |
| Conduct annual reassessment | I | I | I | A | C | R | C | | | | |

---

## 4. RACI — Access Control Activities

| Activity | CEO | COO | CIO | CISO | IT Director | IST | CO | CMO | HR | Legal | DH | All Staff |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Define access control policy | | | C | A | C | R | C | | | C | | |
| Approve user access requests | | | | C | A | R | | | | | C | |
| Provision new user accounts | | | | I | A | R | | | I | | | |
| Modify user access on role change | | | | I | A | R | | | R | | C | |
| Revoke access upon termination | | | | I | A | R | | | R | | | |
| Enforce MFA deployment | | | | A | R | R | | | | | | |
| Conduct quarterly EHR access reviews | | | | A | C | R | C | C | | | C | |
| Conduct annual access recertification | | | | A | R | R | C | | C | | C | |
| Manage vendor remote access | | | | A | R | R | C | | | C | | |
| Review and audit privileged accounts | | | | A | C | R | | | | | | |

---

## 5. RACI — Incident Response Activities

<!-- 
Incident response is the area where RACI confusion causes the most damage.
During an active incident people are stressed, communication is chaotic,
and decisions need to be made fast.
If roles are not pre-defined, the wrong people make decisions,
the right people are not consulted, and critical steps are missed.
The CISO as Incident Commander has authority to make final calls
on containment, communication, and escalation during active incidents.
This authority must be established in advance — not negotiated during a breach.
-->

| Activity | CEO | COO | CIO | CISO | IT Director | IST | CO | CMO | HR | Legal | DH | All Staff |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Define incident response policy | | | C | A | C | R | C | | | C | | |
| Maintain incident response plan | | | | A | C | R | C | | | | | |
| Conduct IR tabletop exercises | I | C | C | A | C | R | C | C | | | C | |
| Detect and triage security events | | | | C | C | A/R | | | | | | |
| Declare security incident | | | | A | C | R | C | | | | | |
| Activate CSIRT | | C | C | A/R | R | R | R | C | | C | | |
| Execute containment actions | | | C | A | R | R | | | | | | |
| Notify executive leadership of P1/P2 incidents | R | R | R | A | | | C | R | | | | |
| Manage external communications during incident | A | C | | R | | | C | C | | C | | |
| Conduct HIPAA breach risk assessment | | | | C | | C | A/R | | | C | | |
| Execute breach notification | | | | C | | | A/R | | | R | | |
| Conduct lessons-learned review | | C | C | A | R | R | C | C | | | | |
| Update IR plan post-incident | | | | A | C | R | C | | | | | |

---

## 6. RACI — Business Continuity Activities

| Activity | CEO | COO | CIO | CISO | IT Director | IST | CO | CMO | HR | Legal | DH | All Staff |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Define BC policy | A | C | C | R | C | | C | C | | C | | |
| Conduct Business Impact Analysis | I | C | C | A | C | R | C | C | C | | C | |
| Develop clinical downtime procedures | | | | C | C | | | A | | | R | |
| Maintain backup infrastructure | | | | C | A | R | | | | | | |
| Test backup restoration | | | | A | R | R | | | | | | |
| Conduct BC tabletop exercises | I | R | C | A | C | R | C | R | | | R | |
| Activate clinical downtime procedures | | A | | C | R | | | R | | | R | R |
| Declare disaster and activate BC plan | A | R | R | C | C | | C | R | | C | | |
| Manage recovery operations | | C | A | C | R | R | | C | | | C | |
| Conduct post-event review | I | C | C | A | R | R | C | C | | | C | |

---

## 7. RACI — Compliance Activities

| Activity | CEO | COO | CIO | CISO | IT Director | IST | CO | CMO | HR | Legal | DH |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Monitor regulatory requirements | | | | C | | | A/R | | C | C | |
| Maintain compliance matrix | | | | C | | R | A | | | C | |
| Conduct internal security audits | | | | A | C | R | C | | | | |
| Manage vendor BAAs | | | | C | | | A/R | | | C | |
| Respond to OCR investigations | C | | | C | C | C | R | | | A/R | |
| Submit annual HIPAA breach report | | | | C | | | A/R | | | C | |
| Conduct security awareness training | | | | A | | R | C | | R | | |
| Enforce data classification policy | | | | A | R | R | C | C | C | | C |
| Review and update all security policies | | | | A | C | R | C | | | C | |

---

## 8. RACI — Security Operations Activities

| Activity | CEO | COO | CIO | CISO | IT Director | IST | CO | CMO | HR | Legal | DH | All Staff |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Deploy and manage security tools | | | | A | R | R | | | | | | |
| Monitor security events and alerts | | | | A | C | R | | | | | | |
| Manage patch deployment | | | | C | A | R | | | | | | |
| Conduct vulnerability scanning | | | | A | C | R | | | | | | |
| Manage security awareness training program | | | | A | | R | C | | R | | | |
| Report security metrics to leadership | I | I | I | R | C | C | C | | | | | |
| Manage third-party security assessments | | | | A | C | R | C | | | C | | |
| Respond to security tool alerts | | | | C | C | A/R | | | | | | |
| Report suspected security incidents | | | | | | | | | | | | R |

---

## 9. RACI Summary — Key Governance Principles Applied

<!-- 
This section summarizes the key governance principles embedded in the RACI above.
These are the principles that make the RACI defensible
and that reflect real-world best practices.
Single accountability is the most important — if two people are both
Accountable for something, neither truly owns it.
The CISO owns information security — but the CEO owns organizational risk.
That distinction matters because the CISO cannot accept risks
that have organizational-level consequences on their own.
-->

| Principle | Application in TSHI RACI |
|---|---|
| Single Accountability | Each activity has exactly one Accountable party — prevents diffusion of responsibility |
| CISO as Security Owner | The CISO is Accountable for the majority of security program activities — consistent with HIPAA's designated security official requirement |
| CEO as Ultimate Authority | The CEO is Accountable for organization-wide risk acceptance and enterprise-level decisions |
| Clinical Leadership in Continuity | The CMO is Accountable for clinical downtime decisions — recognizing that patient care continuity is a clinical, not just technical, responsibility |
| Compliance Officer for Regulatory | The CO is Accountable for regulatory notifications and compliance reporting — ensuring legal obligations are not missed |
| All Staff for Reporting | Every workforce member is Responsible for reporting suspected security incidents — security is everyone's responsibility |

---

## 10. Related Documents

| Document | Path |
|---|---|
| Risk Assessment Policy | [../Docs/Risk_Assessment_Policy.md](../Docs/Risk_Assessment_Policy.md) |
| Incident Response Policy | [../Policies/Incident_Response_Policy.md](../Policies/Incident_Response_Policy.md) |
| Business Continuity Policy | [../Policies/Business_Continuity_Policy.md](../Policies/Business_Continuity_Policy.md) |
| Compliance Matrix | [../Matrices/Compliance_Matrix.md](../Matrices/Compliance_Matrix.md) |
| NIST Control Mapping | [Annex_B_NIST_Control_Mapping.md](Annex_B_NIST_Control_Mapping.md) |

---

*Document ID: TSHI-ANX-RACI-001 | Version: 1.0 | Classification: Internal Use Only | Case Study — Tri-State Health Initiative (TSHI)*
