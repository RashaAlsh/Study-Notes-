# Technological Controls (ISO/IEC 27002:2022)

Technological controls (also called **Technical** or **Logical controls**) are the digital safeguards used to protect systems, networks, and data.

While **Organizational** and **People** controls define rules and responsibilities, **Technological controls enforce them**.

---

## 1. Identity and Access Management (IAM)

The **gatekeeper** of digital systems.

- **Access Control**
  - Ensures users only access what they need  
  - Based on the **Principle of Least Privilege**

- **Authentication**
  - Verifies user identity  
  - Multi-Factor Authentication (MFA):
    - Something you know (password)
    - Something you have (token)
    - Something you are (biometric)

- **Privileged Access Rights**
  - Admin-level access must be:
    - Restricted
    - Monitored
    - Assigned to minimal users

---

## 2. Infrastructure & Network Security

Protects the systems that transport data.

- **Network Segregation**
  - Divide networks into smaller segments  
  - Example: Guest Wi-Fi vs internal systems  

- **Firewalls & Gateways**
  - Filter incoming and outgoing traffic  
  - Enforce security policies  

- **Intrusion Detection / Prevention Systems (IDS/IPS)**
  - Monitor traffic for suspicious behavior  
  - Detect and block potential attacks  

---

## 3. Data Protection & Cryptography

Protects the data itself.

- **Cryptography (Encryption)**
  - Converts readable data into unreadable form  
  - Protects:
    - Data at rest  
    - Data in transit  

- **Data Masking**
  - Hides sensitive data (e.g., partial credit card display)

- **Backup & Redundancy**
  - Ensures data recovery after:
    - System failures  
    - Ransomware attacks  

---

## 4. System & Software Security

Ensures systems and applications are secure.

- **Vulnerability Management**
  - Regular scanning for weaknesses  
  - Apply patches and updates  

- **Malware Protection**
  - Antivirus and anti-malware tools  
  - Detect and remove malicious software  

- **Secure Coding**
  - Integrate security into the SDLC  
  - Prevent vulnerabilities during development  

---

## Summary Table: Technical Tools

| Control        | Goal                    | Example                  |
|----------------|-------------------------|--------------------------|
| Authentication | Confirms identity       | MFA / Biometrics         |
| Encryption     | Protects confidentiality| SSL/TLS / BitLocker      |
| Filtering      | Blocks threats          | Firewalls / Web Filters  |
| Logging        | Ensures accountability  | Audit Trails / SIEM      |
| Patching       | Fixes vulnerabilities   | OS / Firmware Updates    |

---

## Why It Matters for the Exam

Technological controls are powerful—but **not sufficient on their own**.

They depend on:
- **Organizational Controls** → Policies mandate their use  
- **People Controls** → Users apply them correctly  

### Key Insight
> Technology fails without policy and training.

---

## Summary

Technological controls:
- Enforce security rules at the system level  
- Protect data, networks, and applications  
- Work best when combined with people and organizational controls  

They form the **operational backbone** of modern cybersecurity.