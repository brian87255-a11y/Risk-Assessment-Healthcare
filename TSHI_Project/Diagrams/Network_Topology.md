<!-- 
WHAT IS THIS FILE?
This file documents TSHI's network topology — the physical and logical
layout of how all systems, locations, and network segments connect.
A network diagram is one of the most important documents in a security assessment
because it gives the assessor and the reader a visual understanding
of the attack surface — where data flows, where boundaries exist,
and where the gaps are.
In a real organization this would be a proper diagram created in
Visio, Lucidchart, or draw.io and exported as an image or PDF.
Since we are working in GitHub markdown, we use ASCII art diagrams
combined with detailed written descriptions — this is a common and
accepted approach for markdown-based security documentation.
The topology documented here is derived from the IT Environment file
and reflects the hub-and-spoke architecture described there.
Understanding network topology is fundamental for any security role —
you cannot identify network-based threats or recommend network controls
without understanding how the network is structured.
-->

# Network Topology — Tri-State Health Initiative (TSHI)

**Document ID:** TSHI-DIAG-NET-001
**Version:** 1.0
**Classification:** Internal Use Only — Confidential
**Last Updated:** August 2026
**Owner:** IT Director

>  **Security Notice:** This document contains sensitive network architecture information. Distribution is restricted to authorized IT and security personnel only. Do not share externally without CISO approval.

---

## 1. Purpose

<!-- 
The network topology document serves multiple purposes in the risk assessment:
1. It provides context for understanding how threats can move laterally
   through the network once an attacker gains initial access
2. It identifies the boundaries between network segments
   and where controls like firewalls and VLANs are implemented
3. It shows where the gaps in segmentation exist —
   for TSHI the primary gap is medical devices sharing the clinical network
4. It supports the vulnerability and risk findings by showing
   visually why certain risks are rated the way they are
For example: TSHI-RISK-003 (medical device exploitation) is rated Critical
in part because the diagram shows medical devices are NOT isolated
from the clinical workstations that access the EHR —
meaning a compromised infusion pump has a direct network path
to the system containing 85,000 patient records.
-->

This document provides a high-level overview of TSHI's network architecture across all four facilities. It supports the risk assessment by illustrating the attack surface, network segmentation status, and connectivity between key systems and locations.

---

## 2. High-Level Network Overview

<!-- 
The hub-and-spoke model means all clinic traffic flows back
to the main hospital campus before going anywhere else.
This is efficient and allows centralized management —
but it also means the main campus is a single point of failure.
If the main campus data center goes down, all clinics lose access
to centralized systems. This is part of why TSHI-RISK-010
(no secondary data center) is rated High.
The MPLS circuits are dedicated private connections between locations —
faster and more reliable than internet connections
but more expensive and with limited redundancy.
The VPN failover provides a backup path over the public internet
if an MPLS circuit fails — but VPN capacity is lower
and this failover has not been formally tested.
-->

TSHI operates a **hub-and-spoke network** with the main hospital campus in Newark, NJ serving as the central hub. All three outpatient clinic locations connect to the hub via dedicated MPLS circuits with VPN failover.

