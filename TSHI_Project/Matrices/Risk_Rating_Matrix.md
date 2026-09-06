<!-- 
WHAT IS THIS FILE?
This file documents the risk rating matrix — the tool used to combine
likelihood and impact ratings into an overall risk score for each risk entry.
Think of it as the formula sheet for the Risk Register.
Every risk rating in TSHI-RISK-001 through TSHI-RISK-013 was determined
using the matrix defined in this file.
In NIST SP 800-30 terms this covers step 2e of the conduct phase —
"Determine Risk" by combining likelihood and impact.
This file exists separately from the Likelihood_Impact_Matrix
because it serves a different purpose:
- Likelihood_Impact_Matrix.md defines HOW each dimension is scored
- Risk_Rating_Matrix.md defines HOW those scores are combined into a final rating
Together they form the complete scoring methodology for the assessment.
Having both documented separately makes the methodology transparent
and auditable — a regulator or auditor can follow the exact logic
from raw observation all the way to the final risk rating.
-->

# Risk Rating Matrix — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-MAT-RR-001
**Version:** 1.0
**Classification:** Internal Use Only
**Last Updated:** August 2026
**Owner:** Information Security Team

---

## 1. Purpose

<!-- 
The risk rating matrix is the core decision tool of the entire assessment.
It takes two inputs — likelihood and impact — and produces one output — risk rating.
The output determines how urgently a risk must be addressed
and at what organizational level it must be escalated.
A Critical risk goes to the CISO and possibly the Board.
A Low risk gets added to the backlog and addressed when resources allow.
Getting the matrix right matters because it directly drives
how TSHI spends its security budget and staff time.
-->

This document defines the risk rating matrix used to determine the overall risk level for each identified risk in the TSHI risk assessment. The matrix combines likelihood and impact ratings produced by the scoring methodology in `Matrices/Likelihood_Impact_Matrix.md` to generate a final risk rating for each entry in the Risk Register.

Risk ratings are used to:

- Prioritize remediation efforts based on severity
- Determine the appropriate level of organizational escalation
- Guide security investment and resource allocation decisions
- Communicate risk posture to executive leadership and the Board

---

## 2. Risk Rating Matrix

<!-- 
The 3x3 matrix is the standard NIST SP 800-30 qualitative risk matrix.
It maps every combination of likelihood and impact to a risk level.
The four possible risk levels are: Critical, High, Moderate, and Low.
Notice the asymmetry in the matrix — High likelihood + Low impact = Moderate,
but Low likelihood + High impact = also Moderate.
This reflects the reality that both dimensions matter equally —
a catastrophic but unlikely event is just as concerning as
a likely but minor event, and both require attention.
Only when both dimensions are Low does the risk drop to Low.
And only when at least one dimension is High does the risk reach High or Critical.
Critical requires both dimensions to be High.
-->

| | **High Impact** | **Moderate Impact** | **Low Impact** |
|---|---|---|---|
| **High Likelihood** | 🔴 Critical | 🟠 High | 🟡 Moderate |
| **Moderate Likelihood** | 🟠 High | 🟡 Moderate | 🟢 Low |
| **Low Likelihood** | 🟡 Moderate | 🟢 Low | 🟢 Low |

---

## 3. Risk Rating Definitions

<!-- 
Each rating level carries specific meaning in terms of:
1. The urgency of response required
2. Who in the organization must be notified and involved
3. The timeline for remediation
4. What happens if the risk is not addressed
These definitions ensure that everyone from the CISO to a department manager
understands what a rating means and what action is expected.
-->

### 🔴 Critical

<!-- 
Critical risks represent the most severe threats to TSHI.
They combine a high probability of occurrence with a high magnitude of harm.
In healthcare, Critical risks often involve both regulatory consequences
AND patient safety implications — which is why they require immediate executive attention.
In a real organization a new Critical risk discovery would trigger
an emergency briefing with the CISO within 24-48 hours.
-->

