<!-- 
This is TSHI's Incident Response Policy its a document that governs
the method in which TSHI prepares for, detects, responds to, and recovers from security incidents.

An incident response policy is required under HIPAA Security Rule
45 CFR § 164.308(a)(6) Security Incident Procedures.

HIPAA requires covered entities to implement policies and procedures
to address security incidents — including how to identify, respond to,
and document incidents involving ePHI.

The gap identified in the risk assessment was that TSHI has a basic IR plan
but it has never been tested — meaning staff do not know their roles
and the plan may not work in a real incident.

This policy formalizes the program that the plan operates under.
Think of the difference this way:
The POLICY defines the rules, roles, and requirements — it is permanent.
The PLAN (procedures) defines the step-by-step actions — it is operational.
Both are needed. One without the other leaves gaps.
-->

# Incident Response Policy — Tri-State Health Initiative

**Document ID: TSHI-POL-IR-001
Version: 1.0
Classification: Internal Use Only
Effective Date: August 2026
Review Date: August 2027
Owner: Chief Information Security Officer (CISO)
Approved By: Chief Executive Officer (CEO)**


**Purpose**
---

<!-- 
A security incident is any event that threatens the confidentiality,
integrity, or availability of TSHI's information systems or data.
In healthcare this has a direct patient safety dimension
a ransomware attack that takes down the EHR is not just an IT problem,
it is a clinical emergency.
Having a defined, practiced, and documented incident response capability
is what separates organizations that recover quickly from those
that spend weeks rebuilding while patients are at risk.
-->

This policy establishes the requirements, roles, and responsibilities for Tri-State Health Initiative's (TSHI) information security incident response program. It ensures that security incidents are detected, reported, contained, investigated, and resolved in a structured, timely, and legally compliant manner.

This policy supports compliance with:
- HIPAA Security Rule — 45 CFR § 164.308(a)(6) — Security Incident Procedures
- HITECH Act — Breach Notification Requirements (45 CFR Part 164, Subpart D)
- NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide
- NIST Cybersecurity Framework 2.0 — Respond and Recover Functions

**Scope**

This policy applies to all security incidents affecting TSHI information systems, data, and operations regardless of cause, location, or the party responsible for detection.

| In Scope | Examples |
|---|---|
| Cyber incidents | Ransomware, phishing, unauthorized access, data exfiltration, malware |
| Physical incidents | Unauthorized facility access, device theft, physical tampering with systems |
| Insider incidents | Intentional or accidental data exposure by workforce members |
| Third-party incidents | Vendor breaches affecting TSHI data or systems |
| Non-adversarial incidents | Accidental data deletion, system misconfigurations causing data exposure |


**Incident Definition and Classification**

<!-- 
Not every security event is an incident.
An EVENT is any observable occurrence in a system or network.
An INCIDENT is an event that actually or potentially jeopardizes
the confidentiality, integrity, or availability of information.
Distinguishing between events and incidents prevents
the security team from drowning in noise — millions of events
occur daily on a network. The team needs to focus on the ones that matter.
The severity classification system below tells the team
how urgently to respond and who needs to be notified.
A P1 ransomware attack on the EHR requires an all-hands immediate response.
A P4 low-risk email phishing attempt that was caught by the filter
can be logged and reviewed during normal business hours.
-->

**Security Event vs Security Incident**
---

| Term | Definition |
|---|---|
| **Security Event** | Any observable occurrence in a system or network — not all events are incidents |
| **Security Incident** | An event that actually or potentially jeopardizes the confidentiality, integrity, or availability of TSHI information systems or data |
| **Privacy Breach** | A specific type of incident involving actual or suspected unauthorized access, use, or disclosure of ePHI |

**Incident Severity Classification**
---

| Severity | Classification | Definition | Response Time | Notification Required |
|---|---|---|---|---|
| **P1 — Critical** | Enterprise-wide impact | Ransomware, EHR system down, active breach of ePHI affecting large numbers of patients, patient safety at risk | Immediate — within 1 hour | CISO, CEO, COO, CIO, Legal, Clinical Leadership |
| **P2 — High** | Significant impact | Confirmed unauthorized access to ePHI, business email compromise, significant system outage affecting multiple departments | Within 4 hours | CISO, CIO, IT Director, Compliance Officer |
| **P3 — Moderate** | Limited impact | Malware detected and contained, suspected phishing attempt, single system outage, limited data exposure | Within 24 hours | CISO, IT Director |
| **P4 — Low** | Minimal impact | Blocked phishing email, failed login attempts, minor policy violation, security event requiring investigation | Within 72 hours | IT Security Team |



