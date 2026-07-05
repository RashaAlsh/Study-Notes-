# AZ-900 Domain 2.2 — Describe Azure Compute and Network Services

> **Exam Objective:** Understand Azure compute services, application hosting, and networking services.

---

# Azure Compute Services

Azure provides several compute options depending on your workload.

| Service | Best Used For |
|----------|---------------|
| **Virtual Machines (VMs)** | Full control over the operating system and applications (IaaS) |
| **Azure Container Instances (ACI)** | Running a single container or a few containers without managing servers |
| **Azure Kubernetes Service (AKS)** | Managing large numbers of containers using Kubernetes |
| **Azure Functions** | Event-driven, serverless code execution |
| **Azure App Service** | Hosting web apps, APIs, and mobile backends (PaaS) |

---

# Compare Azure Compute Types

## Azure Virtual Machines (VMs)

### Definition

Azure Virtual Machines provide **Infrastructure as a Service (IaaS)**.

You manage:

- Operating system
- Applications
- Updates
- Security

### Best For

- Legacy applications
- Custom software
- Full operating system control

---

## Azure Container Instances (ACI)

### Definition

Azure Container Instances (ACI) allow you to run **Docker containers** on demand without managing servers or virtual machines.

Azure manages the infrastructure.

### Best For

- Small workloads
- Short-lived jobs
- Batch processing
- Development and testing

### Characteristics

- Serverless containers
- Fast startup
- No orchestration required

---

## Azure Kubernetes Service (AKS)

### Definition

Azure Kubernetes Service (AKS) is Microsoft's managed Kubernetes platform for deploying and managing containerized applications.

Azure manages:

- Kubernetes control plane
- Health monitoring
- Updates
- Maintenance

You manage:

- Worker (agent) nodes
- Applications

### Best For

- Large containerized applications
- Microservices
- Automatic scaling
- High availability

> **💡 Exam Tip:** Use **AKS** when container orchestration is required.

---

## Azure Functions

### Definition

Azure Functions is a **serverless** compute service that runs code in response to events.

Examples:

- HTTP requests
- Timer triggers
- Blob uploads
- Queue messages

### Characteristics

- No server management
- Pay only when code runs
- Automatic scaling

### Best For

- Automation
- Background processing
- APIs
- Event-driven applications

---

# Containers vs Virtual Machines

| Containers | Virtual Machines |
|------------|------------------|
| Lightweight | Larger |
| Share the host operating system | Each VM has its own operating system |
| Start in seconds | Longer startup time |
| Efficient resource usage | More resource intensive |
| Best for microservices | Best for full operating systems |

> **💡 Exam Tip:** Containers usually run **inside virtual machines**.

---

# Azure Virtual Machine Options

## Virtual Machine Scale Sets (VMSS)

### Definition

VM Scale Sets allow you to create and manage a group of **identical**, **load-balanced** virtual machines.

### Features

- Automatic scaling
- Load balancing
- High availability
- Supports thousands of VM instances

### Best For

Applications with changing demand.

> **Remember:** **Scale Sets = Scalability**

---

## Availability Sets

### Definition

Availability Sets improve VM availability by distributing VMs across different hardware.

They reduce downtime during:

- Planned maintenance
- Hardware failures

### Two Concepts

### Fault Domains

Separate VMs across different:

- Power sources
- Network switches
- Physical servers

Protect against hardware failures.

### Update Domains

Ensure only one group of VMs is rebooted during planned maintenance.

Protect against planned outages.

> **Remember:** **Availability Sets = Resilience**

---

## Azure Virtual Desktop (AVD)

### Definition

Azure Virtual Desktop is a desktop and application virtualization service running in Azure.

It enables organizations to deliver:

- Windows 10
- Windows 11
- Remote applications

to users from Azure.

### Benefits

- Remote work
- Centralized management
- Secure access
- Multi-session Windows

---

# Virtual Machine Resources

A Virtual Machine typically requires:

