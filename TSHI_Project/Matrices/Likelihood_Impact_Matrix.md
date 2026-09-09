<!-- 
This files explains the thought process behind on how each risk is scored, 
used to determine the likelihood and impact ratings for every listed risk in the Risk Register.
NIST SP 800-30 does not define an exact rating, qualitative or quantitive scale. 
In this study TSHI will use a three point qualitative scale those being High, Moderate, and Low. 
-->

# Likelihood and Impact Matrix — Tri-State Health Initiative (TSHI)

**Document ID: TSHI-MAT-LI-001
Version: 1.0
Classification: Internal Use Only
Last Updated: August 2026
Owner: Information Security Team**


**Purpose**
--- 

<!-- 
This document serves two purposes: 
- Explains the reasoning behind the specific impact and likelihood factors 
- Defines the scoring criteria so it can be reused and applied consistently  
-->

This document defines the likelihood and impact scoring criteria used in the TSHI risk assessment conducted under NIST SP 800-30 Rev. 1. It establishes a consistent, repeatable methodology for evaluating all identified risks and ensures that ratings are applied uniformly across the Risk Register.

---

## 2. Likelihood Assessment Criteria

<!-- 
Likelihood answers the question: How probable is it that this threat
will successfully exploit this vulnerability during the assessment period?
NIST SP 800-30 defines likelihood as a combination of two factors:
1. Threat source characteristics — motivation, capability, and intent
2. Vulnerability characteristics — how easy is the weakness to exploit?
A highly motivated attacker facing a very easy-to-exploit vulnerability
produces a High likelihood rating almost every time.
The assessment period for TSHI is one year — we are asking
"how likely is this to happen within the next 12 months?"
-->

Likelihood ratings reflect the probability that a specific threat source will successfully exploit a specific vulnerability within a one-year assessment period. Likelihood is determined by evaluating two factors:

- **Threat Source Characteristics** — the motivation, capability, and opportunity of the threat actor
- **Vulnerability Characteristics** — how accessible, exploitable, and well-known the weakness is

**Likelihood Rating Definitions**

| Likelihood Rating | Qualitative Definition | Probability Range | Assessment Criteria |
|---|---|---|---|
| High | The threat event is likely to occur within the assessment period | Greater than 70% probability | Threat source is highly motivated and capable; vulnerability is easily exploitable with no compensating controls; similar attacks have occurred at comparable organizations |
| Moderate | The threat event may occur within the assessment period | 30% – 70% probability | Threat source has capability but faces some barriers; vulnerability is exploitable but requires effort or opportunity; some compensating controls exist |
| Low | The threat event is unlikely to occur within the assessment period | Less than 30% probability | Threat source lacks motivation or capability; vulnerability is difficult to exploit; strong compensating controls significantly reduce exploitability |

**Threat Source Characteristic Ratings**

<!-- 
This tables breaks down how threat sources are evaluated
-->

| Threat Source Factor | High | Moderate | Low |
|---|---|---|---|
| **Motivation** | Strong, clear motivation — financial gain, espionage, revenge | Some motivation — opportunistic or ideological | Weak or unclear motivation — unlikely to specifically target TSHI |
| **Capability** | Sophisticated tooling, skilled actors, well-funded operations | Moderate technical skill, commodity tools available | Limited technical skill, no specialized tooling |
| **Opportunity** | Direct or easy access to target systems — internal access, exposed services | Some access pathways exist but require effort | Limited access pathways — strong perimeter controls present |
| **Historical Precedent** | This attack type is actively occurring against comparable organizations | This attack type has occurred in the sector but is not frequent | This attack type is rare or has not been observed in comparable environments |

**Vulnerability Characteristic Ratings**


| Vulnerability Factor | High Exploitability | Moderate Exploitability | Low Exploitability |
|---|---|---|---|
| **Accessibility** | Directly accessible — no authentication or minimal barrier to reach | Requires some access or privilege to reach | Requires significant access, privilege, or physical presence |
| **Exploitability** | Known exploit exists; exploit code publicly available; no technical skill required | Exploit exists but requires skill or specific conditions | No known exploit; exploitation requires advanced capability |
| **Compensating Controls** | No compensating controls present | Partial compensating controls — reduce but do not eliminate exploitability | Strong compensating controls significantly reduce exploitability |
| **Detection Probability** | Very unlikely to be detected — no monitoring or alerting in place | Possible to detect — some monitoring exists but not comprehensive | Likely to be detected — strong monitoring and alerting |

