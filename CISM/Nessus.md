# CISM Operations: Vulnerability Scanning (Nessus)

## 1. Key Objectives
*   **Identify Vulnerabilities:** Discover unpatched software and weak configurations.
*   **Compliance:** Validate systems against CIS or internal security standards.
*   **Remediation:** Provide technical teams with prioritized "how-to-fix" instructions.

## 2. Scan Type Comparison
| Feature | Non-Authenticated | Credentialed |
| :--- | :--- | :--- |
| **Visibility** | Low (Services only) | High (OS, Registry, Apps) |
| **Intrusiveness** | Lower | Higher |
| **Accuracy** | Prone to False Positives | Extremely Accurate |
| **CISM Goal** | External Attack Surface | Internal Risk Profile |

## 3. Operational Best Practices
*   **Enable Safe Checks:** Mandatory for production environments.
*   **Schedule Scans:** Off-peak hours to avoid network congestion.
*   **Integration:** Feed scan results into a **SIEM** for cross-correlation with IDS/IPS alerts.
