# Threat Identification — Tri-State Health Initiative 

*Document ID: TSHI-RISK-TI-001 Version: 1.0 Classification: Internal Use Only — Confidential Last Updated: August 2026 Owner: Information Security Team* 

**Purpose** 
--- 

This document identifies and categorizes threat sources and threat events relevant to Tri-State Health Initiative. Threat identification is the second step of the NIST SP 800-30 risk assessment conduct phase and establishes the threat landscape against which TSHI's vulnerabilities and risks are evaluated. 

Threats are based on: 
- Relevance — whether the threat realistically applies to a regional healthcare network
- Historical precedent — whether similar organizations have faced this threat
- Threat actor capability and intent — whether the threat source has the means and motivation to act against TSHI

**Threat Source Categories** 
--- 

|Threat Source Category|Description|Examples|
|:---|:---:|---:|
|Adversarial, External|Individuals or groups outside TSHI with malicious intent|Cybercriminals, ransomware groups, nation-state actors, hacktivists|
|Adversarial, Internal|Individuals inside TSHI with malicious or negligent intent|Malicious employees, disgruntled staff, negligent users|
|Adversarial, Third Party|Vendors, contractors, or partners who introduce risk|Compromised vendor accounts, malicious insiders at third parties|
|Non-Adversarial, Structural|Environmental or technical failures with no malicious actor|Hardware failure, software errors, power outages|
|Non-Adversarial, Environmental|Natural or physical events outside human control|Hurricanes, flooding, fires, severe weather| 

**Threat Sources** 
--- 

**External Adversarial Threat Sources**

|Threat Source ID|Threat Source|Motivation|Capability|Relevance to TSHI|
|:---|:---:|:---:|:---:|---:|
|TS-EXT-001|Ransomware Groups|Financial gain through extortion|High — well-funded, sophisticated tooling|Very High — healthcare is primary ransomware target|
|TS-EXT-002|Cybercriminals (Data Theft)|Financial gain through sale of ePHI and PII|High — established criminal marketplace|Very High — patient records are highly valuable|
|TS-EXT-003|Nation-State Actors|Espionage, disruption of critical infrastructure|Very High — state-sponsored resources|Moderate — regional healthcare less targeted than federal agencies|
|TS-EXT-004|Hacktivists|Ideological motivation, public embarrassment|Moderate — varies by group|Low to Moderate — healthcare targeted during political events|
|TS-EXT-005|Opportunistic Attackers|Financial gain through low-effort exploitation|Low to Moderate — rely on known vulnerabilities|High — unpatched systems attract automated scanning|
|TS-EXT-006|Phishing Operators|Credential theft, initial access brokering|Moderate — commodity tooling widely available|Very High — healthcare staff are frequent phishing targets| 

**Internal Adversarial Threat Sources** 

|Threat Source ID|Threat Source|Motivation|Capability|Relevance to TSHI|
|:---|:---:|:---:|:---:|---:|
|TS-INT-001|Malicious Employee|Financial gain, revenge, ideology|Moderate — has legitimate access|High — 1,200 staff with varying access levels|
|TS-INT-002|Negligent Employee|No malicious intent — accidental harm|N/A — unintentional|Very High — human error is leading cause of breaches|
|TS-INT-003|Disgruntled Employee|Revenge against organization|Moderate — depends on role and access|Moderate — elevated during staff transitions|
|TS-INT-004|Privileged User Abuse|Financial gain, curiosity|High — IT staff have broad system access| have broad system accessHigh — IT and clinical admin accounts have elevated privileges| 

**Third-Party Threat Sources** 

|Threat Source ID|Threat Source|Motivation|Capability|Relevance to TSHI|
|:---|:---:|:---:|:---:|---:|
||||||
||||||
||||||