**Likelihood Determination Process**

<!-- 
This flowchart describes the decision process for assigning a likelihood rating.
If both evaluate as High, the likelihood is High.
If they are mixed, professional judgment is applied.
-->

The likelihood rating is determined by combining the threat source evaluation with the vulnerability exploitability evaluation:

```
Step 1: Evaluate threat source characteristics
        → Rate as High / Moderate / Low

Step 2: Evaluate vulnerability exploitability
        → Rate as High / Moderate / Low

Step 3: Combine ratings using the table below
        → Assign final likelihood rating

Step 4: Document rationale in the Risk Register
        → Record the specific factors that drove the rating
```

**Likelihood Combination Table:**

| Threat Source Rating | Vulnerability Exploitability | Final Likelihood Rating |
|---|---|---|
| High | High | High |
| High | Moderate | High |
| High | Low | Moderate |
| Moderate | High | High |
| Moderate | Moderate | Moderate |
| Moderate | Low | Low |
| Low | High | Moderate |
| Low | Moderate | Low |
| Low | Low | Low |

---

**Impact Assessment Criteria**

<!-- 
Impact for TSHI must be ovulated across these criteria 
1. Patient safety — could this harm patients directly?
2. Data confidentiality — how much ePHI is exposed?
3. Operational continuity — how long and how severely is care disrupted?
4. Financial — what are the regulatory penalties and recovery costs?
5. Reputational — how does this affect patient and community trust?
--->

Impact ratings reflect the magnitude of harm to TSHI's mission, operations, patients, and stakeholders if a threat event successfully occurs. Impact is evaluated across five dimensions:

**Impact Dimensions**

| Impact Dimension | Description | Why It Matters for TSHI |
|---|---|---|
| **Patient Safety** | Risk of direct harm to patient health outcomes | Clinical systems disruption can delay or prevent life-critical care |
| **Data Confidentiality** | Volume and sensitivity of data exposed | ePHI exposure triggers regulatory notification and patient harm |
| **Operational Continuity** | Duration and scope of operational disruption | EHR downtime affects care delivery across all four facilities |
| **Financial** | Regulatory penalties, recovery costs, revenue loss | HIPAA penalties up to $1.9M per category; ransomware recovery costs average millions |
| **Reputational** | Damage to patient trust and organizational standing | Patient trust is fundamental to healthcare — breaches cause lasting reputational harm |

**Impact Rating Definitions**

| Impact Rating | Qualitative Definition | Patient Safety | Data Exposure | Operational Impact | Financial Impact | Reputational Impact |
|---|---|---|---|---|---|---|
| **High** | Severe, potentially catastrophic harm across multiple dimensions | Direct risk to patient safety — care disruption, device malfunction, or delayed treatment | Large-scale ePHI exposure — thousands of patients affected; mandatory breach notification | Extended disruption — EHR unavailable for hours to days; multi-facility impact | Major penalties, recovery costs in millions; potential litigation | Severe and lasting — media coverage, regulatory investigation, loss of patient trust |
| **Moderate** | Significant harm in one or more dimensions; manageable with effort | Limited patient safety risk — disruption affects care quality but not safety directly | Limited ePHI exposure — hundreds of patients; notification likely required | Moderate disruption — systems unavailable for hours; one or two facilities affected | Significant costs — penalties possible; recovery measured in tens of thousands | Notable — local coverage; some patient concern but recoverable with transparent response |
| **Low** | Minor harm; quickly recoverable with minimal lasting effect | No direct patient safety risk | Minimal data exposure — few individuals; notification may not be required | Brief disruption — systems restored within hours; limited facilities affected | Minor costs — no significant penalties; recovery straightforward | Minimal — no public attention; internal matter |

**Impact Determination Process**

