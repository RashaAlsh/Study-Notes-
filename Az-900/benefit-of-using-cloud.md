# Azure AZ-900 Study Notes: Domain 1.2

## Domain 1.2 — Describe the Benefits of Using Cloud Services

---

## 1. High Availability and Capability in the Cloud

### Availability vs. Uptime
While closely related, these two metrics measure different aspects of system health:

* **Uptime:** Measures **system operation**. It answers: *"Is the hardware/system running?"* (e.g., A server has been powered on and running for 99.9% of the year).
* **Availability:** Measures **user accessibility**. It answers: *"Can users actually access and use the service?"* This requires the server, network, application layer, and database to all function together.

> 💡 **Key Takeaway:** High uptime does not always mean high availability. A server can be powered on (100% uptime) but have a crashed application layer rendering it completely inaccessible to users (0% availability).

### Measuring Availability ("The Nines")
The cloud improves availability through **multiple servers**, **multiple data centers**, **redundancy**, **load balancing**, and **automated failover**. Availability is measured by the percentage of time a service is accessible per year:

| Availability Percentage | Approximate Downtime per Year |
| :--- | :--- |
| **99%** | 3.65 days |
| **99.9%** | 8.76 hours |
| **99.99%** | 52 minutes |
| **99.999%** | 5 minutes |

*Note: More 9s = higher availability and lower potential downtime.*

---

### Scalability vs. Elasticity

* **Scalability:** The *capability* of a system to handle growth in users, traffic, or workload (e.g., smoothly transitioning a website from 10,000 users to 100,000 users).
* **Elasticity:** The *automation* of scaling. The ability of a system to automatically dynamically increase (**Scale Out**) or decrease (**Scale In**) resources based on real-time fluctuating demand.

#### Types of Scaling
* **Scale Up (Vertical Scaling):** Increasing the power of an *existing* resource (e.g., adding more CPU or RAM to a single Virtual Machine).
* **Scale Out (Horizontal Scaling):** Adding *more instances* of a resource (e.g., expanding from 1 VM to 10 VMs). **This is the most common approach in cloud environments.**

---

## 2. Business Continuity, Reliability, and Resiliency

### Agility
* **Definition:** The ability to quickly create, deploy, and change resources.
* **Cloud vs. Traditional:** Instead of buying physical hardware, installing equipment, and waiting weeks, cloud resources can be provisioned in minutes.
* **Example:** Instantly provisioning a *Virtual Machine Scale Set (VMSS)* to automatically manage and deploy multiple VMs.

### Fault Tolerance, High Availability, and Disaster Recovery

* **Fault Tolerance:** The ability of a system to continue working seamlessly when a **hardware, network, or power component fails** (Goal: Prevent a single component failure from stopping the service).
* **High Availability (HA):** The ability to keep a service running and accessible for a long period of time using redundancy, multiple instances, and automated failover (e.g., a banking application available 24/7).
* **Disaster Recovery (DR):** The plan to **recover and restore** service after a major catastrophic failure or disaster (e.g., natural disasters, data center outages) using backups, replication, and structured restore plans.

### Reliability vs. Resiliency
* **Reliability:** The overall ability of a system to recover from failures and continue functioning consistently. It inherently includes availability to provide consistent application access.
* **Resiliency:** The specific capability of an application to **self-heal** and return to a fully functioning state after a failure event occurs.

---

## 3. Predictability: Performance & Cost

The cloud removes guesswork by offering two distinct types of predictability:

* **Performance Predictability:** Ensuring that expected capacity, speed, and Service Level Agreements (SLAs) are consistently met.
* **Cost Predictability:** The ability to accurately estimate and track monthly expenditures and resource usage using native tools like **Azure Budgets, Alerts, and Pricing Calculators**.

---

## 4. Security, Governance, and Compliance

### Cloud Security Benefits
Cloud providers secure the environment across three main layers:
* **Customer Data:** Protected via encryption (at rest and in transit), access control, and identity management.
* **Applications:** Protected via advanced authentication, continuous monitoring, and specialized security tools.
* **Infrastructure:** Protected via physical data center security, network isolation, and **Azure DDoS Protection** (which safeguards applications from massive malicious traffic attacks through enhanced mitigation, monitoring, alerts, and telemetry).

### Shared Responsibility Model
Security responsibilities shift between the provider and customer based on the cloud service model:

| Model | What the Cloud Provider Manages | What the Customer Manages |
| :--- | :--- | :--- |
| **IaaS** *(Infrastructure)* | Physical hosts, network, datacenter | **Operating System, Applications, Data, Middleware** |
| **PaaS** *(Platform)* | Physical infrastructure, Operating System | **Applications, Data** |
| **SaaS** *(Software)* | Almost the entire environment stack | **Users, Access settings, Data settings** |

---

### Cloud Governance & Compliance
* **Governance:** Rules, policies, and controls used to improve security, reduce risk, control costs, and ensure structural efficiency.
    * *Policies:* Define organizational restrictions (e.g., "Only allow resources to be deployed in approved geographic regions").
    * *Deployment Templates:* Create resources using predefined configurations to ensure consistency, speed, and standard adherence.
* **Compliance:** Specialized tooling and verification to ensure the cloud infrastructure aligns with local regulations, industry requirements, and legal security standards.

#### Azure Cloud Adoption Framework (CAF)
A structured guidance framework helping organizations plan and implement their cloud journey across Strategy, Planning, Migration, Governance, and Management.

#### The Five Disciplines of Cloud Governance
1.  **Cost Management:** Controlling and monitoring cloud spend.
2.  **Security Baseline:** Ensuring resource protection requirements are met.
3.  **Identity Baseline:** Structuring and controlling user access.
4.  **Resource Consistency:** Standardizing how resources are deployed and grouped.
5.  **Deployment Acceleration:** Creating faster, repeatable template-driven deployment pipelines.

---

## 5. Manageability of the Cloud

**Manageability** is the cloud's capability to ease operation, monitoring, and maintenance by reducing manual tasks through four primary pillars:

1.  **Automated Scaling:** Automatically adding or removing Virtual Machines based on performance metrics to guarantee speed during peak hours while reducing idle costs during low traffic.
2.  **Template-Based Deployments:** Using preconfigured infrastructure templates to deploy resources (Servers, Networks, Storage, Security) rapidly, uniformly, and without human configuration errors.
3.  **Resource Health Monitoring:** Utilizing native cloud monitoring tools to track performance, availability, errors, and security, and immediately generate automated alerts when anomalies are detected.
4.  **Automated Self-Healing:** The system automatically recovers from failures. If a VM fails, the cloud detects the failure, removes the unhealthy VM, provisions an identical replacement from a template, and hooks it back into the service seamlessly.

---

## 🧠 AZ-900 Quick-Reference Memory Map

* **Availability** ➔ Can users actually access the service?
* **Uptime** ➔ Is the system/hardware turned on and running?
* **Scalability** ➔ Can the system handle a larger workload or growth?
* **Elasticity** ➔ Does the system scale *automatically* (Scale Out/In) based on real-time demand?
* **Agility** ➔ Speed of resource creation and deployment (minutes vs. weeks).
* **Fault Tolerance** ➔ Surviving minor component or hardware failures without shutting down.
* **Disaster Recovery** ➔ Recovering and restoring services after a total catastrophic failure.
* **Predictability** ➔ Knowing future performance metrics and cost expectations in advance.
* **Governance** ➔ Corporate rules, deployment templates, and compliance policies.
* **Manageability** ➔ Automating scaling, template deployments, health monitoring, and self-healing.