| Field | Definition |
|---|---|
| **Likelihood + Impact** | High Likelihood + High Impact |
| **Definition** | Immediate and severe threat to TSHI operations, patient safety, regulatory compliance, or organizational viability |
| **Response Requirement** | Immediate action required — remediation plan must be developed and initiated within 30 days |
| **Escalation** | CISO, CIO, COO, and executive leadership must be notified; Board reporting recommended |
| **Unaddressed Consequence** | High probability of catastrophic harm — patient safety risk, massive ePHI breach, regulatory investigation, potential organizational failure |
| **TSHI Risks at This Level** | TSHI-RISK-001, TSHI-RISK-002, TSHI-RISK-003 |

### 🟠 High

<!-- 
High risks are serious and require planned remediation with defined timelines.
They may not require emergency response but they must be formally owned
and tracked to closure. In a real organization High risks are reviewed
by the CISO monthly and status is reported to executive leadership quarterly.
A High risk that has no remediation plan or owner assigned
is effectively being treated as an accepted risk — and that acceptance
must be formally documented or it becomes a compliance issue.
-->

| Field | Definition |
|---|---|
| **Likelihood + Impact** | High Likelihood + Moderate Impact OR Moderate Likelihood + High Impact |
| **Definition** | Significant threat requiring planned remediation — poses material risk to operations, data, compliance, or finances |
| **Response Requirement** | Remediation plan required within 30 days; implementation within 90 days |
| **Escalation** | CISO must be notified; regular status reporting to CIO and senior leadership |
| **Unaddressed Consequence** | Significant harm probable — substantial data exposure, operational disruption, financial penalties, reputational damage |
| **TSHI Risks at This Level** | TSHI-RISK-004 through TSHI-RISK-010 |

### 🟡 Moderate

<!-- 
Moderate risks should be addressed through scheduled remediation
as part of TSHI's regular security program.
They do not require emergency escalation but they should not be ignored.
In a real organization Moderate risks are typically included in
the quarterly security roadmap and addressed within six months.
An accumulation of many Moderate risks is itself a risk —
multiple moderate weaknesses can combine to enable a more serious attack.
-->

| Field | Definition |
|---|---|
| **Likelihood + Impact** | High Likelihood + Low Impact OR Moderate Likelihood + Moderate Impact OR Low Likelihood + High Impact |
| **Definition** | Notable risk that warrants remediation through normal security program planning |
| **Response Requirement** | Remediation plan within 90 days; implementation within 6 months |
| **Escalation** | Information Security Team responsible; status reported to CISO in regular reporting cycle |
| **Unaddressed Consequence** | Moderate harm possible — limited data exposure, temporary disruption, manageable financial impact |
| **TSHI Risks at This Level** | TSHI-RISK-011, TSHI-RISK-012, TSHI-RISK-013 |

### 🟢 Low

<!-- 
Low risks are acknowledged but may be accepted or deferred
depending on available resources.
They still must be documented — ignoring them entirely is not acceptable.
In a real organization Low risks are reviewed annually
and assessed to determine whether they have changed in likelihood or impact.
A Low risk today can become a Moderate or High risk tomorrow
if the threat landscape changes or new vulnerabilities are discovered.
For TSHI no risks currently fall at the Low level —
which reflects the organization's immature security posture.
A more mature organization would have more Low risks
because strong controls reduce likelihood and impact across the board.
-->

| Field | Definition |
|---|---|
| **Likelihood + Impact** | Moderate Likelihood + Low Impact OR Low Likelihood + Moderate/Low Impact |
| **Definition** | Minor risk — limited probability and limited impact; may be accepted with documentation |
| **Response Requirement** | Addressed opportunistically or as part of annual security program review |
| **Escalation** | Information Security Team tracks; CISO informed during annual review |
| **Unaddressed Consequence** | Minor harm if exploited — quickly recoverable with minimal organizational impact |
| **TSHI Risks at This Level** | None identified in current assessment |

---

## 4. Risk Escalation and Ownership Framework

<!-- 
Knowing the risk rating is only half the battle.
Someone must OWN each risk — meaning they are accountable for ensuring
it is remediated or formally accepted within the required timeframe.
Without assigned ownership, risks sit in a register indefinitely
and never get addressed. Ownership is what turns a risk assessment
from a document into an action plan.
In a real organization risk ownership is negotiated between
the CISO and department heads — technical risks are owned by IT,
policy risks by compliance, physical risks by facilities management, and so on.
-->

