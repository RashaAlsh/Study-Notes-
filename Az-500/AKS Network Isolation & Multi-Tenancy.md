AKS Network Isolation & Multi-Tenancy
Quick Summary
AKS network isolation controls which workloads, users, and teams can communicate with or access each other inside an Azure Kubernetes Service (AKS) cluster.
Multi-tenancy means multiple teams or applications share the same AKS cluster while being logically separated.
AKS Cluster
│
├── HR Namespace
├── Finance Namespace
└── Dev Namespace
Shared cluster ≠ shared access. Isolation controls who can communicate, access resources, and consume capacity.
 
⸻
 
1. Multi-Tenancy
Imagine an AKS cluster as an apartment building:
Building = AKS Cluster
Apartment = Namespace
Family = Team / Application
Example:
Team	Namespace
HR	hr
Finance	finance
Development	dev
Each team shares the cluster but can have separate permissions, resources, and network rules.
 
⸻
 
2. Four Main Areas of AKS Isolation
2.1 Scheduling and Resource Isolation
Controls where workloads run and how many resources they can consume.
Resource Quotas
Limit resources available to a namespace.
HR       → 2 CPUs
Finance  → 4 CPUs
This prevents one team from consuming the entire cluster.
Taints and Tolerations
Reserve nodes for specific workloads.
GPU Node
   ↓
AI Workloads Only
Node Selectors
Place pods on nodes with specific labels.
Example:
node OS = Linux
       ↓
Pod scheduled on Linux node
Affinity / Anti-Affinity
Control whether pods should run together or separately.
* Affinity → prefer/require placement together.
* Anti-affinity → prefer/require separation.
Scheduling isolation = control where workloads run and how much they consume.
 
⸻
 
3. Network Isolation
Controls:
Who can communicate with whom?
Network Policies
A Kubernetes NetworkPolicy acts like a firewall for pod traffic.
Frontend Pod
     │
     ▼
Backend Pod
     ✅ Allowed


Random Pod
     │
     ▼
Database Pod
     ❌ Blocked
Example:
HR Namespace
    │
    └── HR Pods → HR Database ✅

Finance Namespace
    │
    └── Finance Pods → Finance Database ✅

HR Pods → Finance Database ❌
Network policies are one of the most important controls for workload-to-workload isolation.
Network Policy = control pod-to-pod communication.
 
⸻
 
4. Authentication and Authorization
Controls:
Who can access AKS, and what can they do?
Kubernetes RBAC
Role-Based Access Control assigns permissions to users, groups, and service accounts.
Identity	Example Access
Admin	Full cluster administration
Developer	Deploy/manage applications
Auditor	Read-only access
 
⸻
 
Microsoft Entra ID
AKS can integrate with Microsoft Entra ID for centralized identity management.
Benefits:
* Centralized authentication
* SSO
* Group-based access
* Integration with organizational identities
Example:
Entra ID
   │
   ├── AKS-Admins
   ├── AKS-Developers
   └── AKS-Readers
 
⸻
 
Workload Identity
Workload Identity allows pods to authenticate to Azure resources without storing passwords or long-lived credentials inside the application.
Example:
AKS Pod
   │
   │ Microsoft Entra authentication
   ↓
Azure Key Vault
This is preferable to embedding Azure credentials in application code.
 
⸻
 
Azure Key Vault
Key Vault can securely store:
* Secrets
* Certificates
* Keys
Instead of placing sensitive values directly in application code or configuration.
 
⸻
 
5. Container Security
Container security protects the workloads themselves.
Pod Security Standards
Define security requirements for pods.
Example:
Privileged container
        ↓
       ❌
A policy might prevent containers from running with excessive privileges or as root.
 
⸻
 
Azure Policy for AKS
Azure Policy can enforce organizational security requirements.
Examples:
* Require approved container images
* Prevent insecure configurations
* Enforce organizational standards
Pod Deployment
      ↓
Azure Policy
      ↓
Compliant? ── No → ❌ Block
      │
     Yes
      ↓
     ✅ Deploy
 
⸻
 
Microsoft Defender for Containers
Provides security capabilities such as:
* Vulnerability assessment
* Runtime threat detection
* Security recommendations
* Container security monitoring
Defender for Containers = visibility and protection for Kubernetes/container workloads.
 
⸻
 
AppArmor and Seccomp
These Linux security mechanisms restrict what containers can do on the host.
They can limit access to dangerous system capabilities and reduce the impact of a compromised container.
 
⸻
 