```
┌─────────────────────────────────────────────────────────────────┐
│                    INTERNET / PUBLIC CLOUD                       │
│              (Microsoft 365, AWS S3, SaaS Vendors)              │
└───────────────────────────┬─────────────────────────────────────┘
                            │
                    [ISP Redundant Links]
                            │
┌───────────────────────────▼─────────────────────────────────────┐
│                  TSHI MAIN CAMPUS — NEWARK, NJ                  │
│                                                                  │
│  ┌─────────────┐    ┌──────────────┐    ┌────────────────────┐  │
│  │  PERIMETER  │    │  CORE NETWORK│    │   DATA CENTER      │  │
│  │  FIREWALL   │───▶│  SWITCHES /  │───▶│  (On-Premise)      │  │
│  │  (NGFW)     │    │  ROUTERS     │    │  - VMware (40 VMs) │  │
│  └─────────────┘    └──────┬───────┘    │  - SAN Storage     │  │
│                            │            │  - AD Controllers  │  │
│              ┌─────────────┼──────────┐ │  - Veeam Backup    │  │
│              │             │          │ └────────────────────┘  │
│              ▼             ▼          ▼                          │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐            │
│  │  CLINICAL    │ │  ADMIN       │ │  MEDICAL     │            │
│  │  NETWORK     │ │  NETWORK     │ │  DEVICE      │            │
│  │  (VLAN 10)   │ │  (VLAN 20)   │ │  NETWORK     │            │
│  │              │ │              │ │  (NOT FULLY  │            │
│  │  EHR WS      │ │  Office WS   │ │  SEGMENTED)  │            │
│  │  Thin Clients│ │  Admin Laptops│ │              │            │
│  │  Clinical Tab│ │  Billing Sys │ │  Infusion    │            │
│  └──────────────┘ └──────────────┘ │  Pumps       │            │
│                                     │  Patient Mon.│            │
│  ┌──────────────────────────────┐  │  Imaging Sys │            │
│  │  GUEST / PATIENT Wi-Fi       │  └──────────────┘            │
│  │  (FULLY ISOLATED — VLAN 99)  │                               │
│  │  No access to internal nets  │                               │
│  └──────────────────────────────┘                               │
│                                                                  │
└──────────────────────────┬──────────────────────────────────────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
        [MPLS + VPN] [MPLS + VPN] [MPLS + VPN]
        Failover     Failover     Failover
              │            │            │
              ▼            ▼            ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│  NORTH CLINIC   │ │  EAST CLINIC    │ │  METRO CLINIC   │
│  Paterson, NJ   │ │  Jersey City,NJ │ │  Bronx, NY      │
│                 │ │                 │ │                 │
│  ~120 Staff     │ │  ~130 Staff     │ │  ~150 Staff     │
│  Clinical WS    │ │  Clinical WS    │ │  Clinical WS    │
│  Admin WS       │ │  Admin WS       │ │  Admin WS       │
│  Medical Devices│ │  Medical Devices│ │  Medical Devices│
│                 │ │                 │ │                 │
│  ⚠️ Key Locks   │ │  ⚠️ Key Locks   │ │  ⚠️ Key Locks   │
│  No Badge Access│ │  No Badge Access│ │  No Badge Access│
└─────────────────┘ └─────────────────┘ └─────────────────┘
```

---

## 3. Main Campus Network Segments

<!-- 
Network segmentation divides the network into separate zones
controlled by firewall rules or VLAN configuration.
The goal is to limit lateral movement — if an attacker
compromises one segment, segmentation prevents them from
freely moving to other segments.
TSHI has partial segmentation — VLANs exist for clinical and administrative
but the boundaries between them are not strictly enforced,
and medical devices are not fully isolated.
The guest Wi-Fi is the ONLY fully isolated segment —
it cannot reach any internal systems at all.
The security gap is that a compromised medical device on the medical device network
has a path to reach clinical workstations
because they share or have minimal barriers between segments.
-->

| Segment Name | VLAN | Systems Included | Segmentation Status | Access to EHR |
|---|---|---|---|---|
| Clinical Network | VLAN 10 | EHR workstations, thin clients, clinical tablets, nursing stations | Partially segmented from administrative | Yes — primary access point |
| Administrative Network | VLAN 20 | Office workstations, admin laptops, billing systems, HR systems | Partially segmented from clinical | Limited — admin functions only |
| Medical Device Network | No dedicated VLAN | Infusion pumps, patient monitors, imaging systems, lab analyzers | NOT fully segmented — shares traffic with clinical | Indirect — via clinical network |
| Management Network | VLAN 30 | IT infrastructure management, server consoles, network device management | Partially segmented | Yes — administrative access |
| Guest / Patient Wi-Fi | VLAN 99 | Patient and visitor wireless devices | Fully isolated — no internal access | No |
| Data Center | Internal | All virtualized servers, SAN, AD controllers, backup systems | Protected by access controls — not separately segmented from management | Yes — hosts EHR |

---

## 4. Perimeter Security Architecture

