# NIST SP 800-30 Risk Assessment Methodology 

What is the NIST SP 800-30? 

**NIST Special Publication 800-30 Revision 1** titled Guide for Conduction Risk Assessment, is a cyber security framework published by the National Institute of Standards and Technology under the  U.S. Department of Commerce. It provided organizations with standard methodology for identifying, analyzing, and responding to information security risks. 

NIST SP 800-30 is part of a boarder NIST SP 800 series, which covers a wide rage of information security topics used across federal agencies, healthcare organization, and private sector entities. 

# WHY NIST SP 800-30 for Healthcare  

Healthcare organization subject to the Healthcare Insurance Portability and Accountability Act are required under HIPAA Security Rule (45 CFR § 164.308(a)(1)) to conduct an accurate and thorough risk assessment of potential risks to the confidentiality, integrity, and availability of electronic Protected Health Information (ePHI) 

NIST SP 800-30 is widely recognized as an accepted methodology for satisfying this requirement because: 

- Provides a structured and documented process.
- Aligns with the NIST Cybersecurity Framework (CSF) used across federal and regulated industries
- Supports compliance with HIPAA, HITECH and other regulations
- Publicly available and maintained by federal authorities

# The Three-Step Process 

NIST SP 800-30 defines risk assessment as a three step process: 

> [!NOTE]
> **Step 1: Prepare for the Assessment**
> Gather all necessary documentation, define the evaluation scope, and schedule the kickoff meeting with the team.
> 
> **Step 2: Conduct the Assessment**
> Interview key stakeholders, review the technical infrastructure, and log any discovered vulnerabilities or process gaps.
> 
> **Step 3: Maintain the Assessment**
> Update the documentation regularly, track the remediation progress, and schedule the next recurring review period.


# Step 1 - Prepare for the Assessment 

This preparation step establishes the context and the foundation for the risk assessment. It ensures that the team understands the organization's environment, objectives, and constraints before identifying risks. 

Key activities includes: 

| Activity  |  Description | 
| -------- | -------- | 
|Define purpose and scope | Establish what system and data are being assess and why | 
|Identify | Document what is out of scope or assumed to be true |
|Identify information sources | Determine what documentation, tool and personnel will be used | 
|Identify the risk model  | Define how likelihood and impact will be measured and scored | 

For TSHI, this includes documenting the organization's profile, IT environment, regulatory obligations, and the assets. This are contained in the Organization folder of this repository.

# Step 2 - Conduct the Assessment 

The steps is the core of the assessment. It follows a logical sequence where the next task adds on the previous one. 

**2a - Identity Threat Sources and Events**  

Identify realistic threat sources that could harm TSHI's system or data, and the specific events those sources might cause. 

**Threat sources examples:** Cybercriminals, malicious insiders, nation-states actors, and specific events those sources might cause. 

**Threat event examples:** Ransomware, unauthorized access to ePHI, phishing attacks, system outages 

**2b - Identity Vulnerabilities and Predisposing Condtions**

Identify weakness in TSHI's systems, processes, and environment that could be exploited by identified threat sources. 

**Vulnerability examples:** Unpatched software, weak access controls, lack of staff security training, unencrypted data transmissions 

**2c - Determine Likeihood** 

For each identified risk, determine the probability that the threat event will given the existing vulnerabilities and current controls 

| Likelihood | Description | 
| -------- | -------- | 
| High  | Threat source is highly motivated and capable; vulnerability is easily exploited | 
| Moderate  |  The Threat is capable but faces challenges to exploitation |
| Low  |  The threat source lacks capabilities; vulnerability is difficult to exploit | 

**2d - Determine Impact** 

Determine the magnitude of harm that would result if the threat explioted the vulnerability 

| Impact | Description | 
| -------- | -------- | 
| High  | Severe harm - significant loss of ePHI, major financial penalties, patient safety risk, organizational failure | 
| Moderate  | Significant harm - limited ePHI exposure, operational disruption, reputational damage |
| Low  | Minor harm - minimal data exposure, limited operational harm, recoverable quickly | 

**2e - Determine Risk** 

Risk is determined by combining the likelihood of a threat even with the impact it would cause. The result is a risk rating used to prioritize remediation efforts. 

> [!NOTE]
> **Likeihood * Impact**

Risk ratings are documented in the **Risk Register** are visualized in the **Risk Rating Matrix** found in the Matrices folder. 

# Step 3 - Maintain the Assessment 

Risk assessment are not static documents. Step 3 ensure the assessment remaines accurate and relevant over time. 

Key maintenance activities includes: 

| Activity  |  Frequency | 
| -------- | -------- | 
| Monitor identified risks for changes in likelihood or impact | Ongoing | 
|Update the risk register when new threats or vulnerabilities are discovered | As needed |
|Review the full assessment after significant system or organizational changes | As needed | 
|Conduct a full assessment | Annually or per policy | 

# Relationship to Other NIST Publications 

NIST SP 800-30 is designed to work alongside other NIST publications: 

| Publication  |  Title |  Relationship to 800-30 | 
| -------- | -------- | -------- | 
| NIST SP 800-39 | Managing Information Security Risk  | Parent framework; defines the overall risk management process that 800-30 supports |
| NIST SP 800-53 | Security and Privacy Controls | Provides the controls catalog used to address risks identified in 800-30 |
| NIST SP 800-37 | Risk Management Framework (RMF) | Integrates 800-30 assessments into a system authorization process |
| NIST CSF | Cybersecurity Framework | Voluntary framework that complements 800-30 for broader cyber risk management | 

Framework: NIST SP 800-30 Rev. 1 | Publisher: National Institute of Standards and Technology | Case Study — Tri-State Health Initiative (TSHI)
