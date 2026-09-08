<!-- 
WHAT IS THIS FILE?
This is TSHI's Business Continuity Policy — the formal document that governs
how TSHI maintains essential operations during a disruption
and recovers to full capability afterward.
Business continuity and disaster recovery are related but distinct concepts
that are commonly confused — even by experienced professionals.
Business Continuity (BC) = keeping the business running DURING a disruption
Disaster Recovery (DR) = restoring IT systems AFTER a disruption
Think of BC as what your staff does when systems go down
(activate paper-based downtime procedures, redirect patients, communicate with staff)
and DR as what IT does to bring the systems back up.
Both are needed. BC without DR means you can survive the event
but you cannot get back to normal. DR without BC means IT can restore
systems but nobody knows what to do in the meantime.
For a healthcare organization this is especially critical
because clinical operations cannot simply pause.
Patients still need care when the EHR is down.
Medications still need to be dispensed.
Lab results still need to be reported.
This policy is required under HIPAA Security Rule
45 CFR § 164.308(a)(7) — Contingency Plan.
-->

# Business Continuity Policy — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-POL-BC-001
**Version:** 1.0
**Classification:** Internal Use Only
**Effective Date:** August 2026
**Review Date:** August 2027
**Owner:** Chief Operating Officer (COO) / Chief Information Security Officer (CISO)
**Approved By:** Chief Executive Officer (CEO)

---

## 1. Purpose

<!-- 
The purpose of business continuity planning is to ensure
that TSHI can maintain patient care and essential operations
even when systems fail, disasters occur, or security incidents disrupt services.
The purpose is not just to protect IT — it is to protect patients.
A hospital that cannot access medication records during an EHR outage
risks patient harm through medication errors.
A clinic that cannot reach the central lab system
may delay critical diagnoses.
Business continuity planning exists because TSHI's mission —
delivering healthcare — cannot pause just because technology fails.
-->

This policy establishes TSHI's business continuity program, defining the requirements for maintaining essential clinical and operational functions during disruptive events and recovering to full operational capability as quickly as possible.

The policy is driven by two foundational principles:
- **Patient care must continue** — TSHI's primary obligation is to its patients; business continuity planning ensures clinical operations can be maintained even when technology systems are unavailable
- **Recovery must be planned** — the time to plan recovery is before a disruption occurs, not during one

This policy supports compliance with:
- HIPAA Security Rule — 45 CFR § 164.308(a)(7) — Contingency Plan
- NIST SP 800-34 Rev. 1 — Contingency Planning Guide for Federal Information Systems
- NIST Cybersecurity Framework 2.0 — Recover Function

---

## 2. Scope

This policy applies to all TSHI facilities, departments, systems, and personnel. It covers all categories of disruption including:

| Disruption Category | Examples |
|---|---|
| Cyber incidents | Ransomware, EHR system outage, network failure |
| Natural disasters | Hurricanes, flooding, severe storms, fire |
| Infrastructure failures | Power outage, HVAC failure, hardware failure |
| Public health emergencies | Pandemic, mass casualty event |
| Third-party failures | Cloud provider outage, vendor system failure, MPLS circuit failure |

---

## 3. Key Definitions and Metrics

<!-- 
These terms and metrics are essential vocabulary for business continuity
and disaster recovery. They appear constantly in certifications,
interviews, and real-world BC/DR conversations.
RTO — how long can we be down before it becomes unacceptable?
RPO — how much data can we afford to lose?
MTD — what is the absolute maximum we can be down before we fail as an organization?
MTBF — how often does a system fail on average?
MTTR — how long does it take to fix a failed system on average?
These five metrics together describe the resilience of an organization's systems.
In a risk assessment or BC planning conversation,
being able to define and apply all five shows a level of maturity
that most entry-level candidates do not have.
-->

| Term | Definition | TSHI Application |
|---|---|---|
| **RTO — Recovery Time Objective** | The maximum amount of time TSHI can tolerate a system or process being unavailable before the impact becomes unacceptable | Defined per system in Section 5 |
| **RPO — Recovery Point Objective** | The maximum amount of data loss TSHI can tolerate measured in time — how far back is the last acceptable restore point | Defined per system in Section 5 |
| **MTD — Maximum Tolerable Downtime** | The absolute maximum time a process can be offline before TSHI's mission is irreparably compromised | Clinical systems: 4 hours; Administrative systems: 24 hours |
| **MTBF — Mean Time Between Failures** | The average time a system operates between failures — used to predict failure frequency | Tracked by IT for critical infrastructure components |
| **MTTR — Mean Time to Repair** | The average time required to restore a failed system to operation — used to validate RTO targets | Tracked by IT for critical infrastructure components |