**Incident Response Team**
---

<!-- 
The Computer Security Incident Response Team (CSIRT) is the group
of people responsible for managing security incidents at TSHI.
In a real organization this would be a formally designated team
with defined roles, contact information, and 24/7 availability.
TSHI currently does not have a formally designated CSIRT —
this policy creates one.
The CISO is the Incident Commander — they make final decisions
during a response. This is important because incidents move fast
and having clear authority prevents confusion and delays.
Think of it like a fire department — the fire chief has command authority
at the scene even if the building owner is present.
-->

**CSIRT Roles and Responsibilities**
---

| Role | Title | Responsibilities |
|---|---|---|
| **Incident Commander** | CISO | Overall authority during incident response — makes final decisions on containment, communication, and escalation |
| **Technical Lead** | IT Director | Directs technical investigation and containment activities — coordinates IT staff |
| **Communications Lead** | Chief Communications Officer / CEO | Manages all external communications including patient notification, media, and regulatory bodies |
| **Legal Counsel** | General Counsel / External Legal | Advises on legal obligations, regulatory notification requirements, and law enforcement engagement |
| **Compliance Officer** | Compliance Officer | Ensures regulatory requirements are met including HIPAA breach notification timelines |
| **Clinical Lead** | Chief Medical Officer | Represents clinical operations — activates downtime procedures when clinical systems are affected |
| **IT Security Analyst** | Information Security Team | Performs technical forensic analysis, log review, and evidence collection |
| **HR Representative** | HR Director | Involved in incidents with insider threat dimensions — manages workforce implications |

### 4.2 External Resources

| Resource | Purpose | When Engaged |
|---|---|---|
| Cyber Insurance Provider | Incident response support, legal defense, breach notification services | P1 and P2 incidents |
| External Forensics Firm | Independent forensic investigation and evidence preservation | P1 incidents; when internal capability is insufficient |
| FBI / CISA | Law enforcement and federal agency support | Significant ransomware or nation-state incidents |
| HHS Office for Civil Rights | Regulatory notification and investigation | All confirmed ePHI breaches meeting HIPAA notification thresholds |
| State Attorney General (NJ / NY) | State breach notification | Breaches affecting NJ or NY residents |


**Incident Response Phases**
---

<!-- 
NIST SP 800-61 defines the incident response lifecycle in four phases.
Understanding these phases is critical for anyone in cybersecurity.
They are: Preparation, Detection and Analysis, Containment/Eradication/Recovery,
and Post-Incident Activity.
Note that Preparation is the first phase — most of the work in an IR program
happens BEFORE an incident occurs. Training, tools, procedures, contacts —
all of this must be in place before you need it.
When an incident is happening is the worst time to figure out your response.
-->

### Phase 1 — Preparation

<!-- 
Preparation is the most important phase because it determines
how effectively you can respond when an incident actually occurs.
A well-prepared organization contains incidents faster,
recovers more completely, and spends less money doing it.
The gap in TSHI's current state is that preparation has been minimal —
the IR plan exists but has never been tested,
staff have not been trained on their roles,
and the tools needed for effective response are not in place.
-->

**Objective:** Establish the capabilities, tools, and processes needed to respond effectively before an incident occurs.

| Activity | Description | Frequency |
|---|---|---|
| CSIRT Maintenance | Maintain current contact information and on-call schedules for all CSIRT members | Quarterly |
| IR Plan Review | Review and update the incident response procedures document | Annually or after each significant incident |
| Tabletop Exercises | Conduct discussion-based scenario exercises with CSIRT and key stakeholders | Semi-annually |
| Technical Exercises | Conduct technical simulations including ransomware and breach scenarios | Annually |
| Tool Readiness | Verify that forensic tools, communication channels, and backup systems are operational | Quarterly |
| Staff Training | Train all workforce members on how to recognize and report security incidents | Annually — role-specific |
| Legal Preparedness | Maintain current contact information for legal counsel and cyber insurance provider | Annually |

### Phase 2 — Detection and Analysis

<!-- 
Detection is where most organizations struggle.
An attack that goes undetected for 200 days — the industry average dwell time —
means an attacker has had over six months to move through your network,
steal data, and establish persistence before you even know they are there.
TSHI's lack of a SIEM means detection is largely reactive —
someone has to notice something is wrong before the investigation starts.
Deploying a SIEM is the highest-priority technical recommendation
because it transforms detection from reactive to proactive.
The average dwell time (time between initial compromise and detection)
for healthcare breaches has historically been measured in months.
-->

**Objective:** Identify potential security incidents and determine their scope and severity.

