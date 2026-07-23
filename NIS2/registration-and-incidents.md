Registration & Incident Reporting Obligations

## 1. Entity Registration Requirements (Article 3(4))
Organizations operating across multiple EU Member States **must register each local entity individually** with the respective national competent authority.

### Mandatory Information to Submit:
* Organization name, sector, subsector, and entity type (Annex I or II).
* Address of main establishment and all legal establishments in the EU.
* Details of the EU representative (if established outside the Union).
* Primary contact details (emails, phone numbers).
* Specific **IP address ranges** used by the organization.

---

## 2. Incident Notification Timeline (Article 23)
When a **Significant Incident** occurs, entities must follow a strict statutory reporting schedule to the CSIRT or competent authority:

```mermaid
sequenceDiagram
    participant Entity as Scoped Entity
    participant Authority as CSIRT / Authority
    
    Entity->>Authority: Within 24 Hours: Early Warning (Initial Assessment & IoCs)
    Note over Authority: Responds within 24 hours with operational advice
    Entity->>Authority: Within 72 Hours: Detailed Incident Update
    Entity->>Authority: Within 1 Month: Final Report (Root Cause & Mitigation)
⏱️ The Reporting Framework:
1. 24-Hour Early Warning: Initial assessment, severity indication, and Indicators of Compromise (IoCs).
2. 72-Hour Update: More complete incident details.
3. Intermediate Status Report: Required at any time if requested, or automatically if the incident remains ongoing after 1 month.
4. 1-Month Final Report: Detailed description, finalized impact, Root Cause Analysis, and applied mitigations.
  Trust Service Providers Exception: They must bypass the multi-stage delay and submit a complete incident report within 24 hours of becoming aware of the incident.
---