| Risk Rating | Primary Owner | Escalation Path | Review Frequency |
|---|---|---|---|
| Critical | CISO | CEO and Board of Directors | Weekly until mitigated |
| High | CISO / IT Director | COO and CIO | Monthly |
| Moderate | Information Security Team | CISO | Quarterly |
| Low | Information Security Team | CISO | Annually |

---

## 5. Risk Acceptance Criteria

<!-- 
Not every risk can or should be mitigated immediately.
Resources are finite — money, staff, and time.
Risk acceptance is a legitimate and necessary part of risk management
but it must be formal and documented.
The key distinction is between INTENTIONAL risk acceptance
(we know about this risk, we have evaluated it, we have decided to accept it,
and a responsible person has signed off on that decision)
and UNINTENTIONAL risk ignorance
(we never looked at this, or we looked and forgot about it,
or we hoped it would go away).
Regulators and auditors can tell the difference.
HIPAA specifically requires that risk acceptance decisions be documented.
-->

Risks that cannot be immediately remediated may be formally accepted under the following conditions:

| Condition | Requirement |
|---|---|
| **Documentation** | Risk must be fully documented in the Risk Register including likelihood, impact, rating, and reason for acceptance |
| **Approval Authority** | Critical risks — CEO approval required; High risks — CISO approval required; Moderate and Low — IT Director approval sufficient |
| **Compensating Controls** | At minimum, compensating controls must be identified and implemented to reduce exposure during the acceptance period |
| **Review Period** | Accepted risks must be reviewed at the next assessment cycle — acceptance is never permanent |
| **Notification** | Acceptance of Critical or High risks must be communicated to the Board or relevant oversight body |

---

## 6. TSHI Risk Rating Summary

<!-- 
This summary table provides the complete picture of all 13 identified risks
ranked by rating. This is the table the CISO would present to the Board
to communicate the current state of TSHI's risk posture.
Notice that all risks are rated Moderate or above — there are no Low risks.
This reflects the significant security gaps documented in the IT Environment
and Vulnerability Identification files.
A mature organization with strong controls would have more Low risks
because controls reduce likelihood and impact across the board.
The absence of Low risks is itself a finding — it indicates
that TSHI's security program needs significant investment.
-->

| Rank | Risk ID | Risk Title | Likelihood | Impact | Rating |
|---|---|---|---|---|---|
| 1 | TSHI-RISK-001 | Ransomware via Phishing | High | High | 🔴 Critical |
| 2 | TSHI-RISK-002 | Unauthorized EHR Access via Credentials | High | High | 🔴 Critical |
| 3 | TSHI-RISK-003 | Medical Device Exploitation | Moderate* | High | 🔴 Critical* |
| 4 | TSHI-RISK-004 | Insider Theft of ePHI | Moderate | High | 🟠 High |
| 5 | TSHI-RISK-005 | Business Email Compromise | Moderate | High | 🟠 High |
| 6 | TSHI-RISK-006 | Privilege Escalation via Admin Accounts | Moderate | High | 🟠 High |
| 7 | TSHI-RISK-007 | Supply Chain Attack via Vendor | Moderate | High | 🟠 High |
| 8 | TSHI-RISK-008 | Unauthorized Physical Access at Clinics | Moderate | High | 🟠 High |
| 9 | TSHI-RISK-009 | Silent Data Exfiltration | Moderate | High | 🟠 High |
| 10 | TSHI-RISK-010 | Extended Downtime — No Secondary Site | Low | High | 🟠 High* |
| 11 | TSHI-RISK-011 | Cloud Misconfiguration | Moderate | Moderate | 🟡 Moderate |
| 12 | TSHI-RISK-012 | Accidental Data Deletion | Moderate | Moderate | 🟡 Moderate |
| 13 | TSHI-RISK-013 | Network Connectivity Loss at Clinics | Moderate | Moderate | 🟡 Moderate |

*Elevated above matrix formula output due to patient safety implications — professional judgment applied per NIST SP 800-30 guidance.

**Risk Distribution:**