---

## 4. Business Impact Analysis Summary

<!-- 
The Business Impact Analysis (BIA) is the foundation of business continuity planning.
It identifies which business processes are critical,
what systems support them, and what the impact of losing those systems would be.
The BIA is what determines the RTO and RPO targets —
a process with a patient safety impact gets a shorter RTO
than a process that is inconvenient but not dangerous.
This section summarizes the BIA findings that were developed
during the Organization Profile and risk assessment phases.
A full BIA would be a separate detailed document in a real organization —
here we document the key findings that drive BC planning decisions.
-->

The BIA identified the following critical business processes and their recovery priority:

| Priority | Business Process | Supporting System(s) | Patient Safety Impact | RTO | RPO |
|---|---|---|---|---|---|
| 1 — Critical | Patient care delivery and clinical decision-making | Epic EHR, PACS, LIS | Direct — medication errors, delayed treatment | 4 hours | 1 hour |
| 2 — Critical | Pharmacy operations and medication dispensing | Pharmacy Management System, Epic EHR | Direct — medication dispensing errors | 4 hours | 1 hour |
| 3 — Critical | Patient monitoring and medical device operation | Medical Device Integration Engine, clinical network | Direct — monitoring failure, device errors | 2 hours | Real-time |
| 4 — High | Laboratory processing and results reporting | Laboratory Information System | Indirect — delayed diagnoses | 8 hours | 2 hours |
| 5 — High | Emergency department operations | Epic EHR, patient monitoring, communications | Direct — ED operations depend on rapid information access | 2 hours | 30 minutes |
| 6 — High | Network connectivity across facilities | MPLS circuits, VPN, core networking | Indirect — loss of access to centralized systems | 4 hours | N/A |
| 7 — Moderate | Patient scheduling and registration | Patient Scheduling System | Indirect — operational disruption, patient inconvenience | 24 hours | 4 hours |
| 8 — Moderate | Medical billing and claims processing | Billing and Revenue Cycle System | None direct | 48 hours | 24 hours |
| 9 — Moderate | Employee HR and payroll | HRIS | None direct | 72 hours | 24 hours |
| 10 — Low | General administrative email and collaboration | Microsoft 365 | None direct — phone backup available | 8 hours | 4 hours |

---

## 5. Recovery Objectives by System

<!-- 
This table translates the BIA findings into specific RTO and RPO targets
for each major system in TSHI's environment.
These targets drive the technical design of backup and recovery systems.
If the Epic EHR has an RTO of 4 hours, then the recovery infrastructure
must be capable of restoring it within 4 hours.
If it cannot, the RTO target is aspirational — not achievable —
and the organization needs to invest in better recovery capability.
The current gap at TSHI is that these targets have been set
but the underlying infrastructure to meet them (particularly a secondary DR site)
does not exist — meaning some RTO targets may not be achievable
under a major disaster scenario.
This is TSHI-RISK-010 in the Risk Register.
-->

| System | Classification | RTO Target | RPO Target | Current Recovery Capability | Gap |
|---|---|---|---|---|---|
| Epic EHR | Critical | 4 hours | 1 hour | Veeam backup — estimated 6-12 hour restore | ⚠️ RTO gap — exceeds target under major failure |
| PACS | Critical | 4 hours | 1 hour | Veeam backup — estimated 4-8 hour restore | ⚠️ RTO gap possible under major failure |
| Laboratory Information System | Critical | 8 hours | 2 hours | Veeam backup — estimated 4-6 hour restore | ✅ Likely achievable |
| Pharmacy Management System | Critical | 4 hours | 1 hour | Veeam backup — estimated 4-8 hour restore | ⚠️ RTO gap possible |
| Active Directory | Critical | 2 hours | 1 hour | Veeam backup — DC replication provides partial redundancy | ⚠️ RTO gap under site-wide failure |
| Microsoft 365 | High | 8 hours | 4 hours | Microsoft cloud resilience — generally high availability | ✅ Achievable — Microsoft SLA |
| Billing System | Moderate | 48 hours | 24 hours | Veeam backup — estimated 4-6 hour restore | ✅ Achievable |
| Patient Scheduling | Moderate | 24 hours | 4 hours | Cloud-hosted SaaS — provider DR applies | ✅ Achievable — provider SLA |
| AWS S3 Backup | High | N/A | N/A | AWS multi-region redundancy | ✅ Highly available |

