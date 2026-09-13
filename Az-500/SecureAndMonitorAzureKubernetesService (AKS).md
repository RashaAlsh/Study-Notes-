Secure and Monitor Azure Kubernetes Service (AKS)
Quick Summary
Azure Kubernetes Service (AKS) is Microsoft’s managed Kubernetes platform for running containerized applications.
Security for AKS focuses on:
AKS Security
│
├── Security Posture
├── Vulnerability Assessment
├── Runtime Protection
├── Supply Chain Security
├── Policy Enforcement
└── Monitoring & Response
Microsoft Defender for Containers provides security capabilities across these areas.
AKS = Run containers Defender for Containers = Protect and monitor them
 
⸻
 
1. Microsoft Defender for Containers
Microsoft Defender for Containers protects Kubernetes clusters, container images, nodes, and workloads.
It helps:
* Find misconfigurations
* Detect vulnerabilities
* Monitor runtime activity
* Protect the software supply chain
* Enforce security policies
* Generate security alerts
* Support investigation and response
Container Environment
        ↓
Defender for Containers
        ↓
Detect → Assess → Protect → Alert → Respond
 
⸻
 
2. Five Core Security Areas
2.1 Security Posture Management
Checks whether Kubernetes environments follow security best practices.
Examples:
❌ Publicly exposed dashboard
❌ Excessive permissions
❌ Containers running as root
❌ Insecure cluster configuration
Defender provides:
* Security recommendations
* Risk information
* Remediation guidance
Posture Management = Security health check
 
⸻
 
3. Vulnerability Assessment
A vulnerability is a security weakness in software.
Defender can identify vulnerabilities in supported container images and Kubernetes environments.
Example:
Container Image
      ↓
OpenSSL vulnerability
      ↓
Defender Detection
      ↓
Severity + Risk + Remediation
Potential image sources include:
* Azure Container Registry
* Amazon ECR
* Google Artifact Registry
* Google Container Registry
* Docker Hub
* JFrog Artifactory
Vulnerability Assessment = Find known software weaknesses before they become incidents.
 
⸻
 
4. Runtime Threat Protection
Runtime means the workload is actively running.
Defender monitors runtime activity for suspicious behavior.
Examples:
* Suspicious processes or commands
* Privilege escalation
* Unauthorized activities
* Sensitive host mounts
* Exposed Kubernetes dashboards
* High-privilege Kubernetes roles
Example:
Container Running
       ↓
Defender Monitoring
       ↓
Suspicious Activity
       ↓
Security Alert
High-Privilege Example
cluster-admin
     ↓
Very broad Kubernetes permissions
Sensitive Mount Example
/docker.sock
/etc/shadow
Improper access to sensitive resources can increase the risk of privilege escalation or container escape.
Runtime Protection = Watch workloads while they are running.
 
⸻
 
5. Software Supply Chain Protection
Security should cover the complete application path:
Developer
   ↓
Source Code
   ↓
Build
   ↓
Container Image
   ↓
Deployment
   ↓
Production
The goal is to identify security problems before they reach production.
Gated Deployment
A deployment can be evaluated against security requirements.
Container Image
      ↓
Security Check
      ↓
Compliant?
   ↙       ↘
 No         Yes
 ↓           ↓
❌ Block    ✅ Deploy
This is an example of shifting security left.
Supply Chain Security = Secure software before it reaches production.
 
⸻
 
6. Deployment and Monitoring
Defender helps identify whether required security capabilities are deployed and providing coverage.
It can help identify:
* Unmonitored clusters
* Missing security components
* Security configuration issues
* Monitoring coverage gaps
Purpose: Make sure security protection is actually enabled and working.
 
⸻
 
7. Agentless vs Sensor-Based Security
This is an important AKS security concept.
Agentless
Agentless capabilities do not require security software to run inside the cluster nodes.
They can use Azure/Kubernetes APIs and other supported mechanisms for capabilities such as:
* Resource discovery
* Inventory
* Security assessment
* Vulnerability assessment
* Recommendations
Benefits
* Easier deployment
* Less maintenance
* Minimal workload impact
 
