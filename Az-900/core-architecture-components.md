# AZ-900 Domain 2.1 — Describe the Core Architectural Components of Azure

> **Exam Focus:** Understand Azure's global infrastructure, physical infrastructure, and resource hierarchy.

---

# Azure Global Infrastructure

## Azure Geography

### Definition

An **Azure Geography** is a discrete market, typically containing **two or more Azure regions**, that preserves **data residency, compliance, and data sovereignty** boundaries.

### Purpose

- Meet legal and regulatory requirements
- Keep customer data within a specific geographic boundary
- Organize Azure regions based on geopolitical boundaries

### Examples

- Europe
- United States
- Asia Pacific

> ** Exam Tip:** An **Azure Geography** is the **largest geographic boundary** in Azure.

---

## Azure Regions

### Definition

An **Azure Region** is a geographical area containing **one or more datacentres** deployed within a **latency-defined perimeter** and connected through a dedicated **low-latency regional network**.

Each region provides Azure services such as:

- Virtual Machines (VMs)
- Storage
- Networking
- Databases

### Benefits

- Low latency
- High availability
- Disaster recovery support
- Regional compliance

### Example Regions

- West Europe
- North Europe
- East US

> ** Exam Tip:** Most Azure resources require you to choose a **region** when deploying them.

---

## Azure Region Pairs

### Definition

Each Azure region is paired with another region within the **same geography** to support **disaster recovery** and **business continuity**.

### Benefits

- Disaster recovery
- Replication between paired regions (for supported services)
- Platform updates are staggered (only one region in a pair is updated at a time)
- One region is prioritized during large-scale recovery

### Key Facts

- Usually at least **300 miles (≈480 km)** apart
- Chosen and managed by Microsoft
- Belong to the same Azure geography

### Example

```text
West Europe ↔ North Europe
```

> ** Exam Tip**
>
> - **Availability Zones** protect against **datacentre failures**
> - **Region Pairs** protect against **regional failures**

---

## Azure Sovereign Regions

### Definition

**Azure Sovereign Regions** are special Azure cloud environments designed to meet strict **government**, **legal**, or **compliance** requirements.

They are **physically and logically isolated** from the global Azure cloud.

### Azure Government

Designed for:

- U.S. Federal Government
- State and Local Governments
- Department of Defense (DoD)
- Government contractors

**Operated by screened U.S. personnel.**

---

### Azure China

- Operated by **21Vianet**
- Runs under Chinese regulations
- Microsoft provides the technology, but the cloud is operated separately

---

# Azure Physical Infrastructure

## Azure Datacentres

### Definition

Azure **Datacentres** are physical facilities containing thousands of servers and networking equipment that deliver Azure cloud services.

### They include

- Compute servers
- Storage systems
- Networking equipment
- Cooling systems
- Backup power
- Multiple Internet Service Providers (ISPs)

### Characteristics

- Highly secure
- Highly reliable
- Highly available
- Energy efficient
- Multi-tenant

---

## Availability Zones

### Definition

**Availability Zones** are unique physical locations within an Azure region.

Each Availability Zone consists of one or more datacentres with **independent**:

- Power
- Cooling
- Networking

### Purpose

Protect applications against **datacentre failures**.

### Benefits

- High availability
- Fault tolerance
- Redundancy

> ** Exam Tip:** Not every Azure region supports Availability Zones.

---

# Azure Core Architecture

Azure resources are organized in the following hierarchy:

```text
Management Group
        ↓
Subscription
        ↓
Resource Group
        ↓
Resource
```

---

## Management Groups

### Definition

**Management Groups** provide a level of management **above subscriptions**.

### Purpose

Manage multiple subscriptions consistently.

### Features

- Organize subscriptions
- Apply Azure Policy
- Apply Azure RBAC
- Apply governance across subscriptions

### Root Management Group

Every Azure tenant has one **Root Management Group**.

- All subscriptions belong under it by default.
- Provides the highest level for policies and governance.

---

## Subscriptions

### Definition

A **Subscription** is a logical container used to provision and manage Azure resources.

A subscription acts as a:

- Billing boundary
- Management boundary
- Security boundary
- Scale boundary

### Why Use Multiple Subscriptions?

- Separate billing
- Different payment methods
- Separate production and development environments
- Department or project isolation
- Different security or compliance requirements
- Avoid subscription limits and quotas

---

## Resource Groups

### Definition

A **Resource Group (RG)** is a logical container that holds related Azure resources.

Resources in the same Resource Group usually share the same lifecycle.

### Example

A web application Resource Group might contain:

- Virtual Machine
- Storage Account
- Azure SQL Database
- Virtual Network

### Important Exam Facts

- A resource belongs to **only one Resource Group**.
- A Resource Group can contain resources from **different Azure regions**.

---

## Resources

### Definition

A **Resource** is an individual Azure service managed by Azure.

### Examples

- Virtual Machine (VM)
- Virtual Network (VNet)
- Storage Account
- Azure SQL Database
- App Service

---

# Azure Hierarchy Summary

## Global Infrastructure

```text
Azure Geography
        ↓
Azure Region
        ↓
Availability Zone
        ↓
Datacentre
```

## Resource Management

```text
Management Group
        ↓
Subscription
        ↓
Resource Group
        ↓
Resource
```

---

# AZ-900 Exam Memory Sheet

| Component | Remember This |
|-----------|---------------|
| **Geography** | Data residency and compliance boundary |
| **Region** | One or more datacentres connected by a low-latency network |
| **Region Pair** | Disaster recovery between two regions in the same geography |
| **Sovereign Region** | Isolated Azure cloud for government and compliance |
| **Datacentre** | Physical building with servers and networking |
| **Availability Zone** | Separate physical location protecting against datacentre failure |
| **Management Group** | Organizes and governs multiple subscriptions |
| **Subscription** | Billing, management, security, and scale boundary |
| **Resource Group** | Logical container for related resources |
| **Resource** | Individual Azure service (VM, Storage Account, VNet, etc.) |

---

# Common AZ-900 Exam Questions

| Question | Answer |
|----------|--------|
| What protects against a **datacentre failure**? | **Availability Zones** |
| What protects against a **regional failure**? | **Region Pairs** |
| What is the **billing boundary** in Azure? | **Subscription** |
| What is the highest level of Azure resource management? | **Management Group** |
| Can a Resource Group contain resources from multiple regions? | **Yes** |
| Can a resource belong to multiple Resource Groups? | **No — only one** |
| What is the largest geographic boundary in Azure? | **Azure Geography** |

---

# Quick Exam Recap

 **Geography** → Compliance & data residency

 **Region** → One or more datacentres

 **Availability Zone** → Protects against **datacentre failure**

 **Region Pair** → Protects against **regional failure**

 **Datacentre** → Physical facility

 **Management Group** → Governs multiple subscriptions

 **Subscription** → Billing, management, security, and scale boundary

 **Resource Group** → Logical container for related resources

 **Resource** → Individual Azure service

---

> ** AZ-900 Domain 2.1 Exam Tip:** If you can clearly distinguish **Geography vs Region vs Availability Zone vs Region Pair**, and **Management Group vs Subscription vs Resource Group vs Resource**, you're well prepared for nearly all Domain 2.1 exam questions.