---

## 6. Continuity Strategies

<!-- 
Continuity strategies are the specific plans TSHI activates
when a disruption occurs. There are two types:
1. Technology strategies — the IT actions to restore or maintain systems
2. Operational strategies — what staff actually DO when systems are unavailable
Both are required because technology restoration takes time,
and clinical operations must continue during that time.
The downtime procedures for clinical staff are arguably the most
important continuity strategy in a hospital setting —
they define exactly what happens at the bedside when the EHR goes down.
Without documented, trained, and practiced downtime procedures,
clinical staff improvise — which creates patient safety risk.
-->

### 6.1 Technology Continuity Strategies

| Strategy | Description | Applies To |
|---|---|---|
| **Data Backup and Restoration** | Veeam daily incremental and weekly full backups with offsite copy to AWS S3 — primary recovery strategy for most systems | All on-premise systems |
| **Cloud Failover** | Cloud-hosted systems (Microsoft 365, patient scheduling, HRIS) automatically failover to provider DR infrastructure | SaaS and cloud-hosted systems |
| **VPN Failover** | MPLS circuit outage automatically fails over to VPN over broadband for clinic connectivity | All clinic locations |
| **Active Directory Redundancy** | Multiple domain controllers provide partial redundancy for authentication services | Identity and access |
| **Manual Downtime Mode** | Epic EHR supports a downtime mode allowing limited read-only access to recently cached patient data during outages | Epic EHR |

### 6.2 Operational Continuity Strategies — Clinical Downtime Procedures

<!-- 
Clinical downtime procedures are what clinical staff do when the EHR goes down.
In a real hospital these are physical binders kept at every nursing station
that contain paper forms for medication administration records,
patient assessments, physician orders, and lab requisitions.
Staff are trained on these procedures annually
because if they have never practiced them,
they will not know what to do when the EHR goes down in the middle of the night.
The training gap at TSHI is that downtime procedures exist
but have not been fully documented, distributed, or practiced.
This is a finding that will be addressed through the remediation plan.
-->

When clinical systems are unavailable, TSHI clinical staff activate the following downtime procedures:

| Department | Downtime Procedure | Documentation Location |
|---|---|---|
| Nursing | Activate paper Medication Administration Records (MARs); use downtime patient wristbands; paper vital signs documentation | Downtime binders at each nursing station |
| Pharmacy | Activate paper prescription and dispensing logs; verify medication orders verbally with prescribing clinician | Pharmacy downtime procedure manual |
| Laboratory | Activate paper lab requisition forms; document results manually; fax critical results directly to clinical units | Lab downtime procedure binder |
| Radiology | Activate paper imaging request forms; document findings in written reports; verbal communication of critical findings | Radiology downtime procedure binder |
| Emergency Department | Activate paper triage and assessment forms; verbal physician orders with nursing documentation; paper trauma records | ED downtime procedure binder |
| Registration | Activate paper patient registration forms; assign temporary patient identifiers | Registration downtime forms |

**Downtime Communication Protocol:**

| Step | Action | Responsible Party |
|---|---|---|
| 1 | IT declares system downtime and notifies Clinical Lead | IT Director |
| 2 | Clinical Lead activates downtime procedures and notifies all department heads | Chief Medical Officer / Clinical Lead |
| 3 | Department heads distribute downtime binders and brief staff | Department Managers |
| 4 | IT provides regular status updates every 30 minutes during downtime | IT Director |
| 5 | IT notifies Clinical Lead when systems are restored and ready for reconciliation | IT Director |
| 6 | Clinical staff reconcile paper records into EHR upon system restoration | Clinical staff / Health Information Management |

---

## 7. Backup and Recovery Requirements

