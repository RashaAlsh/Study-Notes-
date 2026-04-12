#  The DAD Triad

In Information Security, the **DAD Triad** represents the three negative effects of a security breach. It is the direct inverse of the **CIA Triad** (Confidentiality, Integrity, Availability).

---

##  CIA vs.  DAD: The Inverse Relationship

| CIA Goal (Success) | DAD Outcome (Failure) | Definition of the Failure |
| :--- | :--- | :--- |
| **Confidentiality** | **Disclosure** | Unauthorized individuals gain access to sensitive data. |
| **Integrity** | **Alteration** | Data is modified, corrupted, or tampered with by unauthorized parties. |
| **Availability** | **Destruction** | Data or systems are deleted, rendered unusable, or made inaccessible. |

---

## 
# Breaking Down the DAD Components

### 1. Disclosure (The opposite of Confidentiality)
Disclosure occurs when data "leaks." This is the most common headline in news reports.
* **Examples:** A database dump posted on a dark web forum, a lost unencrypted laptop, or "shoulder surfing."
* **Impact:** Loss of competitive advantage, legal fines (GDPR/HIPAA), and loss of customer trust.

### 2. Alteration (The opposite of Integrity)
Alteration occurs when information is no longer trustworthy because it has been changed.
* **Examples:** A hacker changing bank account balances, a "Man-in-the-Middle" (MitM) attack altering a transaction, or accidental data corruption due to system bugs.
* **Impact:** Poor decision-making based on bad data, financial fraud, and loss of system reliability.

### 3. Destruction (The opposite of Availability)
Destruction (often including **Denial**) occurs when the service or data is gone or blocked.
* **Examples:** A Ransomware attack (Denial), a fire in a data center without backups (Destruction), or a DDoS attack (Denial).
* **Impact:** Business downtime, lost revenue, and inability to provide critical services.

---

##  Why the DAD Triad Matters to Leadership

Senior Leadership and the Board are often more interested in the **DAD Triad** than the CIA Triad because DAD describes **Risk Realization**.

* **Risk Assessment:** We use DAD to calculate the **Impact** of a threat. (e.g., "What is the financial impact of *Disclosure* of our client list?")
* **Incident Response:** When a breach occurs, the CISO must report which part of the DAD triad was affected to determine the legal notification requirements.

> **Key Takeaway:** If you are protecting the **CIA**, you are performing your "Due Care." If you are suffering from the **DAD**, you are dealing with a "Loss Event."
