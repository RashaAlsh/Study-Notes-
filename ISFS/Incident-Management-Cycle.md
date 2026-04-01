# Incident Management Cycle (PDCA Model)

In *Foundations of Information Security*, the **incident management cycle** is a key part of the **"Check"** and **"Act"** phases of the PDCA model. It ensures that security incidents are handled systematically to minimize damage and prevent recurrence.

---

## Stages of the Incident Management Cycle

### 1. Detection and Registration

The cycle begins when an event is identified as a potential security incident.

#### Detection
- Automated systems (e.g., Intrusion Detection Systems - IDS)
- Log monitoring
- Employee reports

#### Registration
- All incidents must be logged
- Creates an audit trail ("paper trail")
- Helps identify attack patterns over time

---

### 2. Classification and Prioritization

Not all incidents are equal; they must be assessed and prioritized.

#### Classification
- Type of incident:
  - Malware infection
  - Physical breach
  - Data leak

#### Prioritization
- Based on business impact
- Example:
  - Critical system outage > minor user issue

---

### 3. Investigation and Diagnosis

Security professionals analyze the incident in detail.

#### Analysis
- Identify root cause:
  - Technical issue (e.g., unpatched software)
  - Human error (e.g., phishing attack)

#### Evidence Collection
- Important for:
  - Legal action
  - Insurance claims
- Maintain integrity of evidence

---

### 4. Recovery (Resolution)

Goal: Restore normal operations as quickly as possible.

#### Containment
- Prevent spread of the incident
- Example: Disconnect infected systems

#### Eradication
- Remove root cause
- Example: Delete malware

#### Restoration
- Restore systems from backups
- Verify proper functionality

---

### 5. Evaluation (Lessons Learned)

Often skipped, but one of the most critical stages.

#### Post-Mortem
- Review what happened
- Evaluate response effectiveness

#### Feedback Loop
- Feed insights back into the **Plan** phase of PDCA
- Improve policies, controls, and procedures

---

## Key Concept: Incident vs. Event

| Term     | Definition |
|----------|-----------|
| **Event**   | Any observable occurrence in a system (e.g., user login) |
| **Incident** | An event that negatively impacts security or operations |

---

## Summary

The incident management cycle ensures:
- Structured response to security breaches  
- Minimized damage and downtime  
- Continuous improvement through feedback  

It plays a vital role in maintaining a resilient and adaptive information security program.