- Virtual Disk
- Virtual Network (VNet)
- Network Interface (NIC)
- Network Security Group (NSG)
- Public IP Address (optional)

---

# Application Hosting Options

## Azure App Service

### Definition

Azure App Service is an **HTTP-based Platform as a Service (PaaS)** used for hosting:

- Web applications
- REST APIs
- Mobile backends

Azure manages:

- Infrastructure
- Operating system
- Scaling
- Patching

---

### Web Apps

Supports:

- ASP.NET
- ASP.NET Core
- Java
- Node.js
- Python
- PHP
- Ruby

---

### API Apps

Used for hosting REST APIs.

Features:

- Swagger/OpenAPI support
- Authentication
- Azure integration

---

### WebJobs

Run background programs or scripts alongside a Web App.

Supports:

- .NET
- Java
- Python
- Node.js
- PowerShell
- Bash

Can be:

- Continuous
- Scheduled
- Triggered

---

### Mobile Apps

Provide back-end services for mobile applications.

Supports:

- Authentication
- Push notifications
- Offline synchronization

---

## Containers

Application hosting using:

- Azure Container Instances (ACI)
- Azure Kubernetes Service (AKS)

Ideal for microservices and cloud-native applications.

---

## Virtual Machines

Applications can also be hosted directly on Azure Virtual Machines when full operating system control is required.

---

# Azure Networking

## Azure Virtual Network (VNet)

### Definition

A Virtual Network (VNet) is the logical representation of a private network in Azure.

A VNet contains one or more subnets.

### Benefits

- Network isolation
- Communication between Azure resources
- Hybrid cloud connectivity
- Secure resource deployment

> **💡 Exam Tip:** Different VNets **cannot communicate by default**.

---

## Azure Subnets

### Definition

A subnet divides a VNet into smaller networks.

### Benefits

- Organize resources
- Apply security separately
- Simplify network management

Example:

- Web subnet
- Application subnet
- Database subnet

> **💡 Exam Tip:** Resources in different subnets **within the same VNet can communicate by default**.

---

## VNet Peering

### Definition

VNet Peering connects two or more Azure Virtual Networks.

The connected VNets communicate as though they were one network.

### Benefits

- High-speed communication
- Low latency
- No VPN required

> **💡 Exam Tip:** Different VNets cannot communicate unless connected through **Peering** or **VPN**.

---

## Azure VPN Gateway

### Definition

Azure VPN Gateway securely connects:

- Azure VNets
- On-premises networks

using encrypted VPN tunnels over the **public Internet**.

### Best For

Hybrid cloud connectivity.

---

## Azure ExpressRoute

### Definition

ExpressRoute provides a **private dedicated connection** between your on-premises network and Azure.

### Benefits

- Does **not** use the Internet
- Higher reliability
- Lower latency
- Improved security

> **💡 Exam Tip**

| VPN Gateway | ExpressRoute |
|-------------|--------------|
| Uses the Internet | Private connection |
| Lower cost | Higher cost |
| Encrypted VPN tunnel | Dedicated connectivity |

---

## Azure DNS

### Definition

Azure DNS hosts DNS domains using Microsoft Azure infrastructure.

Supports:

- Public DNS
- Private DNS

Provides reliable name resolution.

---

# Public vs Private Endpoints

## Service Endpoints

### Definition

Service Endpoints secure Azure PaaS services by allowing access only from specific VNets.

### Characteristics

- Uses the service's **public IP**
- Traffic stays on Microsoft's backbone network
- Resource still has a public endpoint

---

## Private Endpoints

### Definition

Private Endpoints assign a **private IP address** from your VNet to an Azure PaaS resource.

### Benefits

- No public exposure
- Accessible from on-premises through private connectivity
- Increased security

> **💡 Exam Tip**

- **Service Endpoint** → Public endpoint remains
- **Private Endpoint** → Private IP inside your VNet

---

# Network Security Concepts

## Defense in Depth