⸻
 
Sensor-Based
Sensor-based protection deploys Defender components into the environment to provide deeper runtime visibility.
Used for capabilities such as:
* Runtime threat detection
* Behavioral monitoring
* Binary drift detection
Comparison
Feature	Agentless	Sensor-Based
Software in cluster	No	Yes
Deployment	Easier	More involved
Runtime visibility	Limited	Deeper
Maintenance	Lower	Higher
Main strength	Discovery/assessment	Runtime protection
Agentless = visibility without in-cluster sensors Sensor-based = deeper runtime visibility
 
⸻
 
8. Agentless Discovery and Inventory
Defender can discover and maintain information about supported Kubernetes resources.
Examples:
* Clusters
* Nodes
* Pods
* Services
* Deployments
* Container images
* Repositories
* Configurations
Why it matters
You cannot effectively secure resources you do not know exist.
A comprehensive inventory gives security teams visibility into their Kubernetes environment.
 
⸻
 
9. Security Investigation and Risk Hunting
Security teams can investigate Kubernetes security issues using Defender capabilities.
Examples:
Find:
→ Containers running as root

Find:
→ Vulnerable images

Find:
→ Suspicious workloads

Find:
→ High-risk configurations
Security Explorer and related Defender capabilities can help security teams investigate and prioritize risks.
 
⸻
 
10. Control Plane Hardening
The control plane is the management layer or “brain” of Kubernetes.
Important components include:
* Kubernetes API Server
* Scheduler
* Controller Manager
        Control Plane
             │
      ┌──────┼──────┐
      ↓      ↓      ↓
   API     Scheduler  Controller
  Server    Manager    Manager
Defender can assess supported control-plane security configurations and provide recommendations when weaknesses are identified.
Control Plane = Kubernetes management/decision layer
 
⸻
 
11. Data Plane Hardening
The data plane is where application workloads actually run.
Data Plane
│
├── Nodes
├── Pods
└── Containers
Security controls can enforce requirements on these workloads.
Azure Policy for Kubernetes
Azure Policy can enforce organizational requirements.
Example:
Deploy Privileged Container
          ↓
    Policy Evaluation
          ↓
         ❌
A policy can require or prohibit specific Kubernetes configurations.
Data Plane = Where application workloads run
 
⸻
 
12. Binary Drift Detection
What is Drift?
Suppose an approved image contains:
Apache
Node.js
After deployment, unauthorized software is manually added.
Approved Image
      ≠
Running Container
This unexpected difference is binary drift.
Defender can detect unauthorized changes in supported scenarios.
Why it matters
An attacker who gains access to a container may modify its contents after deployment.
Binary Drift = Unexpected changes to a running workload compared with its approved image.
 
⸻
 
13. Security Alerts
Defender can generate alerts for suspicious or risky activity.
Examples:
* Exposed Kubernetes dashboards
* Suspicious processes
* Sensitive mounts
* Privilege-related activity
* Vulnerable workloads
* Other detected threats
Security teams can investigate alerts through:
* Microsoft Defender for Cloud
* Microsoft Defender XDR
 
⸻
 
14. Microsoft Defender XDR Integration
Defender XDR can help security teams:
* Investigate incidents
* Correlate alerts
* Understand attack timelines
* Perform response actions
Example:
Threat Detected
      ↓
Security Alert
      ↓
Investigation
      ↓
Containment
      ↓
Remediation
In supported scenarios, response actions can help restrict or contain affected workloads.
 
⸻
 
15. MITRE ATT&CK Mapping
MITRE ATT&CK is a framework/catalog describing common attacker techniques and behaviors.
Defender can map detected activity to relevant ATT&CK techniques.
This helps analysts understand:
* What technique may be involved
* How an attacker may be operating
* What additional investigation may be useful
Security Alert
      ↓
MITRE ATT&CK Technique
      ↓
Understand Attack Behavior
      ↓