<!-- 
The perimeter is the boundary between TSHI's internal network
and the outside world — primarily the internet.
The NGFW (Next-Generation Firewall) is the primary control at this boundary.
Unlike a traditional packet-filtering firewall that only looks at
IP addresses and ports, an NGFW can inspect the content of traffic,
identify applications, and block threats based on what the traffic IS
rather than just where it came from.
The perimeter is only one layer of defense — defense in depth
requires controls inside the network as well.
TSHI's perimeter is reasonably mature — the gaps are INSIDE the network
(limited internal segmentation, no SIEM, no EDR)
rather than at the perimeter.
-->

```
INTERNET
    │
    │ [Dual ISP Links — Redundant]
    │
    ▼
┌──────────────────────────────────────┐
│         PERIMETER FIREWALL           │
│         (Next-Gen Firewall)          │
│                                      │
│  ✅ Stateful inspection              │
│  ✅ Application-layer filtering      │
│  ✅ Intrusion Prevention (IPS)       │
│  ✅ VPN termination                  │
│  ⚠️ No internal network IPS         │
│  ⚠️ No web application firewall      │
└──────────────────┬───────────────────┘
                   │
    ┌──────────────┼──────────────┐
    │              │              │
    ▼              ▼              ▼
[Internal      [DMZ Zone]     [VPN Access
 Network]      (If added)      Gateway]
               Public-facing   Remote staff
               services        and vendors
```

**Email Security Architecture:**

```
INBOUND EMAIL (Internet)
    │
    ▼
┌─────────────────────────────────────┐
│     Microsoft Defender for          │
│     Office 365 (Basic Tier)         │
│                                     │
│  ✅ Spam filtering                  │
│  ✅ Basic malware scanning          │
│  ⚠️ No advanced phishing protection │
│  ⚠️ No attachment sandboxing        │
│  ⚠️ No impersonation protection     │
└──────────────────┬──────────────────┘
                   │
                   ▼
          Microsoft 365 Tenant
          (Exchange Online)
```

---

## 5. Remote Access Architecture

<!-- 
Remote access has become critical in healthcare since the pandemic.
Clinical staff working from home, administrators accessing systems remotely,
and vendors providing remote support all require secure remote access.
TSHI uses Cisco AnyConnect VPN — an industry standard solution.
The gap is that MFA is only partially enforced —
some users can still authenticate with password only.
This is one of the easiest vulnerabilities for an attacker to exploit:
steal a password (via phishing), connect to the VPN, access the EHR.
No second factor to stop them.
This is captured in VT-002 in the Vulnerability Identification file
and addressed in TSHI-RISK-002 in the Risk Register.
-->

```
REMOTE USER / VENDOR
(Internet — Untrusted Network)
    │
    │ [Encrypted VPN Tunnel — TLS]
    │
    ▼
┌──────────────────────────────────┐
│         VPN GATEWAY              │
│    (Cisco AnyConnect)            │
│                                  │
│  Authentication:                 │
│  ✅ Username + Password          │
│  ⚠️ MFA — partially deployed    │
│     (not enforced for all users) │
│                                  │
│  Split Tunneling: Disabled       │
│  Session Logging: Basic          │
└──────────────┬───────────────────┘
               │
               ▼
      Internal Network Access
      (Same access as on-site
       based on user role)
```

---

## 6. Cloud Architecture

<!-- 
TSHI uses a hybrid cloud model — some workloads on-premise,
some hosted in public cloud.
The shared responsibility model applies here:
Microsoft is responsible for the security OF the cloud (infrastructure),
TSHI is responsible for security IN the cloud (configurations, access, data).
The risk at TSHI is cloud misconfiguration — particularly in
Microsoft 365 and AWS S3 — which is captured as TSHI-RISK-011.
The dotted lines in the diagram indicate that these cloud connections
go over the public internet (encrypted) rather than through
a dedicated private connection like MPLS.
-->