<!-- 
Backup requirements define exactly how data is backed up —
how often, what is included, where it is stored, and how it is tested.
The testing requirement is the most commonly neglected part.
Organizations assume their backups work until they try to restore
during a ransomware attack and discover the backups are corrupted,
incomplete, or incompatible with the current system version.
Discovering your backups do not work during a ransomware recovery
is one of the worst possible situations in healthcare IT.
Regular restoration testing eliminates this risk.
-->

| Requirement | Standard |
|---|---|
| Backup Frequency — Critical Systems | Daily incremental backup; weekly full backup |
| Backup Frequency — High Systems | Daily incremental backup; weekly full backup |
| Backup Frequency — Moderate and Low Systems | Weekly full backup |
| Offsite Backup | All backup data must have an offsite copy — TSHI uses AWS S3 for offsite replication |
| Backup Encryption | All backup data must be encrypted at rest — AES-256 minimum |
| Backup Retention | Critical data: 90 days online; 6 years archived per HIPAA; other data per retention schedule |
| Restoration Testing — Critical Systems | Full restoration test quarterly — documented with results |
| Restoration Testing — Other Systems | Full restoration test semi-annually — documented with results |
| Backup Monitoring | Backup jobs must be monitored daily — failed backups must be investigated and resolved within 24 hours |
| Immutable Backups | At least one backup copy must be stored in an immutable format that cannot be encrypted or deleted by ransomware |

---

## 8. BC Plan Testing Requirements

<!-- 
A BC plan that has never been tested is a theory, not a capability.
Testing reveals gaps between what the plan says will happen
and what actually happens when people try to follow it under pressure.
There are different types of tests with increasing levels of realism and disruption:
Tabletop — discussion based, no systems affected, lowest cost and disruption
Walkthrough — staff walk through procedures step by step without activating them
Simulation — partial activation of procedures in a controlled environment
Full test — complete activation including actual system failover
Healthcare organizations must balance testing thoroughness
against the risk of disrupting patient care during the test.
-->

| Test Type | Description | Frequency | Participants |
|---|---|---|---|
| Tabletop Exercise | Discussion-based scenario — no systems affected | Semi-annually | CISO, COO, IT Director, Clinical Lead, Department Managers |
| Backup Restoration Test | Restore specific critical data from backup to validate integrity and recoverability | Quarterly | IT Director, Clinical Systems Team |
| Downtime Procedure Drill | Clinical staff practice activating and using paper downtime procedures | Annually | Clinical staff across all facilities |
| Communication Tree Test | Verify all emergency contact information is current and reachable | Annually | HR, CISO, Department Heads |
| Full Continuity Exercise | Partial or full activation of BC procedures — may include actual system failover | Every two years | All CSIRT members and department heads |

**Test Documentation Requirements:**

| Requirement | Details |
|---|---|
| Test Plan | A written test plan must be developed before each exercise defining objectives, scope, participants, and success criteria |
| After-Action Report | A written after-action report must be produced within 14 days of each test documenting findings and improvement actions |
| Plan Updates | BC plan must be updated based on test findings within 60 days of each exercise |
| Retention | All test documentation must be retained for a minimum of six years |

---

## 9. Plan Maintenance

| Trigger | Required Action |
|---|---|
| Annual review | Full review and update of BC policy and plan — regardless of whether a disruption has occurred |
| After any actual disruption | Review and update based on lessons learned within 60 days |
| After any BC test | Update based on findings within 60 days |
| Significant organizational change | Review and update when new facilities, systems, or major organizational changes occur |
| Regulatory change | Review and update when applicable regulations change |

---

## 10. Related Documents

| Document | Path |
|---|---|
| Risk Assessment Policy | [../Docs/Risk_Assessment_Policy.md](../Docs/Risk_Assessment_Policy.md) |
| Incident Response Policy | [Incident_Response_Policy.md](Incident_Response_Policy.md) |
| Risk Register | [../Risk/Risk_Register.md](../Risk/Risk_Register.md) |
| Asset Inventory | [../Risk/Asset_Inventory.md](../Risk/Asset_Inventory.md) |
| Compliance Matrix | [../Matrices/Compliance_Matrix.md](../Matrices/Compliance_Matrix.md) |

---

*Document ID: TSHI-POL-BC-001 | Version: 1.0 | Classification: Internal Use Only | Effective: August 2026 | Case Study — Tri-State Health Initiative (TSHI)*