| Activity | Description |
|---|---|
| Incident Identification | Security events are identified through system alerts, user reports, vendor notifications, or third-party intelligence |
| Initial Triage | IT Security Analyst performs initial analysis to determine if the event constitutes an incident |
| Severity Classification | Incident Commander assigns severity level (P1-P4) based on classification criteria in Section 3.2 |
| Scope Determination | Technical team determines which systems, data, and users are affected |
| Evidence Preservation | All relevant logs, system states, and artifacts are preserved immediately upon incident confirmation — evidence must not be altered or destroyed |
| Notification | CSIRT members are notified according to severity level requirements in Section 3.2 |

**Indicators of Compromise to Monitor:**

| Indicator Category | Examples |
|---|---|
| Network Anomalies | Unusual outbound traffic volumes, connections to unknown external IPs, DNS queries to suspicious domains |
| Authentication Anomalies | Multiple failed logins, logins at unusual hours, logins from unexpected geographic locations, impossible travel |
| Endpoint Anomalies | Unusual process execution, unexpected software installation, abnormal file system activity, disabled security tools |
| Application Anomalies | Bulk EHR record downloads, unusual query patterns in clinical systems, unauthorized configuration changes |
| User Behavior Anomalies | Access to systems outside normal job function, large data transfers, access to terminated employee accounts |

### Phase 3 — Containment, Eradication, and Recovery

<!-- 
These three activities are often discussed together but they are distinct steps
that must happen in order.
CONTAINMENT first — stop the bleeding. Prevent the incident from spreading.
This might mean isolating an infected system from the network.
You do not want to recover systems before you have contained the threat —
otherwise you might restore a system that immediately gets reinfected.
ERADICATION second — remove the cause. Delete malware, patch vulnerabilities,
reset compromised credentials. Make sure the threat is completely gone.
RECOVERY last — restore systems to normal operation and verify they are clean.
In a healthcare environment this order is especially critical —
restoring clinical systems before eradication is complete
could put patient data at risk again immediately.
-->

#### 3a — Containment

**Objective:** Limit the scope and spread of the incident to prevent additional damage.

| Containment Action | Description | When Applied |
|---|---|---|
| Network Isolation | Disconnect affected systems from the network to prevent lateral movement | Immediately upon confirmation of active malware or breach |
| Account Suspension | Suspend compromised or suspected compromised user accounts | When credential compromise is confirmed or suspected |
| Vendor Access Revocation | Immediately revoke access for any vendor account involved in the incident | When vendor compromise is suspected |
| Traffic Blocking | Implement firewall rules to block malicious IP addresses or domains identified during analysis | As indicators of compromise are identified |
| Clinical Downtime Activation | Activate paper-based clinical downtime procedures if EHR or clinical systems are affected | When clinical systems cannot be safely maintained online |

#### 3b — Eradication

**Objective:** Remove the root cause of the incident from the environment.

| Eradication Action | Description |
|---|---|
| Malware Removal | Remove all identified malware using approved tools — do not trust automated removal alone for significant infections |
| Credential Reset | Reset all compromised or potentially compromised credentials — prioritize privileged accounts |
| Vulnerability Remediation | Patch or mitigate the vulnerability that enabled the initial compromise |
| System Rebuild | Systems confirmed to be compromised must be rebuilt from known-good images rather than cleaned in place |
| Backdoor Identification | Scan for and remove any persistence mechanisms or backdoors installed by the attacker |

#### 3c — Recovery

**Objective:** Restore systems to normal operation and verify they are secure.

| Recovery Activity | Description |
|---|---|
| Restore from Backup | Restore affected systems from verified clean backups — confirm backup integrity before restoration |
| System Validation | Verify restored systems are clean and functioning correctly before returning to production |
| Enhanced Monitoring | Implement increased monitoring on recovered systems for a minimum of 30 days post-incident |
| Phased Return | Return systems to production in phases — clinical systems last, after thorough validation |
| User Notification | Notify affected users of system restoration and any credential changes required |

### Phase 4 — Post-Incident Activity

<!-- 
The lessons learned review is one of the most valuable activities
in the entire IR process — and the one most commonly skipped.
Organizations that skip it make the same mistakes in the next incident.
Organizations that do it well continuously improve their security posture.
The review should be conducted within two weeks of incident closure
while details are still fresh. It should be blame-free —
the goal is to understand what happened and improve, not punish people.
The questions it answers: What happened? How did we find out?
How did we respond? What worked? What did not? What do we change?
-->

**Objective:** Learn from the incident to improve future response capability.

