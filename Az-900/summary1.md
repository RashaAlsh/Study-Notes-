# Microsoft Azure Fundamentals (AZ-900) English Summary

This summary covers all the topics you've studied so far: Cloud Computing, Shared Responsibility Model, Cloud Models, Consumption-Based Model, Cloud Benefits, and Cloud Service Types (IaaS, PaaS, SaaS).

---

# 1. What is Cloud Computing?

Cloud computing is the delivery of computing services over the Internet.

These services include:

- Servers
- Storage
- Databases
- Networking
- Artificial Intelligence (AI)
- Machine Learning (ML)
- Analytics

Instead of owning physical infrastructure, organizations rent resources from cloud providers like Microsoft Azure and pay only for what they use.

## Benefits

- ✅ Lower costs
- ✅ Faster deployment
- ✅ Scalability
- ✅ Global access
- ✅ High availability

---

# 2. Shared Responsibility Model

Responsibilities are shared between the cloud provider and the customer.

## Cloud Provider Responsibilities

- Physical datacenter
- Physical servers
- Physical network
- Power and cooling

## Customer Responsibilities

- Data
- Accounts and identities
- Access permissions
- Connected devices

## Key Rule

- You own your data.
- The cloud provider owns the physical infrastructure.

---

# 3. Cloud Models

## A. Public Cloud

Resources are owned and managed by a cloud provider.

### Examples

- Microsoft Azure
- Amazon Web Services (AWS)
- Google Cloud

### Benefits

- ✅ Low cost
- ✅ High scalability
- ✅ Pay-as-you-go

---

## B. Private Cloud

Dedicated to one organization only.

### Benefits

- ✅ Maximum control
- ✅ Greater security

### Disadvantages

- ❌ Higher cost

---

## C. Hybrid Cloud

Combination of Public Cloud and Private Cloud.

### Benefits

- ✅ Maximum flexibility
- ✅ Better control of sensitive data

---

## D. Multicloud

Using multiple cloud providers.

### Example

- Azure + AWS

---

# 4. Consumption-Based Model

Cloud computing uses a **Pay-As-You-Go** pricing model.

You pay only for the resources you consume.

## Benefits

- ✅ No upfront costs
- ✅ Scale when needed
- ✅ Reduce resources when demand falls
- ✅ Better cost management

## CapEx vs OpEx

| CapEx | OpEx |
|-------|------|
| Upfront investment | Pay over time |
| Traditional datacenter | Cloud computing |

---

# 5. High Availability

High Availability means keeping services running even when failures occur.

Azure provides **Service-Level Agreements (SLAs)** to guarantee uptime.

## Benefits

- ✅ Less downtime
- ✅ Business continuity
- ✅ Better customer experience

---

# 6. Scalability

Scalability means adjusting resources based on demand.

## Vertical Scaling

Increase server power.

- More CPU
- More RAM
- Scale Up / Scale Down

## Horizontal Scaling

Increase the number of servers.

- Scale Out
- Scale In

---

# 7. Reliability

Reliability is the ability to recover from failures and continue operating.

Azure uses multiple regions worldwide to improve resiliency.

## Benefits

- ✅ Disaster recovery
- ✅ Business continuity
- ✅ Reduced outages

---

# 8. Predictability

Predictability means knowing:

- Expected performance
- Expected cost

## Performance Predictability

Supported by:

- Autoscaling
- Load balancing
- High availability

## Cost Predictability

Supported by:

- Monitoring
- Cost analysis
- Azure Pricing Calculator

---

# 9. Security

Security protects:

- Data
- Applications
- Users
- Systems

## Cloud Security Benefits

- ✅ Identity Management
- ✅ Encryption
- ✅ Threat Detection
- ✅ DDoS Protection
- ✅ Automated Patching

---

# 10. Governance

Governance ensures resources follow company policies and compliance requirements.

## Benefits

- ✅ Compliance
- ✅ Auditing
- ✅ Standardization
- ✅ Cost Control

---

# 11. Manageability

There are two types:

## A. Management of the Cloud

Cloud helps manage resources through:

- Autoscaling
- Templates
- Monitoring
- Alerts
- Automatic replacement

## B. Management in the Cloud

Ways to manage Azure:

- Azure Portal
- Azure CLI
- PowerShell
- APIs

---

# 12. Sustainability

Sustainability means reducing waste and improving efficiency.

## Best Practices

- ✅ Right-size resources
- ✅ Scale down when demand drops
- ✅ Turn off unused resources
- ✅ Monitor usage
- ✅ Automate operations

---

# 13. Cloud Service Models

## IaaS (Infrastructure as a Service)

You rent infrastructure.

### You Manage

- Operating System (OS)
- Applications
- Data

### Azure Manages

- Hardware
- Network
- Datacenter

### Example

- Azure Virtual Machines

### Key Idea

**Highest Control + Highest Responsibility**

---

## PaaS (Platform as a Service)

You focus on applications.

### Azure Manages

- Operating System
- Runtime
- Middleware
- Infrastructure

### You Manage

- Application
- Data

### Examples

- Azure App Service
- Azure SQL Database

### Key Idea

**Focus on Development**

---

## SaaS (Software as a Service)

You use a ready-made application.

The cloud provider manages almost everything.

### You Manage

- Users
- Data
- Permissions

### Examples

- Microsoft 365
- Microsoft Teams
- Outlook

### Key Idea

**Just Use the Software**

---

# Final AZ-900 Memory Sheet

| Concept | Remember |
|----------|----------|
| Cloud Computing | IT services over the Internet |
| Public Cloud | Lowest cost |
| Private Cloud | Highest control |
| Hybrid Cloud | Public + Private |
| Multicloud | Multiple providers |
| Shared Responsibility | Shared between customer and provider |
| High Availability | Keep services running |
| Reliability | Recover from failures |
| Scalability | Adjust resources to demand |
| Vertical Scaling | Bigger server |
| Horizontal Scaling | More servers |
| Security | Protect resources |
| Governance | Control & Compliance |
| Manageability | Monitor and automate |
| Sustainability | Right-size, automate, optimize |
| IaaS | Rent infrastructure |
| PaaS | Focus on code |
| SaaS | Use the application |
| CapEx | Traditional datacenter |
| OpEx | Cloud Pay-As-You-Go |

---

# Exam Shortcut

- **IaaS = Control Infrastructure**
- **PaaS = Build Applications**
- **SaaS = Use Applications**

---

**This is the core knowledge needed for the Microsoft Azure Fundamentals (AZ-900) exam.**