Azure Network Watcher

Complete Beginner-Friendly Summary

What is Azure Network Watcher?

Azure Network Watcher is an Azure network monitoring and diagnostics service used to monitor, troubleshoot, and analyze Azure networking resources, especially IaaS networking.

It helps administrators investigate connectivity, routing, security rules, network traffic, and VPN problems.

Common resources include:

* Virtual Machines (VMs)
* Virtual Networks (VNets)
* Network Interfaces (NICs)
* Network Security Groups (NSGs)
* Load Balancers
* Application Gateways
* VPN Gateways

Important: Network Watcher is primarily focused on Azure network infrastructure and diagnostics. It is not a general-purpose PaaS application monitoring or web analytics service.

⸻

Why Use Network Watcher?

When an application cannot communicate with another system, several things could be wrong:

Application
    ↓
VM / NIC
    ↓
NSG
    ↓
Route Table
    ↓
VNet
    ↓
Gateway / Firewall
    ↓
Destination

Network Watcher provides tools that help determine where the problem is.

It can help answer questions such as:

* Is the traffic being blocked?
* Which NSG rule blocked it?
* Where will the packet go next?
* What security rules are applied to this VM?
* Is there network latency?
* Can one endpoint reach another?
* What packets are actually being transmitted?
* Is the VPN connection working?
* What network traffic is flowing through the environment?

⸻

Main Categories

Network Watcher capabilities can be grouped into three major areas:

Azure Network Watcher
│
├── Monitoring
│   ├── Topology
│   └── Connection Monitor
│
├── Network Diagnostics
│   ├── IP Flow Verify
│   ├── NSG Diagnostics
│   ├── Next Hop
│   ├── Effective Security Rules
│   ├── Connection Troubleshoot
│   ├── Packet Capture
│   └── VPN Troubleshoot
│
└── Traffic Monitoring & Analytics
    ├── Flow Logs
    ├── Traffic Analytics
    └── Usage + Quotas

⸻

1. Monitoring

Topology

Topology provides a visual representation of Azure networking resources and their relationships.

It can help you understand:

* Network architecture
* Resource relationships
* Network dependencies
* Connectivity between resources

Example:

                 VNet
                  │
          ┌───────┴───────┐
          │               │
       Subnet 1        Subnet 2
          │               │
         VM              VM
          │
         NIC
          │
         NSG

Use Case

An administrator inherits a large Azure environment and needs to understand how the network is structured.

Topology provides a visual view of the environment.

Memory

Topology = Visual network map

⸻

Connection Monitor

Connection Monitor continuously monitors network connectivity between endpoints.

It can help measure:

* Connectivity
* Network performance
* Latency
* Packet loss
* Network path behavior

It is useful for monitoring:

* Azure-to-Azure communication
* Azure-to-on-premises communication
* Hybrid connectivity
* Application connectivity

Example:

VM-A
 │
 │ Continuous Monitoring
 ↓
VM-B

Memory

Connection Monitor = Continuous monitoring

⸻

2. Network Diagnostic Tools

Network Watcher provides several tools for troubleshooting network problems.

⸻

1. IP Flow Verify

IP Flow Verify determines whether a specific network flow is:

* Allowed
* Denied

It can also identify the NSG rule responsible for the result.

Example:

VM
 │
 │ TCP 443
 ↓
Destination

IP Flow Verify can tell you:

Result: Allowed
Rule: Allow-HTTPS

or:

Result: Denied
Rule: Deny-Inbound

Use Case

A VM cannot communicate with another system.

Use IP Flow Verify to determine whether an NSG is blocking the traffic.

Memory

IP Flow Verify = Is the traffic allowed or denied?

⸻

2. NSG Diagnostics

NSG Diagnostics helps analyze Network Security Group rules and determine how they affect network traffic.

It can help identify:

* Whether traffic is allowed
* Whether traffic is blocked
* Which rule is responsible
* Potential rule configuration issues

Use Case

An application cannot connect to another service.

Use NSG diagnostics to investigate the NSG configuration.

Memory

NSG Diagnostics = Troubleshoot NSG rules

⸻

3. Next Hop

Next Hop determines where Azure will send traffic next.

It helps display information such as:

* Route type
* Next-hop address
* Routing decision

Example:

VM
 │
 │ Destination: 10.20.0.0/16
 ↓
Next Hop
 │
 └── Virtual Appliance
       10.0.100.4

Use Case

You created a UDR and want to verify whether traffic is actually being sent to the firewall.

Use Next Hop.

Memory

Next Hop = Where will the traffic go next?

⸻

4. Effective Security Rules

Effective Security Rules shows the security rules that are actually applied to a network interface.

These rules can come from:

* NIC-level NSGs
* Subnet-level NSGs

The result represents the effective security configuration affecting the VM’s NIC.

Example:

Subnet NSG
     +
NIC NSG
     ↓
Effective Security Rules

Use Case

You have multiple NSGs and are unsure why traffic is allowed or denied.

Use Effective Security Rules to see the combined effective rules.

Memory

Effective Security Rules = What security rules actually affect this NIC?

⸻

5. Connection Troubleshoot

