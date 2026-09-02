Microsoft Cloud Security Benchmark Summary

Overview

The Microsoft Cloud Security Benchmark (MCSB) provides security recommendations for protecting cloud environments.

This summary focuses on three major security areas:

1. Data Protection
2. Logging and Threat Detection
3. Network Security

Together, these controls support:

* Confidentiality
* Integrity
* Availability
* Threat detection
* Incident response
* Regulatory compliance
* Defense in depth

⸻

1. Data Protection

DP-3: Encrypt Sensitive Data in Transit

Objective

Protect sensitive data while it is being transmitted across networks to prevent:

* Interception
* Eavesdropping
* Tampering
* Unauthorized access

Key Requirements

Organizations should:

* Encrypt sensitive data in transit, especially across public and external networks.
* Use TLS 1.2 or later for web applications and services.
* Use secure remote-management protocols:
    * SSH for Linux
    * RDP over TLS for Windows
* Replace insecure file-transfer protocols such as FTP with:
    * SFTP
    * FTPS

Azure

Recommended controls include:

* Enable Secure Transfer for Azure Storage.
* Use TLS 1.2+ for supported services.
* Azure encrypts supported datacenter-to-datacenter traffic automatically.
* Use Azure Private Link where appropriate.
* Apply secure-transfer policies.

AWS

Recommended controls include:

* Enable encryption for:
    * Amazon S3
    * Amazon RDS
    * Amazon CloudFront
    * Elastic Load Balancing
* Use AWS Transfer Family for SFTP/FTPS.
* Use encryption for supported traffic between AWS services and VPC resources.

Google Cloud

Recommended controls include:

* Use HTTPS/TLS 1.2+.
* Use built-in encryption for supported Google Cloud infrastructure traffic.
* Use SSH/RDP for secure remote administration.
* Use secure file-transfer services.

Business Benefit

Encryption in transit:

* Protects confidential information.
* Reduces the risk of network-based attacks.
* Protects data integrity.
* Supports compliance requirements such as:
    * PCI DSS
    * NIST
    * CIS Controls

⸻

2. Logging and Threat Detection

LT-4: Enable Network Logging for Security Investigation

Objective

Capture network activity logs to support:

* Threat detection
* Security monitoring
* Incident response
* Forensic investigations
* Threat hunting
* Compliance audits

Important Log Sources

Organizations should collect logs from:

* Firewalls
* Network Security Groups (NSGs)
* DNS services
* Web Application Firewalls (WAFs)
* Network flow-monitoring tools
* Virtual machines
* Network devices

⸻

Azure

Important logging sources include:

* NSG Flow Logs
* Azure Firewall Logs
* WAF Logs
* DNS Analytics

Store and analyze logs using:

* Azure Monitor
* Log Analytics
* Traffic Analytics

These services provide visibility into network activity and support security investigations.

⸻

AWS

Important logging sources include:

* VPC Flow Logs
* AWS WAF Logs
* Route 53 Resolver Query Logs

Logs can be exported to:

* Amazon CloudWatch
* Amazon S3

Organizations can also integrate AWS logging with security monitoring platforms such as Microsoft Sentinel.

⸻

Google Cloud

Important capabilities include:

* VPC Flow Logs
* Audit Logs
* Packet Mirroring

Logs can be exported using:

* Cloud Logging
* Pub/Sub

This supports real-time monitoring and security investigations.

Business Benefit

Network logging provides:

* Visibility into suspicious activity
* Threat-hunting capabilities
* Better incident response
* Forensic evidence
* Compliance support

⸻

3. Network Security

Network Security focuses on:

* Isolating workloads
* Controlling network traffic
* Protecting cloud services
* Reducing public exposure
* Preventing external attacks
* Limiting lateral movement

⸻

NS-1: Establish Network Segmentation Boundaries

Objective

Reduce the spread of attacks by isolating critical and high-risk workloads.

Best Practices

Organizations should:

* Separate sensitive workloads into dedicated networks.
* Implement a deny-by-default network model.
* Restrict traffic based on:
    * Port
    * Protocol
    * Source IP
    * Destination IP

Cloud Implementations

Azure	AWS	Google Cloud
VNet	VPC	VPC
Subnets	Security Groups	Subnets
NSGs	NACLs	Firewall Rules
ASGs	—	—

Benefit

Network segmentation:

