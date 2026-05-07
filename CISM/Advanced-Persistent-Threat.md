# CISM – Advanced Persistent Threats (APT)

In the **CISM** context, an **Advanced Persistent Threat (APT)** is defined as a sophisticated, resource-rich, and long-term attack campaign targeting a specific organization. Unlike traditional malware, the primary goal of an APT is often strategic—such as espionage, intellectual property theft, or infrastructure sabotage—rather than immediate financial gain.

---

# 1. The Three Pillars of an APT

## Advanced
Attackers possess significant funding and technical expertise, utilizing custom tools and **Zero-day vulnerabilities**.

## Persistent
Attackers are goal-oriented; if one entry point is blocked, they pivot to another and remain in the environment for extended periods (**Dwell Time**).

## Threat
These are organized entities, often state-sponsored or high-level criminal syndicates, with clear strategic objectives.

---

# 2. APT Lifecycle

| Stage | Action | ISM Focus |
| :--- | :--- | :--- |
| **1. Reconnaissance** | Gathering intel on employees and technology. | Awareness Training / OSINT reduction |
| **2. Initial Intrusion** | Phishing, 0-days, or supply chain compromise. | Defense in Depth / MFA / EDR |
| **3. Command & Control (C2)** | Establishing a "beacon" to the attacker server. | Egress Filtering / Traffic Analytics |
| **4. Lateral Movement** | Moving from standard user to Admin rights. | PAM / Network Segmentation |
| **5. Exfiltration** | Packaging and sneaking data out. | DLP / Traffic Baselines |
| **6. Persistence** | Creating backdoors for long-term access. | Root Cause Analysis (RCA) |

---

# 3. Managerial Strategy (The CISO's View)

## "Assume Breach" Mindset

The CISM framework encourages an **"Assume Breach"** philosophy regarding APTs. Because these threats are designed to bypass perimeter defenses, the Information Security Manager (ISM) must prioritize **Detection and Response** over mere prevention.

---

## IoC vs. IoA

### Indicators of Compromise (IoC)
Evidence that an attack *has* occurred.

**Examples:**
- Malicious file hash
- Known malicious IP address
- Compromised domain

### Indicators of Attack (IoA)
Evidence of *how* an attack is progressing.

**Examples:**
- Unusual account behavior
- Unauthorized script execution
- Privilege escalation attempts

---

# 4. Key Exam Concepts

## Dwell Time
The number of days an attacker remains inside the environment before detection.

> Reducing dwell time is a critical **KPI** for security operations.

---

## Threat Hunting
Proactively searching through the network for hidden indicators of APT activity that automated tools might miss.

---

## Root Cause Analysis (RCA)
To prevent the APT from returning, the ISM must ensure the **original entry point** is identified and remediated.

---

# Quick Summary

- APTs are **advanced, persistent, and strategic** attacks.
- Traditional prevention alone is insufficient.
- CISM emphasizes:
  - Detection
  - Monitoring
  - Response
  - Threat Hunting
  - Root Cause Analysis
- The goal is to reduce:
  - **Dwell Time**
  - Data Exfiltration Risk
  - Long-term Persistence

---