```
Step 1: Evaluate impact across all five dimensions
        → Note which dimensions are affected and to what degree

Step 2: Apply the impact rating that best reflects
        the combination of affected dimensions
        → A High rating in any single dimension may justify a High overall impact

Step 3: Consider existing response capabilities
        → Untested IR plan, unverified backups, and limited monitoring
          may elevate impact ratings for TSHI

Step 4: Document rationale in the Risk Register
        → Record which dimensions drove the impact rating
```

---

**Applied Likelihood and Impact Ratings — TSHI Risk Register**

<!--  
This tables explains why the given likelihood an rating assigned to that specific risk 
-->

| Risk ID | Risk Title | Likelihood | Likelihood Rationale | Impact | Impact Rationale |
|---|---|---|---|---|---|
| TSHI-RISK-001 | Ransomware via Phishing | High | Healthcare most targeted sector; no EDR, no MFA, basic email security only | High | EHR encryption disrupts patient care across 4 facilities; ePHI exposure; breach notification triggered |
| TSHI-RISK-002 | Unauthorized EHR Access | High | Credential theft highly prevalent; no MFA on EHR; no behavioral monitoring | High | Full ePHI access for 85,000 patients; mandatory breach notification; regulatory penalties |
| TSHI-RISK-003 | Medical Device Exploitation | Moderate | Known vulnerability class; exploitability elevated by lack of segmentation | High | ePHI exposure plus direct patient safety risk from device manipulation |
| TSHI-RISK-004 | Insider ePHI Theft | Moderate | 1,200 staff with EHR access; no behavioral monitoring; no formal access reviews | High | HIPAA breach notification; patient harm; criminal and civil liability for organization |
| TSHI-RISK-005 | Business Email Compromise | Moderate | Executives targeted; no MFA on M365; basic email security | High | Fraudulent financial transfers; potential six-figure financial loss |
| TSHI-RISK-006 | Privilege Escalation | Moderate | No PAM; admin accounts unmonitored; MFA only on VPN | High | Domain compromise gives attacker control of all TSHI systems including EHR and backups |
| TSHI-RISK-007 | Supply Chain Attack | Moderate | Multiple vendors with direct access; vendor security not consistently assessed | High | Full network access via trusted vendor channel; ePHI exposure; difficult to detect |
| TSHI-RISK-008 | Physical Access at Clinics | Moderate | Key locks at three clinics; no visitor management; no clean desk enforcement | High | Device theft with unencrypted ePHI; unauthorized EHR access via unattended workstation |
| TSHI-RISK-009 | Silent Data Exfiltration | Moderate | No SIEM, no EDR, no DLP — attacker can operate undetected | High | Large-scale ePHI exfiltration; breach not discovered until data surfaces externally |
| TSHI-RISK-010 | Extended Downtime — No DR Site | Low | Single data center; some redundancy exists at infrastructure level | High | Multi-facility EHR outage; patient safety risk; untested recovery procedures |
| TSHI-RISK-011 | Cloud Misconfiguration | Moderate | Cloud configurations not regularly audited; no CSPM tool | Moderate | Limited data exposure; prompt detection likely once discovered |
| TSHI-RISK-012 | Accidental Data Deletion | Moderate | No change management; backups untested; human error inherent | Moderate | Data loss recoverable from backup assuming backup integrity — currently unvalidated |
| TSHI-RISK-013 | Network Connectivity Loss | Moderate | MPLS circuits have VPN failover but failover not tested | Moderate | Single clinic isolated; paper downtime procedures exist but incomplete |

---

**Related Documents**

| Document | Path |
|---|---|
| Risk Register | [Risk Register](../Risk/Risk_Register.md) |
| Risk Rating Matrix | [Risk Rating Matrix](Risk_Rating_Matrix.md) |
| Threat Identification | [Threat Identification](../Risk/Threat_Identification.md) |
| Vulnerability Identification | [Vulnerability Identification](../Risk/Vulnerability_Identification.md) |
| NIST 800-30 Methodology | [NIST 800-30 Methodology](../Docs/NIST_800-30_Methodology.md) |

---

*Document ID: TSHI-MAT-LI-001 | Version: 1.0 | Classification: Internal Use Only | Case Study — Tri-State Health Initiative (TSHI)*