* Limits lateral movement.
* Reduces exposure.
* Contains compromised systems.
* Protects critical workloads.

⸻

NS-2: Secure Cloud Native Services with Network Controls

Objective

Minimize public exposure and use private connectivity whenever possible.

Best Practices

* Use private endpoints whenever possible.
* Disable public network access when it is not required.
* Avoid assigning public IP addresses directly to servers.
* Prefer private connectivity between cloud services.

Cloud Implementations

Cloud	Private Connectivity
Azure	Azure Private Link
AWS	AWS PrivateLink
Google Cloud	Google Private Access

Benefit

Private connectivity:

* Reduces the attack surface.
* Keeps traffic away from the public internet.
* Reduces unauthorized exposure.

⸻

NS-3: Deploy Firewalls at the Network Edge

Objective

Filter and inspect traffic entering or leaving the environment.

Best Practices

Block unnecessary or dangerous traffic such as:

* Malicious IP addresses
* RDP from the internet
* SSH from the internet
* SMB when unnecessary
* Kerberos when unnecessary
* Other unnecessary protocols

Use centralized firewall management where possible.

Cloud Implementations

Cloud	Firewall Solution
Azure	Azure Firewall
AWS	AWS Network Firewall
Google Cloud	Google Cloud Armor + Firewall Policies

Benefit

Network firewalls:

* Prevent unauthorized access.
* Filter malicious traffic.
* Improve traffic control.
* Protect network boundaries.

⸻

NS-5: Deploy DDoS Protection

Objective

Protect applications and networks against Distributed Denial-of-Service (DDoS) attacks.

A DDoS attack attempts to overwhelm a service with large amounts of traffic, affecting availability.

Cloud Implementations

Azure

* DDoS Protection Basic
* DDoS Protection Standard

AWS

* AWS Shield Standard
* AWS Shield Advanced

Google Cloud

* Google Cloud Armor
* Advanced DDoS protection capabilities

Benefit

DDoS protection helps:

* Maintain service availability.
* Absorb malicious traffic.
* Reduce the impact of denial-of-service attacks.

⸻

NS-6: Deploy a Web Application Firewall (WAF)

Objective

Protect web applications and APIs against Layer 7 attacks.

Recommended Protections

A WAF can help protect against:

* SQL Injection
* Cross-Site Scripting (XSS)
* OWASP Top 10 vulnerabilities
* Malicious bots
* Other HTTP/HTTPS-based attacks

Cloud Implementations

Cloud	WAF
Azure	Azure WAF
AWS	AWS WAF
Google Cloud	Google Cloud Armor WAF

Azure WAF

Azure WAF can be deployed with services such as:

* Application Gateway
* Azure Front Door

Benefit

A WAF protects internet-facing applications by inspecting web traffic and blocking malicious requests.

⸻

NS-8: Detect and Disable Insecure Services and Protocols

Objective

Identify and eliminate outdated, weak, or insecure protocols.

Examples of Insecure Protocols

* TLS 1.0
* TLS 1.1
* SSL
* SMBv1
* SSHv1
* NTLMv1
* Unsigned LDAP

Recommended Actions

Disable insecure protocols whenever possible.

If they cannot immediately be removed, apply compensating controls such as:

* Firewall restrictions
* Network segmentation
* WAF protection
* Access restrictions

Benefit

Removing insecure protocols:

* Reduces attack surface.
* Reduces exposure to known vulnerabilities.
* Limits legacy attack techniques.
* Improves overall security posture.

⸻

NS-9: Connect On-Premises and Cloud Networks Privately

Objective

Provide secure communication between on-premises environments and cloud networks without relying unnecessarily on the public internet.

Cloud Implementations

Azure	AWS	Google Cloud
VPN Gateway	AWS VPN	Cloud VPN
ExpressRoute	Direct Connect	Cloud Interconnect
VNet Peering	Transit Gateway	Network Connectivity Center

Best Practices

* Prefer private connectivity over internet-based communication.
* Use dedicated links for mission-critical workloads.
* Use network peering where appropriate.
* Keep traffic on cloud-provider backbones when possible.

Benefit

Private connectivity can improve:

* Security
* Performance
* Reliability
* Network control

It also reduces exposure to internet-based threats.

⸻

Security Controls at a Glance

