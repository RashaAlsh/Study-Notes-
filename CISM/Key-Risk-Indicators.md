# CISM Operations: Intrusion Detection Systems (IDS)

## 1. Primary Objective
To provide visibility into suspicious activity and act as a detective control within the "Defense in Depth" strategy.

## 2. Key Terminology
*   **False Positive:** A legitimate action wrongly flagged as a threat (causes "alert fatigue").
*   **False Negative:** A real attack that the IDS missed (the most dangerous scenario).
*   **True Positive:** A real attack correctly identified.
*   **Confidence Level:** The level of certainty the system has that an alert is valid.

## 3. Placement Strategy
*   **Outside Firewall:** High noise, shows all "knocks on the door."
*   **Inside Firewall (DMZ):** Detects attacks that bypassed perimeter defenses.
*   **Internal Segments:** Identifies lateral movement from an APT or an internal threat.

## 4. Integration with SIEM
An IDS is most effective when its logs are fed into a **Security Information and Event Management (SIEM)** system, allowing for cross-correlation with logs from firewalls, servers, and DLP.