| Activity | Description | Timeline |
|---|---|---|
| Lessons Learned Review | Conduct a formal review with CSIRT and relevant stakeholders — document what happened, what worked, what failed, and what needs to change | Within 14 days of incident closure |
| Incident Report | Produce a formal written incident report documenting timeline, impact, response actions, and recommendations | Within 30 days of incident closure |
| Policy and Plan Updates | Update IR policy, procedures, and relevant security policies based on lessons learned | Within 60 days of incident closure |
| Control Implementation | Implement any new controls or remediation actions identified during the review | Per remediation timeline |
| Documentation Retention | Retain all incident documentation for a minimum of six years per HIPAA requirements | Ongoing |



**HIPAA Breach Notification Requirements**
---

<!-- 
When a security incident involves unauthorized access to unsecured ePHI,
it may constitute a HIPAA breach requiring mandatory notification.
The key distinction is between a security incident and a breach.
Not every security incident is a breach.
A breach is specifically an impermissible use or disclosure of ePHI
that compromises the security or privacy of the information.
HIPAA provides a risk assessment framework to determine if an incident
is a notifiable breach — looking at the nature of the ePHI,
who accessed it, whether it was actually acquired or viewed,
and the extent to which the risk has been mitigated.
If encryption was in place and the key was not compromised —
the safe harbor provision may apply and notification may not be required.
This is why encrypting ePHI is so strategically important.
-->

**6.1 Breach Determination**
---

Upon discovery of a potential ePHI breach, TSHI must conduct a four-factor risk assessment to determine if notification is required:

| Factor | Assessment Question |
|---|---|
| Nature and extent of ePHI involved | What types of ePHI were involved and how sensitive is it? |
| Who accessed or could have accessed the ePHI | Was the access by an unauthorized person who would have no obligation to protect the data? |
| Whether ePHI was actually acquired or viewed | Is there evidence the information was actually seen or taken? |
| Extent to which risk has been mitigated | Has the risk been fully mitigated — e.g., through confirmed destruction of data? |

If the risk assessment cannot demonstrate a low probability that ePHI was compromised, the incident is presumed to be a breach and notification is required.

**Breach Notification Timeline**

| Notification Target | Timeline | Responsible Party |
|---|---|---|
| Affected Individuals | Within 60 days of breach discovery | Compliance Officer / Communications Lead |
| HHS Office for Civil Rights | Within 60 days for breaches affecting 500+ individuals; annually for breaches under 500 | Compliance Officer / Legal |
| Media (State where breach occurred) | Within 60 days for breaches affecting 500+ residents of a state | Communications Lead / Legal |
| NJ Division of Consumer Affairs | Most expedient time possible — NJ Identity Theft Prevention Act | Compliance Officer / Legal |
| NY Attorney General | Most expedient time possible — NY SHIELD Act | Compliance Officer / Legal |



**Evidence Handling and Chain of Custody**
---

<!-- 
Evidence handling is critical for two reasons:
1. If TSHI pursues legal action against an attacker or insider,
   evidence must be collected and preserved in a legally admissible manner.
   Improperly handled evidence can be thrown out in court.
2. The forensic investigation depends on the integrity of the evidence.
   If logs are deleted or systems are modified before they can be imaged,
   the investigation may be unable to determine what happened.
Chain of custody documentation tracks who collected evidence,
when, how it was stored, and who had access to it.
This is a standard requirement in any legal or regulatory proceeding.
-->

| Requirement | Description |
|---|---|
| Evidence Preservation | Do not power off, reformat, or modify affected systems before forensic imaging — unless necessary to prevent ongoing harm |
| Chain of Custody | Document who collected each piece of evidence, when, how it was stored, and who had access |
| Log Retention | Preserve all relevant system logs, network captures, and audit trails immediately upon incident confirmation |
| Legal Hold | Place a legal hold on all documentation related to the incident — suspend normal data destruction schedules |
| Forensic Imaging | Create forensic images of affected systems using approved tools before any remediation is performed |



**Related Documents**
---

| Document | Path |
|---|---|
| Risk Assessment Policy | [Risk Assessment Policy](../Docs/Risk_Assessment_Policy.md) |
| Access Control Policy | [Access Control Policy](Access_Control_Policy.md) |
| Business Continuity Policy | [Business Continuity Policy](Business_Continuity_Policy.md) |
| Risk Register | [Risk Register](../Risk/Risk_Register.md) |
| Compliance Matrix | [Compliance Matrix](../Matrices/Compliance_Matrix.md) |

---

*Document ID: TSHI-POL-IR-001 | Version: 1.0 | Classification: Internal Use Only | Effective: August 2026 | Case Study — Tri-State Health Initiative (TSHI)*