Connection Troubleshoot performs an on-demand connectivity test.

It can test connectivity between supported Azure endpoints and destinations such as:

* VM → VM
* VM → IP address
* VM → FQDN
* VM → URI
* Bastion → VM

Example:

VM-A
 │
 │ One-time test
 ↓
VM-B

The tool helps identify connectivity problems and can provide information about the network path.

⸻

Connection Monitor vs Connection Troubleshoot

This is an important exam distinction.

Feature	Connection Monitor	Connection Troubleshoot
Purpose	Continuous monitoring	On-demand troubleshooting
Monitoring	Ongoing	One-time
Best for	Performance monitoring	Immediate investigation
Example	Monitor VM-to-server connectivity	Test why VM cannot connect

Memory

Connection Monitor
= Continuous
Connection Troubleshoot
= One-time

⸻

6. Packet Capture

Packet Capture captures network packets from Azure virtual machines.

It can be used to investigate:

* Application traffic
* Connectivity failures
* Protocol behavior
* Network troubleshooting
* Security incidents

Example:

VM
 │
 ├── Packet 1
 ├── Packet 2
 ├── Packet 3
 └── Packet 4
        ↓
   Packet Capture

The administrator can analyze the captured traffic without needing to manually log into the VM and run packet-capture tools locally.

Memory

Packet Capture = Capture actual network packets

⸻

7. VPN Troubleshoot

VPN Troubleshoot helps investigate problems with Azure VPN connectivity.

It can be used for scenarios involving:

* VPN Gateways
* Site-to-Site VPN
* Point-to-Site VPN

Example:

On-Premises
     │
 VPN Tunnel
     │
VPN Gateway
     │
 Azure VNet

If the VPN connection is failing, VPN Troubleshoot can help identify the problem.

Memory

VPN Troubleshoot = Diagnose VPN connectivity

⸻

3. Traffic Monitoring and Analytics

Network Watcher also provides capabilities for monitoring and analyzing network traffic.

Important concepts include:

* Flow Logs
* Traffic Analytics
* Usage and Quotas

⸻

Flow Logs

Network Security Group (NSG) flow logs record information about network traffic associated with NSGs.

Flow-log information can include details such as:

* Source IP
* Destination IP
* Source port
* Destination port
* Protocol
* Traffic decision

Example:

Source
10.0.1.4
   │
   │ TCP 443
   ↓
Destination
10.0.2.5

The flow log can provide information about the observed traffic.

⸻

Why Are Flow Logs Important?

Flow logs can support:

* Threat hunting
* Security investigations
* Network troubleshooting
* Network forensics
* Compliance requirements
* Traffic analysis

They can also be integrated into broader monitoring and security solutions.

⸻

Microsoft Cloud Security Benchmark

Network logging directly supports the Microsoft Cloud Security Benchmark concept:

LT-4: Enable Network Logging for Security Investigation

The goal is to maintain sufficient network visibility for:

* Threat detection
* Incident response
* Investigation
* Forensic analysis

⸻

Traffic Analytics

Traffic Analytics analyzes network traffic data and helps provide visibility into network behavior.

It can help identify:

* Traffic patterns
* Communication flows
* Network usage
* Potential anomalies
* Network bottlenecks

Example:

Flow Logs
    ↓
Traffic Analytics
    ↓
Dashboards + Insights

Benefits

Traffic Analytics can help organizations:

* Detect suspicious traffic
* Understand network communication
* Identify bottlenecks
* Analyze network usage
* Improve network visibility

Memory

Traffic Analytics = Analyze and visualize network traffic

⸻

Usage + Quotas

The Usage + Quotas capability helps administrators understand Azure networking resource usage and limits.

It can support:

* Capacity planning
* Network scaling
* Resource planning
* Avoiding deployment failures caused by quota limits

Examples of resources with limits include:

* VNets
* Public IP addresses
* Load Balancers
* NSGs
* Other networking resources

Memory

Usage + Quotas = How much networking capacity are we using?

⸻

Important Network Watcher Concepts

Tool	Main Purpose
Topology	Visual network map
Connection Monitor	Continuous connectivity monitoring
IP Flow Verify	Determine whether traffic is allowed or denied
NSG Diagnostics	Analyze NSG behavior
Next Hop	Determine routing destination
Effective Security Rules	View effective NSG rules
Connection Troubleshoot	Perform an on-demand connectivity test
Packet Capture	Capture VM network packets
VPN Troubleshoot	Diagnose VPN connectivity
Flow Logs	Record network traffic information
Traffic Analytics	Analyze network traffic
Usage + Quotas	Monitor resource usage and limits

⸻

Troubleshooting Decision Guide

When you encounter a networking problem, choose the appropriate tool.

“I want to see my network architecture.”

Use:

Topology

Topology
   ↓
Visual Network Map

⸻

“Is my traffic being blocked?”

Use:

IP Flow Verify

IP Flow Verify
      ↓
Allowed / Denied
      ↓
NSG Rule

⸻

“What NSG rules are actually affecting this VM?”

Use:

Effective Security Rules

Subnet NSG
     +
NIC NSG
     ↓
Effective Rules

⸻

“Where is my traffic going?”