6. Logical Isolation
Logical isolation means multiple teams share one AKS cluster but are separated using Kubernetes and Azure security controls.
Common controls:
Shared AKS Cluster
│
├── Namespaces
├── RBAC
├── Network Policies
├── Resource Quotas
└── Security Policies
Example
AKS Cluster
│
├── HR
│   ├── Pods
│   └── Services
│
├── Finance
│   ├── Pods
│   └── Services
│
└── Development
    ├── Pods
    └── Services
Benefits
* Lower cost
* Better resource utilization
* Higher workload density
* Easier scaling
* Fewer clusters to manage
Logical isolation = shared infrastructure with controlled boundaries.
 
⸻
 
7. Physical Isolation
Physical isolation means workloads use separate AKS clusters.
HR
 ↓
AKS Cluster 1

Finance
 ↓
AKS Cluster 2

Development
 ↓
AKS Cluster 3
Benefits
* Stronger separation
* Smaller blast radius
* Useful for highly sensitive or hostile workloads
Drawbacks
* Higher cost
* More administration
* More infrastructure to manage
* Potentially lower resource utilization
 
⸻
 
Logical vs Physical Isolation
Feature	Logical Isolation	Physical Isolation
Infrastructure	Shared cluster	Separate clusters
Cost	Lower	Higher
Management	Simpler	More complex
Resource utilization	Usually better	Can be lower
Security boundary	Logical	Stronger infrastructure boundary
Typical use	Most multi-team environments	Strong isolation requirements
When Physical Isolation Makes Sense
Consider separate clusters when:
* Workloads require stronger isolation
* Teams/customers have low trust
* Regulatory requirements demand separation
* Workloads are highly sensitive
* The environment is effectively hostile multi-tenancy
 
⸻
 
8. Recommended Isolation Model
For many organizations, use logical isolation first:
                    AKS Cluster
                         │
        ┌────────────────┼────────────────┐
        ↓                ↓                ↓
     HR NS            Finance NS        Dev NS
        │                │                │
      RBAC            RBAC             RBAC
        │                │                │
 Network Policy    Network Policy   Network Policy
        │                │                │
 Resource Quota    Resource Quota   Resource Quota
Move to separate clusters when the required security boundary cannot be achieved safely within one cluster.
 
⸻
 
9. Isolation Controls Cheat Sheet
Requirement	Main Control
Separate teams/workloads	Namespaces
Limit resource consumption	Resource Quotas
Control pod communication	Network Policies
Control user permissions	Kubernetes RBAC
Centralize user identity	Microsoft Entra ID
Secure Azure access from pods	Workload Identity
Store secrets securely	Azure Key Vault
Enforce security policies	Azure Policy
Secure pod execution	Pod Security Standards / Linux security controls
Detect container threats	Microsoft Defender for Containers
Strong infrastructure separation	Separate AKS clusters
 
⸻
 
Exam & Interview Questions
What is network isolation in AKS?
Controlling communication and access between workloads, users, and teams within an AKS environment.
What is multi-tenancy?
Multiple teams, applications, or customers sharing infrastructure while being logically or physically isolated.
How do you isolate teams inside one AKS cluster?
Use:
* Namespaces
* RBAC
* Network Policies
* Resource Quotas
* Security policies
What controls pod-to-pod communication?
Network Policies
What limits how many resources a namespace can consume?
Resource Quotas
What controls who can perform Kubernetes operations?
RBAC
How can AKS users authenticate using organizational identities?
Microsoft Entra ID integration
How can a pod access Azure resources without storing credentials?
Workload Identity
When would you choose separate AKS clusters?
When stronger isolation, regulatory separation, or a more hostile trust boundary is required.
 
⸻
 
🧠 Memory
AKS ISOLATION

WHERE workloads run
        ↓
Scheduling / Quotas

WHO can communicate
        ↓
Network Policies

WHO can access AKS
        ↓
Entra ID + RBAC

WHAT workloads can do
        ↓
Pod Security + Azure Policy

HOW strongly separated
        ↓
Logical vs Physical Isolation
Golden Rule
Logical isolation = shared AKS cluster + Namespaces + RBAC + Network Policies + Resource Quotas.

Physical isolation = separate AKS clusters when a stronger security boundary is required.
One-Line Exam Summary
AKS multi-tenancy uses namespaces, RBAC, network policies, resource controls, and security policies to isolate shared workloads; logical isolation is generally preferred for efficiency, while separate clusters provide stronger isolation when required.
