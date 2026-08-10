# Tri-State Health Initiative (TSHI) - RISK ASSESSMENT 
-- This is a case study created for educational and portfolio purposes --



# Overview 

This repository contains a comprehensive risk assessment conducted for Tri-State Health Initiative (TSHI), a fictional regional healthcare network operating a main hospital and three other clinics across across New Jersey and neighboring areas, serving approximately 85,000 patients annually. 

The assessment is created to identity, analyze, and prioritize information security risks to TSHI's systems, data, and operations and to recommend controls to mitigate risks with regulatory requirements in mind.


# Framework 

This risk assessment follows the NIST SP 800-30 Rev.1 - Guide for Conducting Risk Assessment, published by the National Institute of Standards of Technology (NIST). NIST SP 800-30 provides a structured process for conducting risk assessments across all tiers of an organization and is widely adopted in both government and healthcare environments. 

# Regulatory Context 

As a healthcare organization, TSHI is subject to the following frameworks addressed in this assessment: 


| Regulation | Full Name | Relevance |
| ---------------- | ---------------- | ---------------- |
| HIPAA | Health Insurance Portability and Accountability Act | Protection of patient health information|
| HITECH | Health Information Technology for Economic and Clinical Health Act | Strengthen HIPAA enforcement and breach notification |
| NIST CSF | NIST Cybersecurity Framework | Framework guiding cybersecurity risk management  |

# Repository Structure 

```
healthcare-risk-assessment/
│
├── README.md                          
│
├── Docs/
│   ├── NIST_800-30_Methodology.md      ← Framework explanation and process steps
│   └── Risk_Assessment_Policy.md       ← Internal policy governing this assessment
│
├── Organization/
│   ├── Organization_Profile.md         ← Who TSHI is, mission, and structure
│   ├── IT_Environment.md               ← Systems, infrastructure, and technology
│   └── Regulatory_Framework.md         ← Applicable laws and compliance obligations
│
├── Risk/
│   ├── Asset_Inventory.md              ← Identified assets and their classifications
│   ├── Threat_Identification.md        ← Threat sources and threat events
│   ├── Vulnerability_Identification.md ← Known weaknesses in systems and processes
│   └── Risk_Register.md                ← Consolidated risk register with ratings
│
├── Matrices/
│   ├── Likelihood_Impact_Matrix.md     ← Scoring methodology for likelihood and impact
│   ├── Risk_Rating_Matrix.md           ← Overall risk ratings per identified risk
│   └── Compliance_Matrix.md            ← Regulatory requirements mapped to controls
│
├── Policies/
│   ├── Access_Control_Policy.md        ← Rules governing access to TSHI systems
│   ├── Incident_Response_Policy.md     ← Procedures for responding to security incidents
│   ├── Data_Classification_Policy.md   ← How TSHI classifies and handles data
│   └── Business_Continuity_Policy.md   ← Maintaining operations during disruptions
│
├── Annexes/
│   ├── Annex_A_RACI_Matrix.md          ← Roles and responsibilities across the assessment
│   └── Annex_B_NIST_Control_Mapping.md ← NIST 800-53 controls mapped to identified risks
│
└── Diagrams/
    └── Network_Topology.md             ← High-level network diagram of TSHI environment 
```
# Author 

Brian Rivera
ISC2 Certified in Cybersecurity (CC)
Information Technology Student — NJIT Honors College
Aspiring Cybersecurity Analyst | Federal Sector Focus 

Assessment Date: August 10 2026 | Framework: NIST SP 800-30 Rev. 1 | Status: Case Study
