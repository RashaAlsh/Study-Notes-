# CISM Control: Data Loss Prevention (DLP)

## 1. Detection Methods
| Method | Description | Example |
| :--- | :--- | :--- |
| **Pattern Matching** | Looks for specific formats. | Credit Card numbers (16 digits), SSNs. |
| **Fingerprinting** | Matches exact files or snippets. | Protecting a specific sensitive CAD drawing. |
| **Exact Data Match (EDM)** | References a database. | Preventing a customer list from being exported. |
| **Metadata Tagging** | Checks for classification tags. | Blocking files labeled "Top Secret" by the Data Owner. |

## 2. Response Actions
* **Log/Report:** Records the event but allows the data to pass (Testing phase).
* **Block:** Stops the transmission immediately (High-confidence rules).
* **Encrypt:** Automatically applies protection (e.g., encrypting an outbound email).
* **Notify:** Alerts the user or manager of a policy violation.

## 3. Governance Requirements
* **Privacy:** DLP can be invasive. Must align with legal/HR (GDPR/CCPA).
* **False Positives:** High rates of false alarms can break business processes.
* **Baseline:** You cannot implement DLP without a mature **Data Classification** scheme.