```
┌─────────────────────────────────────────────────────────────────┐
│                      CLOUD ENVIRONMENT                           │
│                                                                  │
│  ┌──────────────────────┐    ┌──────────────────────────────┐  │
│  │   MICROSOFT AZURE    │    │        AWS                    │  │
│  │                      │    │                               │  │
│  │  Microsoft 365       │    │  S3 — Offsite Backup Storage  │  │
│  │  - Exchange Online   │    │  (Encrypted backups from      │  │
│  │  - SharePoint        │    │   on-premise Veeam)           │  │
│  │  - Teams             │    │                               │  │
│  │  - Epic Cloud Modules│    │  ⚠️ Configuration not         │  │
│  │                      │    │     regularly audited         │  │
│  │  ⚠️ MFA partially    │    └──────────────────────────────┘  │
│  │     deployed         │                                        │
│  └──────────────────────┘                                        │
│                                                                  │
│  ┌──────────────────────┐    ┌──────────────────────────────┐  │
│  │  SaaS — Patient      │    │  SaaS — HRIS                  │  │
│  │  Scheduling          │    │  (Employee Records, Payroll)  │  │
│  │  (Telehealth also    │    │                               │  │
│  │   SaaS)              │    │  MFA: ✅ Enforced             │  │
│  │  MFA: ⚠️ Partial    │    └──────────────────────────────┘  │
│  └──────────────────────┘                                        │
└─────────────────────────────────────────────────────────────────┘
          ▲                  ▲
          │ (Encrypted       │ (Encrypted
          │  HTTPS/TLS)      │  HTTPS/TLS)
          │                  │
┌─────────┴──────────────────┴──────────────────────┐
│              TSHI INTERNAL NETWORK                  │
│              (Main Campus + Clinics)                │
└─────────────────────────────────────────────────────┘
```

---

## 7. Identified Network Security Gaps

<!-- 
This section summarizes the network-level security gaps
visible from the topology.
Each gap maps directly to a risk in the Risk Register.
This is the section that ties the diagram back to the assessment —
showing that the topology is not just a pretty picture
but a tool that reveals security weaknesses.
-->

| Gap | Location | Risk Register Reference | Recommended Remediation |
|---|---|---|---|
| Medical devices not fully segmented | Main campus and all clinics | TSHI-RISK-003 | Implement dedicated medical device VLAN with strict ACLs |
| No internal network IPS/SIEM | Entire internal network | TSHI-RISK-001, TSHI-RISK-009 | Deploy SIEM with network sensor coverage |
| MFA not enforced on VPN for all users | VPN Gateway | TSHI-RISK-002 | Enforce MFA for all VPN connections — Phase 2 priority |
| Key locks at outpatient clinics | North, East, Metro clinics | TSHI-RISK-008 | Upgrade to electronic badge access at all three locations |
| No dedicated DMZ for public-facing services | Main campus perimeter | Future consideration | Implement DMZ if public-facing web services are added |
| Cloud configurations not regularly audited | Microsoft 365 and AWS S3 | TSHI-RISK-011 | Deploy CSPM tool; establish cloud configuration baselines |
| No web application firewall (WAF) | Internet perimeter | Future consideration | Evaluate WAF for patient portal protection |
| VPN failover to clinics not tested | All clinic MPLS connections | TSHI-RISK-013 | Conduct formal VPN failover test for each clinic location |

---

## 8. Legend

```
LEGEND:
━━━━━━━  Physical or MPLS connection (dedicated private link)
- - - -  Internet connection (encrypted, public network)
──────▶  Traffic direction
[VLAN X] Virtual LAN segment
✅       Control in place and effective
⚠️       Control partially implemented or with identified gap
❌       Control absent
```

---

**Diagram Maintenance**
---

| Requirement | Standard |
|---|---|
| Review frequency | Annually and after any significant network change |
| Update triggers | New facility, new network segment, significant infrastructure change, post-incident review |
| Version control | All diagram changes must be version controlled with date and description of change |
| Distribution | Restricted to IT and security staff — CISO approval required for external distribution |


**Related Documents**
---

| Document | Path |
|---|---|
| IT Environment | [IT Environment](../Organization/IT_Environment.md) |
| Asset Inventory | [Asset Inventory](../Risk/Asset_Inventory.md) |
| Vulnerability Identification | [Vulnerability Identification](../Risk/Vulnerability_Identification.md) |
| Risk Register | [Risk Register](../Risk/Risk_Register.md) |



*Document ID: TSHI-DIAG-NET-001 | Version: 1.0 | Classification: Internal Use Only — Confidential | Case Study — Tri-State Health Initiative (TSHI)*