Investigate / Respond
 
⸻
 
16. AKS Security Architecture
                    AKS
                     │
       ┌─────────────┼─────────────┐
       ↓             ↓             ↓
  Control Plane   Data Plane   Container Images
       │             │             │
       ↓             ↓             ↓
   Hardening      Policies      Vulnerability
                  Network        Assessment
                  Security
       │             │             │
       └─────────────┼─────────────┘
                     ↓
          Defender for Containers
                     ↓
          Detection + Monitoring
                     ↓
          Defender XDR / Response
 
⸻
 
17. Security Control Cheat Sheet
Requirement	Main Capability
Find misconfigurations	Security Posture Management
Find known vulnerabilities	Vulnerability Assessment
Monitor running workloads	Runtime Threat Protection
Secure image-to-production path	Supply Chain Protection
Block policy-violating deployments	Gated Deployment / Policy
Discover Kubernetes resources	Agentless Discovery
Deep runtime visibility	Sensor-Based Protection
Detect unauthorized runtime changes	Binary Drift Detection
Enforce Kubernetes configuration	Azure Policy
Control pod communication	Network Policies
Control Kubernetes permissions	Kubernetes RBAC
Centralize identity	Microsoft Entra ID
Investigate incidents	Defender XDR
Classify attacker techniques	MITRE ATT&CK
 
⸻
 
Exam & Interview Questions
What is AKS?
A managed Kubernetes service from Microsoft Azure used to run and manage containerized applications.
What is Microsoft Defender for Containers?
A security solution that helps protect Kubernetes and container environments through vulnerability assessment, posture management, runtime protection, monitoring, and security recommendations.
What are the five main Defender for Containers security areas?
1. Security Posture Management
2. Vulnerability Assessment
3. Runtime Threat Protection
4. Software Supply Chain Protection
5. Deployment & Monitoring
What is agentless security?
Security capabilities that do not require security agents or sensors to be installed inside the Kubernetes cluster.
What is sensor-based security?
Security protection that deploys Defender components into the environment to provide deeper runtime visibility and detection.
What is binary drift detection?
Detection of unexpected changes to a running container compared with its original or approved image.
What is gated deployment?
A security control that evaluates workloads before deployment and can block deployments that violate defined security requirements.
What is Azure Policy for Kubernetes?
A policy enforcement mechanism that helps apply organizational security and compliance requirements to Kubernetes resources.
What is the control plane?
The Kubernetes management layer responsible for making cluster-level decisions and coordinating workloads.
What is the data plane?
The infrastructure where Kubernetes workloads actually run, including nodes, pods, and containers.
What is Defender XDR used for?
Security investigation, alert correlation, incident analysis, and response across supported Microsoft security signals.
 
⸻
 
One-Minute Revision
AKS
= Managed Kubernetes

Defender for Containers
= Security for Kubernetes + Containers

Posture
= Find misconfigurations

Vulnerability Assessment
= Find known software vulnerabilities

Runtime Protection
= Detect threats while workloads run

Supply Chain
= Secure code → image → deployment → production

Agentless
= No in-cluster security sensor

Sensor-Based
= Deeper runtime monitoring

Azure Policy
= Enforce Kubernetes rules

Binary Drift
= Detect unexpected changes after deployment

Gated Deployment
= Stop non-compliant workloads before production

Defender XDR
= Investigate and respond

MITRE ATT&CK
= Classify attacker techniques
Final Takeaway
Secure AKS using layered controls: assess the cluster’s security posture, scan images and workloads for vulnerabilities, enforce policies, monitor runtime behavior, protect the software supply chain, and use Defender tools for investigation and response.
Golden Rule
ASSESS
  ↓
Find weaknesses

SCAN
  ↓
Find vulnerabilities

ENFORCE
  ↓
Apply security policies

MONITOR
  ↓
Detect runtime threats

RESPOND
  ↓
Investigate and contain
AKS runs the workloads; Defender for Containers helps secure them throughout their lifecycle.
