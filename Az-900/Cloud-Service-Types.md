# Azure AZ-900 Study Notes: Domain 1.3

## Domain 1.3 — Cloud Service Types and the Shared Responsibility Model

---

## 1. Introduction to Cloud Service Types
Cloud computing distributes management responsibilities across three primary service models depending on the level of control, flexibility, and management overhead a customer wants:

1. **Infrastructure as a Service (IaaS)**
2. **Platform as a Service (PaaS)**
3. **Software as a Service (SaaS)**

---

## 2. The Shared Responsibility Model
The **Shared Responsibility Model** is a core cloud concept that defines exactly which operational and security layers are managed by the cloud provider versus what remains the responsibility of the customer.



### Responsibility Breakdown Matrix

| Operational Component | On-Premises | IaaS | PaaS | SaaS |
| :--- | :---: | :---: | :---: | :---: |
| **Physical Infrastructure & Datacenter** | 👤 Customer | ☁️ Provider | ☁️ Provider | ☁️ Provider |
| **Physical Network & Storage** | 👤 Customer | ☁️ Provider | ☁️ Provider | ☁️ Provider |
| **Virtualization Layer / Hypervisor** | 👤 Customer | ☁️ Provider | ☁️ Provider | ☁️ Provider |
| **Operating System (OS)** | 👤 Customer | **👤 Customer** | ☁️ Provider | ☁️ Provider |
| **Middleware & Runtime** | 👤 Customer | **👤 Customer** | ☁️ Provider | ☁️ Provider |
| **Applications** | 👤 Customer | **👤 Customer** | **👤 Customer** | ☁️ Provider |
| **Data & Governance** | 👤 Customer | **👤 Customer** | **👤 Customer** | **👤 Customer** |
| **Identity & Directory Infrastructure** | 👤 Customer | **👤 Customer** | **👤 Customer** | **👤 Customer** |
| **Endpoints & Devices** | 👤 Customer | **👤 Customer** | **👤 Customer** | **👤 Customer** |

> **Critical Exam Note:** Regardless of the cloud deployment model you choose (IaaS, PaaS, or SaaS), the **Customer** is *always* 100% responsible for protecting their own **Data, Endpoints, Account Access, and Identities**.

---

## 3. Infrastructure as a Service (IaaS)

### Definition
IaaS provides raw virtualized computing infrastructure on-demand over the internet. The provider treats physical servers, storage disks, and networking as a utility, leaving the customer to configure everything from the operating system upward.

* **Azure Examples:** Azure Virtual Machines (VMs), Azure Virtual Networks (VNets), Azure Disk Storage.

### Primary Use Cases
* **Testing and Development:** Fast, scriptable environment provisioning. Teams can spin up VMs with varied OS configurations to test code, and instantly tear them down when done without capital hardware expenditure.
* **Lift-and-Shift Migration:** Transitioning existing application workloads out of physical enterprise datacenters directly into cloud VMs with minimal recoding.
* **Extending Datacenters:** Creating secure site-to-site VPN tunnels or dedicated connections to bridge on-premises networks into an Azure Virtual Network.
* **Disaster Recovery (DR):** Maintaining automated warm-standby infrastructure configurations in the cloud that can boot instantly in the event of an on-premises disaster.

---

## 4. Platform as a Service (PaaS)

### Definition
PaaS provides a managed hosting environment tailored for application deployment. The cloud provider entirely automates hardware management, OS patching, system updates, and scaling pipelines so developers can solely focus on writing application code.

* **Azure Examples:** Azure App Services, Azure SQL Database, API Management.

### Primary Use Cases
* **Development Frameworks:** Provides integrated frameworks and deployment pipelines out-of-the-box, shortening development cycles and building scalability, multi-tenancy, and high availability natively into apps.
* **Analytics & Business Intelligence (BI):** Deploying pre-packaged data analytics tools to ingest large data sets, identify patterns, forecast trends, and drive organizational decision-making without setting up underlying data clusters.

---

## 5. Software as a Service (SaaS)

### Definition
SaaS delivers fully functional, ready-to-use software applications directly to end-users via the web browser. The provider fully owns, hosts, scales, and manages the entire software solution stack.

* **Examples:** Microsoft 365 (Teams, Outlook, Word), Dynamics 365, online expense trackers.

### Primary Use Cases & Benefits
* **Utility Applications:** Excellent for systems critical to standard operations but outside of a company's core distinct business domain (e.g., corporate email, payroll platforms, HR portals).
* **Rapid Deployment:** Instantly grants application capabilities to users without configuring underlying infrastructure or managing updates.

---

## 6. Hybrid Cloud Architecture

A **Hybrid Cloud** bridges the gap by linking traditional on-premises infrastructure with public cloud platforms. 

* **Common Implementations:** Utilizing IaaS resources within Azure via secure Hybrid connections (like Site-to-Site VPNs or ExpressRoute) to seamlessly transfer workloads.
* **Key Advantage:** Offers enterprise flexibility by allowing developers to migrate non-sensitive testing workloads up to the public cloud while strictly isolating critical, highly compliance-regulated workloads in an on-premises private datacenter.

---

##  AZ-900 Domain 1.3 Core Summary

* **On-Premises:** You buy, configure, maintain, and secure everything.
* **IaaS:** You rent the physical computer; **you manage the OS, software, and applications.**
* **PaaS:** You rent the execution space; **you write the code, while Azure handles the OS and servers.**
* **SaaS:** You rent the finished application; **you simply manage your data and user access configurations.**
