# Regulatory Framework - Try State Health Initiative


*Document ID: TSHI-ORG-REG-001 Version: 1.0 Classification: Internal Use Only Last Updated: August 2026
Owner: Compliance Officer*

**Purpose** 
--- 

This document identifies and describes the regulatory, legal, and industry framework obligations applicable to Tri-State Health Initiative (TSHI). Compliance with these frameworks directly shapes TSHI's information security program and informs the risk assessment conducted under NIST SP 800-30. 

Understanding the regulatory environment is essential because: 
- It defines the minimum security requirements TSHI must meet
- It determines what data must be protected and how
- It establishes the consequences of non-compliance including financial penalties and criminal liability
- It informs which risks are of highest priority when resources for remediation are limited


**Primary Regulatory Frameworks** 
--- 

*Health Insurance Portability and Accountability Act of 1996
Enforced By: U.S. Department of Health and Human Services (HHS), Office for Civil Rights (OCR)
Applicability to TSHI: TSHI is a covered entity under HIPAA as a healthcare provider that transmits health information electronically.* 

**HIPAA Privacy Rule (45 CFR Part 164, Subpart E)** 

The Privacy Rule establishes national standards for the protection of individually identifiable health information, known as Protected Health Information (PHI).

|Key Requirement|Description|
|:---|---:|
|Minimum necessary standard|Only the minimum amount of PHI necessary to accomplish a task should be used or disclosed|
|Patient rights|Patients have the right to access, amend, and receive an accounting of disclosures of their PHI|
|Permitted uses and disclosures|PHI may only be used or disclosed for treatment, payment, healthcare operations, or with patient authorization|
|Notice of Privacy Practices|TSHI must provide patients with a written notice of how their PHI is used and protected|

**HIPAA Security Rule (45 CFR Part 164, Subpart C)** 

The Security Rule requires TSHI to implement administrative, physical, and technical safeguards to protect electronic Protected Health Information. 

Administrative Safeguards: 

|Standard|Requirement|TSHI Status|
|:---|:---:|---:|
|Security Management Process|Conduct risk analysis and implement risk management program|In progress|
|Assigned Security Responsibility|Designate a security official responsible for security policies|Compliant|
|Workforce Security|Implement procedures for authorization and supervision of workforce access to ePHI|Partially Compliant|
|Information Access Management|Implement policies for granting access to ePHI|Partially Complaint|
|Security Awareness Training|Train all workforce members on security policies and procedures|Partially Complaint through annual training only|
|Security Incident Procedures|Implement policies to address security incidents|Partially Compliant; plans exist but are untested|
|Contingency Plan|Establish policies for responding to emergencies affecting ePHI systems|Partially Complaint|
|Evaluation|Perform periodic technical and non-technical evaluation|In progress|
|Business Associate Contracts|Obtain satisfactory assurances from business associates|Complaint| 

**Physical Safeguards** 

|Standard|Requirement|TSHI Status|
|:---|:---:|---:|
|Facility Access Control|Limit physical access to systems containing ePHI|Partially Complaint found gaps at outpatient clinics|
|Workstation Use|Implement policies for proper workstation use|Partially Compliant|
|Workstation Security|Implement physical safeguards for workstations|Partially Compliant|
|Device and Media Controls|Implement policies for hardware and electronic media containing ePHI|Partially Compliant| 

**Technical Safeguards** 

|Standard|Requirement|TSHI Status|
|:---|:---:|---:|
|Access Controls|Implement technical policies to allow only authorized access to ePHI|Partially Compliant there is no MFA on EHR|
|Audit Controls|Implement hardware and software to record and examine activity on systems containing ePHI|Partially Compliant|
|Integrity Controls|Implement policies to protect ePHI from improper alteration or destruction|Partially Complaint|
|Transmission Security|Implement security measures to guard against unauthorized access to ePHI transmitted over networks|Compliant through the use of TLS encryption|

**HIPAA Penalty Structure** 

|Violation Category|Description|Penalty Per Violation|Annual Maximum|
|:---|:---:|:---:|---:|
|Tier 1 Unknowing||$100-$50,000|$25,000|
|Tier 2 Reasonable||$1,000-$50,000|$100,000|
|Tier 3 Willful Neglect(Corrected)|Violation due to willful neglect but corrected within 30 days|$10,000-$50,000|$250,000|
|Tier 4 Willful Neglect(Not Corrected)|Violation due to willful neglect and not corrected|$50,000|$1,900,000|

**HITECH Act**

*Health Information Technology for Economic and Clinical Health Act of 2009
Enforced By: HHS Office for Civil Rights (OCR)
Applicability to TSHI: As a HIPAA covered entity, TSHI is directly subject to HITECH requirements.* 


|Key Requirements|Description|
|:---|---:|
|Breach Notification Rule|TSHI must notify affected patients, HHS, and potentially the media within 60 days of discovering a breach affecting unsecured ePHI|
|Business Associate Liability|Business Associates are directly liable for HIPAA compliance under HITECH|
|Increased Penalties|HITECH increased maximum HIPAA penalties and required HHS to impose penalties for willful neglect|
|Meaningful Use|Encourages adoption of EHR systems with security standards built in| 

**Breach Notification Requirements:**

|Breach Size|Who Must Be Notified|Timeline|
|:---|:---:|---:|
|Any size breach|Affected individuals|Within 60 days of discovery|
|500+ individuals in a state|Affected individuals + prominent media outlets in that state|Within 60 days of discovery|
|500+ individuals total|HHS; listed publicly on HHS breach portal|Within 60 days of discovery|
|Fewer than 500 individuals|HHS; submitted annually|Within 60 days of end of calendar year|

