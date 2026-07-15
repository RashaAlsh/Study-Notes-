# AZ-900 3.2 – Azure Governance and Compliance

## Microsoft Purview
Microsoft Purview is a **unified data governance service** that helps organizations discover, classify, manage, and govern data across:

- On-premises environments
- Multi-cloud environments
- SaaS applications

### Key Features
- Automated data discovery
- Data scanning and classification
- Data cataloging
- Data governance and compliance across the organization's data estate

> **Exam Tip:** Purview = **Data Governance**

---

## Azure Policy
Azure Policy helps enforce organizational standards and ensure Azure resources remain compliant.

### Azure Policy
An **Azure Policy** is a rule (policy definition) that defines the conditions Azure resources must meet.

**Common examples:**
- Restrict resource deployment to approved Azure regions.
- Require specific resource tags.
- Allow only approved resource types.
- Enforce security and compliance settings.

> **Exam Tip:** Azure Policy = **Govern resources by enforcing rules.**

---

## Azure Initiative
An **Azure Initiative** is a collection of related Azure Policy definitions grouped together to achieve a common governance or compliance goal.

**Example:**
A security initiative may include policies that require:
- Encryption
- Resource tagging
- Approved deployment regions

> **Exam Tip:** Initiative = **Group of policies.**

---

## Azure Blueprints
Azure Blueprints provide a repeatable way to deploy and govern new Azure environments.

A blueprint can include:
- Azure Policies
- Role Assignments (RBAC)
- Azure Resource Manager (ARM) templates
- Resource Groups

Blueprints help organizations deploy environments that already meet governance and compliance requirements.

> **Exam Tip:** Blueprint = **Deploy a complete, compliant environment.**

---

## Azure Policy vs Azure Blueprint

| Azure Policy | Azure Blueprint |
|--------------|-----------------|
| Governs resources by enforcing rules. | Deploys and governs an entire Azure environment. |
| Focuses on compliance. | Combines policies, RBAC, ARM templates, and resource groups. |
| Used after or during deployment. | Used when creating new environments. |

---

## Resource Locks
Resource Locks protect critical Azure resources from accidental deletion or modification.

### Types of Locks

### Delete Lock (`CanNotDelete`)
- Prevents a resource from being deleted.
- Resource can still be modified.

### Read-only Lock (`ReadOnly`)
- Prevents both modification and deletion.
- Resource can only be viewed.

> **Important:** Resource Locks override Azure RBAC permissions. Even users with sufficient permissions cannot modify or delete a locked resource until the lock is removed.

> **Exam Tip:** Resource Locks = **Prevent accidental deletion or modification.**

---

# AZ-900 Exam Summary

| Service | Purpose |
|---------|---------|
| **Microsoft Purview** | Discover, classify, and govern organizational data. |
| **Azure Policy** | Enforce governance and compliance rules on Azure resources. |
| **Azure Initiative** | Group multiple Azure Policies together. |
| **Azure Blueprint** | Deploy repeatable, compliant Azure environments. |
| **Resource Locks** | Prevent accidental deletion or modification of resources. |