Defense in Depth is a **security strategy**, not an Azure service.

It protects systems using multiple layers of security.

Example layers:

- Physical security
- Identity
- Perimeter
- Network
- Compute
- Application
- Data

---

## Network Security Group (NSG)

### Definition

A Network Security Group (NSG) filters inbound and outbound network traffic.

Rules can specify:

- Source
- Destination
- Port
- Protocol
- Allow or Deny

NSGs can be associated with:

- A subnet
- A network interface (NIC)

---

## Azure Firewall

### Definition

Azure Firewall is a fully managed, stateful firewall service for Azure Virtual Networks.

### Features

- Built-in high availability
- Automatic scaling
- Centralized network security
- Application and network filtering

---

## Azure DDoS Protection

### Definition

Azure DDoS Protection defends Azure resources against Distributed Denial of Service (DDoS) attacks.

### Tiers

**Basic**

- Included automatically
- Default protection

**Standard**

Adds:

- Enhanced mitigation
- Attack analytics
- Telemetry
- Alerts
- Cost protection

---

# AZ-900 Exam Memory Sheet

| Service | Remember This |
|----------|---------------|
| **Virtual Machine** | Full OS control (IaaS) |
| **Container Instance (ACI)** | Single serverless containers |
| **AKS** | Managed Kubernetes |
| **Azure Functions** | Serverless event-driven code |
| **App Service** | PaaS for Web Apps and APIs |
| **VM Scale Sets** | Automatic scaling |
| **Availability Sets** | Fault tolerance for VMs |
| **Azure Virtual Desktop** | Cloud-hosted Windows desktops |
| **VNet** | Private Azure network |
| **Subnet** | Division within a VNet |
| **VNet Peering** | Connects VNets |
| **VPN Gateway** | Hybrid connectivity over the Internet |
| **ExpressRoute** | Private hybrid connectivity |
| **Azure DNS** | DNS hosting |
| **Service Endpoint** | Public endpoint restricted to VNets |
| **Private Endpoint** | Private IP access to Azure services |
| **NSG** | Filters network traffic |
| **Azure Firewall** | Managed firewall |
| **Azure DDoS Protection** | Protection against DDoS attacks |

---

# Common AZ-900 Exam Questions

| Question | Answer |
|----------|--------|
| Which compute service is serverless? | **Azure Functions** |
| Which service manages Kubernetes? | **Azure Kubernetes Service (AKS)** |
| Which VM feature automatically scales VM instances? | **Virtual Machine Scale Sets** |
| Which VM feature improves resilience? | **Availability Sets** |
| Which Azure service hosts web apps and APIs? | **Azure App Service** |
| Can different VNets communicate by default? | **No** |
| Which service connects Azure to on-premises over the Internet? | **VPN Gateway** |
| Which service provides a private dedicated connection? | **ExpressRoute** |
| Which endpoint removes public exposure? | **Private Endpoint** |
| Which Azure service filters network traffic? | **Network Security Group (NSG)** |

---

# Quick Exam Recap

- ✅ **VM** → Full operating system control
- ✅ **ACI** → Serverless containers
- ✅ **AKS** → Kubernetes orchestration
- ✅ **Azure Functions** → Event-driven serverless compute
- ✅ **App Service** → Host web apps and APIs
- ✅ **VM Scale Sets** → Scalability
- ✅ **Availability Sets** → Resilience
- ✅ **VNet** → Private Azure network
- ✅ **Subnet** → Segment within a VNet
- ✅ **VNet Peering** → Connect Azure VNets
- ✅ **VPN Gateway** → Hybrid cloud over the Internet
- ✅ **ExpressRoute** → Private hybrid connection
- ✅ **Service Endpoint** → Public endpoint restricted to VNets
- ✅ **Private Endpoint** → Private IP access
- ✅ **NSG** → Network traffic filtering
- ✅ **Azure Firewall** → Managed firewall
- ✅ **Azure DDoS Protection** → DDoS mitigation