**New Jersey Identity Theft Prevention Act**

*New Jersey Identity Theft Prevention Act (N.J.S.A. 56:8-161 et seq.)
Enforced By: New Jersey Division of Consumer Affairs
Applicability to TSHI: TSHI must comply as a business operating in New Jersey that maintains personal information of NJ residents.* 

|Key Requirements|Description|
|:---|---:|
|Breach Notification|Must notify affected NJ residents in the most expedient time possible following discovery of a breach of personal information|
|Notification Content|Notice must describe the breach, type of information involved, and steps individuals can take to protect themselves|
|Notification to State|Must notify the New Jersey Division of Consumer Affairs when notifying more than 1,000 residents simultaneously|

**New York SHIELD Act** 

*New York Stop Hacks and Improve Electronic Data Security Act (SHIELD Act)
Enforced By: New York State Attorney General
Applicability to TSHI: TSHI must comply as an organization that owns or licenses private information of New York residents through its Bronx clinic.* 

|Key Requirements|Description|
|:---|---:|
|Breach Notification|Must notify affected NY residents in the most expedient time possible|
|Reasonable Security|Must implement and maintain reasonable safeguards to protect private information|
|Expanded Definition of Private Information|Includes biometric information, email credentials, and account numbers in addition to traditional PII| 

**PCI-DSS**

*Payment Card Industry Data Security Standard
Enforced By: Payment Card Industry Security Standards Council (PCI SSC)
Applicability to TSHI: TSHI accepts credit and debit card payments for patient services and must comply with PCI-DSS to maintain payment processing capability.*

|PCI-DSS Control Objective|Key Requirements|
|:---|---:|
|Build and maintain a secure network|Firewall configuration standards; no vendor-supplied default passwords|
|Protect cardholder data|Protect stored cardholder data; encrypt transmission of cardholder data across open networks|
|Maintain a vulnerability management program|Use and regularly update antivirus; develop and maintain secure systems and applications|
|Implement strong access control measures|Restrict access to cardholder data by business need to know; assign unique IDs to each person with computer access|
|Regularly monitor and test networks|Track and monitor all access to network resources and cardholder data; regularly test security systems|
|Maintain an information security policy|Maintain a policy that addresses information security for all personnel|

**Applicable Security Framework**
--- 

**NIST Cybersecurity Framework (CSF)**

*Publisher: National Institute of Standards and Technology
Type: Voluntary Framework
Applicability: TSHI has adopted the NIST CSF as a guiding framework for its cybersecurity program.*

The NIST CSF organizes cybersecurity activities into six core functions: 

|Function|Description|Relevance to TSHI|
|:---|:---:|---:|
|Govern|Establish and monitor cybersecurity risk management strategy and policy|CISO and security governance structure|
|Identify|Understand assets, risks, and vulnerabilities|Asset inventory and risk assessment|
|Protect|Implement safeguards to protect critical services|Access controls, encryption, training|
|Detect|Implement capabilities to identify cybersecurity events|Logging, monitoring, incident detection|
|Respond|Take action regarding detected cybersecurity incidents|Incident response plan and procedures|
|Recover|Maintain resilience and restore capabilities after an incident|Business continuity and disaster recovery| 

**NIST SP 800-53 Rev. 5 - Security and Privacy Controls** 

*Publisher: National Institute of Standards and Technology
Type: Control Catalog
Applicability: Used to select and map security controls to risks identified in this assessment.* 

NIST SP 800-53 provides a comprehensive catalog of security and privacy controls organized into 20 control families. Selected controls from this catalog are mapped to TSHI's identified risks in [Annex]{../Annexes/Annex_B_NIST_Control_Mapping.md} 

**Regulatory Compliance Summary** 

|Regulation/Framework|Overall Compliance Status|Primary Gaps|
|:---|:---:|---:|
|HIPAA Privacy Rule|Mostly Compliant|Minor gaps in workforce training and access management|
|HIPAA Security Rule — Administrative|Partially Compliant|Risk assessment in progress; security training not role-specific|
|HIPAA Security Rule — Physical|Partially Compliant|Physical access controls weak at outpatient clinic locations|
|HIPAA Security Rule — Technical|Partially Compliant|No MFA on EHR; no SIEM; inconsistent audit controls|
|HITECH Breach Notification|Compliant; Plan Exists|Breach response plan not recently tested|
|NJ Identity Theft Prevention Act|Compliant; Plan Exists|Notification procedures in place|
|NY SHIELD Act|Partially Compliant|Reasonable security controls need strengthening at Metro Clinic|
|PCI-DSS|Partially Compliant|Cardholder data environment needs stronger segmentation|
|NIST CSF 2.0|Partially Adopted|Detect and Govern functions underdeveloped|
|NIST SP 800-53|In Progress|Control mapping underway via this assessment|

**Related Documents** 
--- 

|Document|Path|
|:---|---:|
|Organization Profile|[Organization Profile](Organization_Profile.md)|
|IT Environment|[IT Environment](IT_Environment.md)|
|NIST 800-30 Methodology|[NIST 800-30 Methodology](../Docs/NIST_800-30_Methodology.md)|
|Risk Assessment Policy|[Risk Assessment Policy](../Docs/Risk_Assessment_Policy.md)|
|Compliance Matrix|[Compliance Matrix](../Matrices/Compliance_Matrix.md)|
|NIST Control Mapping|[NIST Control Mapping](../Annexes/Annex_B_NIST_Control_Mapping.md)|

*Document ID: TSHI-ORG-REG-001 | Version: 1.0 | Classification: Internal Use Only | Case Study — Tri-State Health Initiative (TSHI)*