Control	Main Purpose	Key Technologies
DP-3	Encrypt data in transit	TLS, SSH, SFTP, FTPS
LT-4	Network logging	Flow Logs, Firewall Logs, WAF Logs, DNS Logs
NS-1	Network segmentation	VNet, VPC, NSG, Security Groups, NACLs
NS-2	Private connectivity	Private Link, PrivateLink, Private Access
NS-3	Network-edge protection	Azure Firewall, AWS Network Firewall, Cloud Armor
NS-5	DDoS protection	Azure DDoS Protection, AWS Shield, Cloud Armor
NS-6	Web application protection	WAF
NS-8	Remove insecure protocols	Disable TLS 1.0/1.1, SMBv1, SSHv1, etc.
NS-9	Hybrid connectivity	VPN, ExpressRoute, Direct Connect, Interconnect

⸻

Executive Summary

The Microsoft Cloud Security Benchmark emphasizes three major security pillars:

1. Data Protection

Encrypt sensitive data in transit using:

* TLS 1.2+
* SSH
* SFTP
* FTPS

The goal is to protect confidentiality and integrity while data travels across networks.

2. Logging and Threat Detection

Collect and analyze network activity from:

* Firewalls
* NSGs
* Flow logs
* DNS
* WAFs
* Network devices

The goal is to provide visibility for:

* Threat detection
* Incident response
* Threat hunting
* Forensics
* Compliance

3. Network Security

Use multiple layers of network protection:

* Network segmentation
* Private endpoints
* Firewalls
* DDoS protection
* WAFs
* Secure protocols
* Private hybrid connectivity

The goal is to reduce the attack surface and prevent unauthorized access.

⸻

Defense-in-Depth Model

A strong cloud security architecture uses multiple layers:

                    Internet
                       |
                       v
                 DDoS Protection
                       |
                       v
                     WAF
                       |
                       v
                  Edge Firewall
                       |
                       v
              Network Segmentation
                       |
              +--------+--------+
              |                 |
              v                 v
          Web Tier          Application Tier
                                |
                                v
                          Private Network
                                |
                                v
                           Data Services

Each layer provides a different security control.

If one layer is bypassed, additional controls can still protect the environment.

⸻

Key Exam Concepts

DP-3

Question: How should sensitive data be protected while traveling across networks?

Answer: Use encryption such as TLS 1.2+, SSH, SFTP, or FTPS.

⸻

LT-4

Question: Why collect network logs?

Answer: To support threat detection, security investigations, incident response, and forensics.

⸻

NS-1

Question: Why use network segmentation?

Answer: To isolate workloads and limit lateral movement.

⸻

NS-2

Question: How can public exposure be reduced?

Answer: Use private endpoints/private connectivity and disable unnecessary public network access.

⸻

NS-3

Question: What protects the network boundary?

Answer: Network firewalls.

⸻

NS-5

Question: What protects against DDoS attacks?

Answer: A cloud DDoS protection service.

⸻

NS-6

Question: What protects web applications from Layer 7 attacks?

Answer: A Web Application Firewall (WAF).

⸻

NS-8

Question: What should you do with insecure protocols?

Answer: Disable and remove them whenever possible.

⸻

NS-9

Question: How should on-premises and cloud networks communicate securely?

Answer: Use private connectivity such as VPN, ExpressRoute, Direct Connect, or Cloud Interconnect.

⸻

Easy Memory Formula

PROTECT
   ↓
Encrypt Data
   ↓
LOG
   ↓
Monitor Network Activity
   ↓
SEGMENT
   ↓
Isolate Workloads
   ↓
FILTER
   ↓
Firewalls + WAF
   ↓
DEFEND
   ↓
DDoS Protection
   ↓
CONNECT PRIVATELY
   ↓
Secure Hybrid Connectivity

Final Takeaway

Cloud Security
     |
     +-- Data Protection
     |      └── Encrypt Data in Transit
     |
     +-- Logging & Detection
     |      └── Collect Network Logs
     |
     +-- Network Security
            ├── Segment Networks
            ├── Use Private Connectivity
            ├── Deploy Firewalls
            ├── Protect Against DDoS
            ├── Deploy WAF
            └── Disable Insecure Protocols

Golden Rule:

Encrypt → Log → Segment → Filter → Protect → Connect Privately

This defense-in-depth approach strengthens confidentiality, integrity, availability, visibility, and overall cloud security across Azure, AWS, and Google Cloud.