| Rating | Count | Percentage |
|---|---|---|
| 🔴 Critical | 3 | 23% |
| 🟠 High | 7 | 54% |
| 🟡 Moderate | 3 | 23% |
| 🟢 Low | 0 | 0% |
| **Total** | **13** | **100%** |

---

## 7. Risk Treatment Priority Plan

<!-- 
This section translates risk ratings into an actionable timeline.
It answers the question every CISO gets from the CEO:
"OK we have all these risks — what do we fix first and when?"
The priority plan gives a structured answer based on risk rating.
Immediate actions address the most critical exposures first
regardless of cost — these are the things that if exploited tomorrow
would cause catastrophic harm.
Short-term actions address significant risks that need planned remediation.
Medium-term actions address important but less urgent improvements.
-->

### Immediate Priority — Within 30 Days

| Action | Addresses Risk(s) |
|---|---|
| Enforce MFA on Epic EHR for all users | TSHI-RISK-001, TSHI-RISK-002 |
| Enforce MFA on Microsoft 365 and all admin accounts | TSHI-RISK-002, TSHI-RISK-005, TSHI-RISK-006 |
| Implement medical device network segmentation (VLAN) | TSHI-RISK-003 |
| Enforce full disk encryption on all laptops and tablets | TSHI-RISK-008 |
| Conduct emergency backup restoration test | TSHI-RISK-001, TSHI-RISK-010 |
| Enforce MFA for all vendor remote access accounts | TSHI-RISK-007 |

### Short-Term Priority — Within 90 Days

| Action | Addresses Risk(s) |
|---|---|
| Deploy EDR solution across all endpoints | TSHI-RISK-001, TSHI-RISK-009 |
| Upgrade email security to advanced tier | TSHI-RISK-001, TSHI-RISK-005 |
| Deploy SIEM with User Behavior Analytics | TSHI-RISK-004, TSHI-RISK-009 |
| Conduct incident response tabletop exercise | TSHI-RISK-001, TSHI-RISK-010 |
| Implement formal access review process | TSHI-RISK-002, TSHI-RISK-004 |
| Upgrade clinic physical access to badge readers | TSHI-RISK-008 |
| Implement role-specific security awareness training | TSHI-RISK-001, TSHI-RISK-004, TSHI-RISK-005 |
| Implement Privileged Access Management solution | TSHI-RISK-006 |
| Establish vendor risk assessment program | TSHI-RISK-007 |
| Develop and distribute clinical downtime procedures | TSHI-RISK-010, TSHI-RISK-013 |
| Implement change management process | TSHI-RISK-011, TSHI-RISK-012 |
| Enable DNS filtering across all network segments | TSHI-RISK-001, TSHI-RISK-009 |

### Medium-Term Priority — Within 6 Months

| Action | Addresses Risk(s) |
|---|---|
| Evaluate and implement cloud DR or warm secondary site | TSHI-RISK-010 |
| Implement Data Loss Prevention (DLP) solution | TSHI-RISK-009 |
| Implement Cloud Security Posture Management (CSPM) | TSHI-RISK-011 |
| Implement Single Sign-On (SSO) | TSHI-RISK-002 |
| Deploy Network Access Control (NAC) for medical devices | TSHI-RISK-003 |
| Deploy visitor management system at all locations | TSHI-RISK-008 |

---

## 8. Related Documents

| Document | Path |
|---|---|
| Likelihood and Impact Matrix | [Likelihood_Impact_Matrix.md](Likelihood_Impact_Matrix.md) |
| Risk Register | [../Risk/Risk_Register.md](../Risk/Risk_Register.md) |
| Compliance Matrix | [Compliance_Matrix.md](Compliance_Matrix.md) |
| NIST Control Mapping | [../Annexes/Annex_B_NIST_Control_Mapping.md](../Annexes/Annex_B_NIST_Control_Mapping.md) |
| NIST 800-30 Methodology | [../Docs/NIST_800-30_Methodology.md](../Docs/NIST_800-30_Methodology.md) |

---

*Document ID: TSHI-MAT-RR-001 | Version: 1.0 | Classification: Internal Use Only | Case Study — Tri-State Health Initiative (TSHI)*