Use:

Next Hop

Traffic
   ↓
Next Hop
   ↓
Firewall / Gateway / VNet / Internet / etc.

⸻

“Can this VM reach the destination right now?”

Use:

Connection Troubleshoot

VM
 ↓
One-Time Connectivity Test
 ↓
Destination

⸻

“I want to continuously monitor connectivity.”

Use:

Connection Monitor

Endpoint A
    ↓
Continuous Monitoring
    ↓
Endpoint B

⸻

“I need to inspect the actual packets.”

Use:

Packet Capture

VM
 ↓
Packet Capture
 ↓
Network Packets

⸻

“My VPN connection is failing.”

Use:

VPN Troubleshoot

VPN Gateway
     ↓
VPN Troubleshoot
     ↓
Connectivity Analysis

⸻

“I need network traffic logs.”

Use:

Flow Logs

Network Traffic
      ↓
Flow Logs
      ↓
Storage / Analytics / Security Tools

⸻

“I want to analyze network traffic patterns.”

Use:

Traffic Analytics

Flow Logs
    ↓
Traffic Analytics
    ↓
Traffic Patterns + Insights

⸻

Network Watcher Security Benefits

Network Watcher improves network visibility and can support security operations.

It helps organizations:

* Monitor network health
* Troubleshoot connectivity
* Validate NSG behavior
* Investigate routing decisions
* Capture packets
* Collect network traffic information
* Analyze traffic patterns
* Support incident response
* Perform network forensics
* Improve visibility across Azure infrastructure

⸻

Network Watcher and Security Operations

A typical investigation could look like this:

Security Alert
      ↓
Network Logs
      ↓
Traffic Analytics
      ↓
IP Flow Verify
      ↓
Next Hop
      ↓
Packet Capture
      ↓
Investigation

Different Network Watcher tools answer different questions.

⸻

Network Watcher vs Azure Monitor

These services are related but have different primary purposes.

Network Watcher

Focused on:

* Azure network diagnostics
* Network connectivity
* Routing
* NSGs
* Packet capture
* Network traffic analysis

Azure Monitor

Broader monitoring platform for:

* Applications
* VMs
* Azure resources
* Metrics
* Logs
* Alerts
* Performance monitoring

Easy Memory

Network Watcher
= Network-specific diagnostics
Azure Monitor
= Broad Azure monitoring

⸻

Exam and Interview Takeaways

Most Important Tools

Topology

Visualize network architecture.

Connection Monitor

Continuously monitor connectivity and network performance.

Connection Troubleshoot

Perform an on-demand connectivity test.

IP Flow Verify

Determine whether a specific network flow is allowed or denied and identify the relevant NSG rule.

Next Hop

Determine where traffic will be routed next.

Effective Security Rules

View the effective security rules affecting a network interface.

Packet Capture

Capture network packets from an Azure VM.

VPN Troubleshoot

Diagnose Azure VPN connectivity problems.

Flow Logs

Record network traffic information for analysis and investigation.

Traffic Analytics

Analyze and visualize network traffic data.

⸻

🧠 Easy Memory Formula

TOPOLOGY
= See the network
CONNECTION MONITOR
= Monitor continuously
CONNECTION TROUBLESHOOT
= Test once
IP FLOW VERIFY
= Allowed or denied?
NEXT HOP
= Where does traffic go?
EFFECTIVE SECURITY RULES
= Which NSG rules apply?
PACKET CAPTURE
= Capture packets
VPN TROUBLESHOOT
= Fix VPN problems
FLOW LOGS
= Record traffic
TRAFFIC ANALYTICS
= Analyze traffic

⸻

Quick Exam Cheat Sheet

Question:
"Show me the network visually."
→ Topology
Question:
"Monitor connectivity continuously."
→ Connection Monitor
Question:
"Test connectivity right now."
→ Connection Troubleshoot
Question:
"Why is this traffic blocked?"
→ IP Flow Verify
Question:
"What route will traffic take?"
→ Next Hop
Question:
"What security rules apply to this NIC?"
→ Effective Security Rules
Question:
"I need to inspect packets."
→ Packet Capture
Question:
"My VPN is not working."
→ VPN Troubleshoot
Question:
"I need network traffic logs."
→ Flow Logs
Question:
"I want traffic analysis and dashboards."
→ Traffic Analytics

⸻

Final Takeaway

Azure Network Watcher is a network-focused monitoring and diagnostics service that provides visibility, troubleshooting, routing analysis, packet capture, VPN diagnostics, and network traffic analysis for Azure networking environments.

The most important concepts to remember are:

Network Watcher
│
├── Monitoring
│   ├── Topology
│   └── Connection Monitor
│
├── Diagnostics
│   ├── IP Flow Verify
│   ├── NSG Diagnostics
│   ├── Next Hop
│   ├── Effective Security Rules
│   ├── Connection Troubleshoot
│   ├── Packet Capture
│   └── VPN Troubleshoot
│
└── Traffic Analysis
    ├── Flow Logs
    ├── Traffic Analytics
    └── Usage + Quotas

Golden Rule

Network Watcher = See + Test + Troubleshoot + Analyze Azure Networks