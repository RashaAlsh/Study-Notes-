# CISM Control: Privileged Access Management (PAM)

## 1. Key Objectives
* **Prevent Credential Theft:** Mitigate Pass-the-Hash and Golden Ticket attacks.
* **Auditability:** Provide an irrefutable trail of administrative actions.
* **Minimize Attack Surface:** Reduce the number of permanent admin accounts.

## 2. PAM Control Framework
| Control Type | Implementation | CISM Goal |
| :--- | :--- | :--- |
| **Administrative** | Policy defining who qualifies for "Privileged" status. | Governance |
| **Technical** | Multi-Factor Authentication (MFA) for all admin logins. | Risk Mitigation |
| **Operational** | Monthly review of privileged account memberships. | Compliance |
| **Physical** | Secure access to "Break Glass" accounts/physical safes. | Recovery |

## 3. The "Break Glass" Account
* **Definition:** An emergency-only account used when the primary PAM system or SSO fails.
* **Protocol:** Must be highly monitored, have a long/complex password split between two people, and trigger an immediate alert when used.
