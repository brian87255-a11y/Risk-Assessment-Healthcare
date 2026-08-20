# Organization Profile - Tri-State Health Initiative (TSHI)

*Document ID: TSHI-ORG-PROF-001 Version: 1.0 Classification: Internal Use Only Last Updated: August 2026* 

**Organization Order** 
--- 
| Field | Details | 
| :--- | :---: |
|Organization Name |Tri-State Health Initiative (TSHI) |
|Organization Type |Regional Nonprofit Healthcare Network |
|Headquarters |Newark, New Jersey |
|Operating region |New Jersey, New York, and Pennsylvania  |
|Founded |1988 |
|Annual Patient Volume |Approximately 85,000 patients  |
|Total Staff |Approximately 1,200 employees and contractors  |
|Facilities |1 main hospital campus, 3 outpatient clinics  |

**Mission & Vision** 
--- 

**Mission:** To deliver accessible, high-quality healthcare services to communities across the tri-state region, with a commitment to patient safety, clinical excellence, and the responsible stewards of patient information 

**Vision:** To be the most trusted regional healthcare network in the tri-state area, recognized for patient-centered care and innovative health services. 

**Facility Locations** 
--- 

| Facility | Location | Type | Staff | Patients Served Annually |
| :--- | :---: | :---: |:---: |---: |
| TSHI Main Hospital | Newark, NJ |Acute Care Hospital |~800 |~50,000 |
|TSHI North Clinic |Paterson, NJ |Outpatient Clinic |~120 |~12,000 |
|TSHI East Clinic |Jersey City, NJ |Outpatient Clinic |~130 |~13,000 |
|TSHI Metro Clinic |Bronx, NJ |Outpatient Clinic |~150 |~10,000 | 

**Organizational Structure** 
---

TSHI operates under a hierarchical governance structure with structure with executive leadership overseeing clinical, operational, and technology functions: 

```
Chief Executive Officer (CEO)
│
├── Chief Medical Officer (CMO)
│   └── Clinical Department Heads
│
├── Chief Operating Officer (COO)
│   └── Facility Managers (per location)
│
├── Chief Financial Officer (CFO)
│   └── Finance and Billing Department
│
└── Chief Information Officer (CIO)
    │
    ├── Chief Information Security Officer (CISO)
    │   └── Information Security Team
    │
    └── IT Director
        ├── Network and Infrastructure Team
        ├── Clinical Systems Team
        └── Help Desk and Support

```

**Key Business Processes** 
--- 

The following processes are considered critical to TSHI's mission and operations: 


| Business Process | Description | Impact if Disrupted |
| :--- | :---: | ---: |
|Patient care delivery |Clincical services provided across all four faculties |Direct risk to patient outcomes |
|Electronics Health Records (EHR) management |Access to and maintenance of patient medical records  |Inability to deliver safe, informed care  |
|Medical billing and claims processing  |Submission and tracking of insurance claims and patient billing  |Revenue disruption and financial instability |
|Pharmacy operations |Medication ordering, dispensing, and tracking |Risk of medication errors and patient harm |
|Patient scheduling and registration |Appointment booking and patient intake across all locations |Operational disruption and patient dissatisfaction |
|Laboratory and diagnostic systems |Processing and reporting of lab results and imaging |Delayed diagnostic and treatment decisions |
|Network and communications |Internal and external connectivity across all locations  |Disruption to all digital operations and communications  |

**Data Assets Overview** 
--- 

TSHI handles several categories of sensitive data that require protection: 

| Data Types | Description | Regulatory Classification |
| :--- | :---: | ---: |
|Electronic Protected Health Information (ePHI)|Patient diagnoses, treatment records, medications, lab results |HIPAA Protected |
|Personally Identifiable Information (PII) |Patient names, addresses, dates of birth, Social Security numbers |HIPAA/Privacy Act |
|Financial Data |Patient billing records, insurance information, payment data |PCI-DSS/HIPAA |
|Employee Records |HR data, payroll information, personnel files |Privacy Act |
|Operational Data |Network configurations, system logs, vendor contracts |Internal-Confidential | 

**Third-Party Relationships** 
---

TSHI maintains relationships with the following categories of third-party vendors and partners who have access to TSHI systems or data: 

| Vendor Category | Examples | Access to ePHI |HIPAA BAA Required |
| :--- | :---: | :---: |---: |
|EHR Software Provider |Electronic health records platform vendor |Yes |Yes |
|Cloud Services Provider |Infrastructure hosting and backup services |Yes |Yes |
|Medical Device Manufacturer |Imaging systems, patient monitoring equipment |Yes |Yes |
|IT Managed Services Provider |Help desk and infrastructure support |Yes |Yes |
|Insurance and Billing Clearinghouse |Claims processing and revenue cycle management |Yes |Yes |
|Cybersecurity Service Provider |Security monitoring and incident response |Yes |Yes |
|Facility Maintenance Vendors |HVAC, physical plant - no system access |No |No |

**Regulatory and Compliance Obligations** 
--- 
| Regulation | Applicability to TSHI |
| :--- | ---: |
|HIPAA Security Rule |Requires administrative, physical, and technical safeguard to protect ePHI |
|HIPAA Privacy Rule |Governs how patient health information may be used and disclosed |
|HITECH Act |Strengthens HIPAA enforcement; mandates breach notification to patients and HHS |
|New Jersey Identity Theft Prevention Act |Requires notification of NJ residents in the event of a data breach |
|PCI-DSS |Applies to TSHI's handling of patient payment card information |

**Current Security Posture** 
--- 

The following represents TSHI's security posture at the time of this assessment: 

| Area | Current State |
| :--- | ---: |
|Security Policies |Partially developed; some policies exist but are not consistently enforced |
|Access Controls |Active Directory in use; MFA not yet deployed for all staff |
|Patch Management |Inconsistent; some systems running outdated software versions|
|Security Awareness Training |Annual training provided but not role-specific |
|Incident Response |Basic incident response plan exists; not recently tested |
|Data Encryption |Encryption in place for data in transit; inconsistent for data at rest |
|Third-Party Risk Management |BAAs in place; vendor security assessments not consistently performed|
|Physical Security |Badge access at main hospital; less controlled at outpatient clinics |
|Network Segmentation |Limited segmentation; clinical and administrative networks partially separated |
|Security Monitoring |Basic logging in place; no dedicated SIEM deployed |

**Related Documents** 
--- 
| Document | Path |
| :--- | ---: |
|IT Environment |[IT Environment](IT_Environment.md) |
|Regulatory Framework |[Regulatory Framework](Regulatory_Framework.md) |
|Asset Inventory |[Asset Inventory](../Risk/Asset_Inventory.md) |
|Risk Assessment Policy |[Risk Assessment policy](../Docs/Risk_Assessment_Policy.md) |

*Document ID: TSHI-ORG-PROF-001 | Version: 1.0 | Classification: Internal Use Only | Case Study — Tri-State Health Initiative (TSHI)*

