Azure Virtual Network Peering vs VPN Gateway
Beginner-Friendly Summary for New Azure Engineers
Azure Virtual Networks (VNets) are isolated from each other by default.
Resources in one VNet cannot communicate with resources in another VNet unless you explicitly establish connectivity.
Two important ways to connect networks are:
1. Virtual Network Peering
2. VPN Gateway
 
⸻
 
1. Virtual Network Peering
What is VNet Peering?
Virtual Network Peering directly connects two Azure VNets.
After peering is configured, resources in the connected VNets can communicate using private IP addresses as though they were part of the same larger network.
Example:
VNet-A
(Web Servers)
     │
     │ VNet Peering
     │
VNet-B
(Database Servers)
The web servers can communicate directly with the database servers using private IP addresses.
 
⸻
 
Key Benefits
VNet Peering provides:
* High bandwidth
* Low latency
* Private IP connectivity
* Traffic over the Microsoft backbone
* No need to route traffic over the public internet
* Support for Azure-to-Azure connectivity across regions
 
⸻
 
Typical Use Cases
VNet Peering is commonly used for:
* Application-to-application communication
* Database connectivity
* Database replication
* Disaster recovery
* Cross-region architectures
* Large Azure environments
* Communication between application tiers
 
⸻
 
Regional vs Global VNet Peering
VNet Peering can connect VNets:
Within the Same Azure Region
VNet-A
   │
Peering
   │
VNet-B
Across Different Azure Regions
This is known as Global VNet Peering.
East US                         West Europe
VNet-A  ─── Global Peering ───  VNet-B
This allows Azure resources in different regions to communicate privately over Microsoft’s network.
 
⸻
 
2. VPN Gateway
What is a VPN Gateway?
Azure VPN Gateway is a managed virtual network gateway that provides secure connectivity using encrypted VPN tunnels.
It can be used for:
* Azure ↔ On-premises
* Azure ↔ Azure
* Remote connectivity scenarios
Example:
On-Premises Network
        │
        │ Encrypted VPN Tunnel
        │
   VPN Gateway
        │
        │
    Azure VNet
VPN connectivity commonly uses:
* IPsec
* IKE
The traffic is encrypted as it travels through the VPN tunnel.
 
⸻
 
Common VPN Gateway Use Cases
VPN Gateway is commonly used for:
* Connecting corporate datacenters to Azure
* Hybrid cloud architectures
* Connecting branch offices to Azure
* Site-to-Site VPN
* Point-to-Site VPN
* Secure network connectivity over the internet
 
⸻
 
VNet Peering vs VPN Gateway
Feature	VNet Peering	VPN Gateway
Primary purpose	Connect Azure VNets	Secure VPN connectivity
Typical use	Azure-to-Azure	Azure-to-on-premises
Transport	Microsoft backbone	Encrypted VPN tunnel
Public Internet	Not used for the peering path	Used for internet-based VPN
Encryption	Peering traffic is not inherently an IPsec VPN tunnel	IPsec/IKE encryption
Latency	Very low	Higher than peering
Performance	High	Depends on gateway SKU
Cost	Peering/data-transfer charges	Gateway charges + data transfer
Management	Relatively simple	Requires VPN gateway configuration
Best for	High-performance Azure connectivity	Hybrid connectivity
Easy Memory
VNet Peering
= Fast Azure-to-Azure private connectivity

VPN Gateway
= Encrypted VPN connectivity
 
⸻
 
Gateway Transit
What is Gateway Transit?
Gateway Transit allows a peered VNet to use a gateway located in another VNet.
This is especially useful in hub-and-spoke architectures.
Instead of deploying a VPN Gateway in every spoke VNet, the organization can place a gateway in the hub and allow eligible peered VNets to use it.
 
⸻
 
Hub-and-Spoke with Gateway Transit
Example:
                 On-Premises
                      │
                      │
                 VPN Gateway
                      │
                      │
                  Hub VNet
                  /      \
                 /        \
                /          \
           Spoke A       Spoke B
The hub contains the gateway.
The spoke VNets can use the hub gateway when the appropriate peering and gateway-transit settings are configured.
 
⸻
 
Without Gateway Transit
Each VNet might require its own gateway:
On-Prem
  │
  ├── Gateway → VNet A
  │
  ├── Gateway → VNet B
  │
  └── Gateway → VNet C
This can increase:
* Cost
* Management complexity
* Operational overhead
 
⸻
 
With Gateway Transit
A shared gateway can be placed in the hub:
                 On-Premises
                      │
                 VPN Gateway
                      │
                   Hub VNet
                  /        \
                 /          \
            Spoke A       Spoke B
Benefits
* Lower infrastructure cost
* Centralized connectivity
* Easier management
* Suitable for hub-and-spoke architectures
* Avoids deploying a gateway in every spoke
 
⸻
 
Important Gateway Transit Terms
When configuring gateway transit, remember the concepts:
Hub VNet
The VNet containing the VPN or ExpressRoute gateway.
Spoke VNet
A peered VNet that can use the hub gateway.
Gateway Transit
Allows the spoke to use the gateway in the hub.
Use Remote Gateways
Configured on the spoke side to use the remote hub gateway.
Allow Gateway Transit
Configured on the hub side to allow the peered VNet to use its gateway.
 
⸻
 
VNet Peering Is Non-Transitive
One of the most important concepts to remember is:
VNet peering is non-transitive by default.
Example:
VNet A
   ↕
VNet B
   ↕
VNet C
Even though:
A ↔ B
B ↔ C
this does not automatically mean:
A ↔ C
VNet A cannot automatically use VNet B as a router to reach VNet C.
Additional routing architecture is required.
Possible solutions include:
* Azure VPN Gateway
* Azure Route Server
* Network Virtual Appliances
* Appropriate routing configurations
 
⸻
 
VNet Peering Across Subscriptions and Tenants
VNet peering can be configured between VNets that belong to different Azure subscriptions.
It can also support cross-tenant scenarios when the appropriate permissions and configuration are available.
The important point for exams is:
VNet peering is not limited to VNets in the same subscription.
 
⸻
 
VPN Gateway Characteristics
A VNet can have a VPN gateway that provides VPN connectivity for that VNet.
VPN Gateway supports different connectivity scenarios, including:
* Site-to-Site VPN
* Point-to-Site VPN
* VNet-to-VNet VPN
VPN Gateway can also participate in routing architectures using BGP.
 
⸻
 
BGP and VPN Gateway
What is BGP?
Border Gateway Protocol (BGP) is a dynamic routing protocol used to exchange network routes between networks.
In Azure hybrid networking, BGP can exchange routes between:
Azure
  ↕
VPN Gateway
  ↕
On-Premises Router
This can reduce the need to manually configure every route.
 
⸻
 
Peering vs VPN Gateway: Architecture
VNet Peering
VNet A
   │
   │ Private Azure Connectivity
   │
VNet B
Best when you need direct Azure-to-Azure connectivity.
 
⸻
 
VPN Gateway
On-Premises
     │
     │ Encrypted VPN Tunnel
     │
VPN Gateway
     │
Azure VNet
Best when you need secure hybrid connectivity.
 
⸻
 
When Should You Use VNet Peering?
Choose VNet Peering when:
* Connecting Azure VNets
* High performance is required
* Low latency is important
* Large amounts of data need to move between VNets
* Private Azure backbone connectivity is preferred
* You need cross-region Azure connectivity
Example
Application VNet
       │
   Peering
       │
Database VNet
 
⸻
 
When Should You Use VPN Gateway?
Choose VPN Gateway when:
* Connecting Azure to an on-premises network
* Encrypted VPN communication is required
* Hybrid cloud connectivity is needed
* Site-to-Site VPN is required
* Point-to-Site VPN is required
* VPN-based Azure-to-Azure connectivity is appropriate
Example
Corporate Datacenter
        │
    VPN Tunnel
        │
  VPN Gateway
        │
    Azure VNet
 
⸻
 
Real-World Enterprise Architecture
A common enterprise architecture combines several technologies:
                       On-Premises
                            │
                            │ VPN / ExpressRoute
                            │
                       Hub VNet
                     ┌──────┴──────┐
                     │             │
                  Firewall       Gateway
                     │
                     │
              ┌──────┴──────┐
              │             │
           Spoke A        Spoke B
              │             │
         Application     Database
VNet Peering provides connectivity between the hub and spokes.
Gateway Transit can allow spokes to use a gateway located in the hub.
UDRs can then be used when traffic must follow a specific path, such as through a firewall.
 
⸻
 
Relationship Between Peering, VPN Gateway, and UDR
These technologies solve different networking problems.
Technology	Main Purpose
VNet Peering	Connect VNets directly
VPN Gateway	Create VPN connectivity
Gateway Transit	Share a gateway with peered VNets
UDR	Control traffic routing
NSG	Allow or deny network traffic
Azure Firewall	Inspect and filter network traffic
Easy Memory
Peering
= Connect

VPN Gateway
= Encrypt / Hybrid Connect

Gateway Transit
= Share Gateway

UDR
= Choose Path

NSG
= Allow or Deny
 
⸻
 
Exam Scenarios
Scenario 1
Requirement
Two Azure VNets need high-performance private communication.
Best Choice
VNet Peering
VNet A
   │
Peering
   │
VNet B
 
⸻
 
Scenario 2
Requirement
A company needs to connect its Azure VNet to its corporate datacenter using an encrypted tunnel over the internet.
Best Choice
VPN Gateway
Corporate Network
       │
   VPN Tunnel
       │
VPN Gateway
       │
 Azure VNet
 
⸻
 
Scenario 3
Requirement
Several spoke VNets need to use one VPN Gateway located in a hub VNet.
Best Choice
Gateway Transit
             VPN Gateway
                  │
               Hub VNet
              /        \
         Spoke A      Spoke B
 
⸻
 
Scenario 4
Requirement
Traffic between VNets must pass through a firewall.
Best Choice
Use routing, such as UDRs, together with the appropriate hub/firewall architecture.
Spoke
  │
  │ UDR
  ↓
Firewall
  │
  ↓
Destination
 
⸻
 
Common Mistakes
Mistake 1: Thinking Peering Is Transitive
Incorrect:
A ↔ B ↔ C

Therefore A ↔ C
Not automatically.
Remember:
Peering is non-transitive by default.
 
⸻
 
Mistake 2: Using VPN Gateway for Every Azure-to-Azure Connection
VPN Gateway is useful, but direct VNet Peering is generally the preferred option when the requirement is simply high-performance Azure-to-Azure connectivity.
 
⸻
 
Mistake 3: Confusing Connectivity with Routing
VNet Peering establishes connectivity.
A UDR determines a custom traffic path.
They are related but solve different problems.
 
⸻
 
Mistake 4: Confusing VPN Gateway with ExpressRoute
VPN Gateway
Uses VPN connectivity, commonly over the public internet with IPsec/IKE encryption.
ExpressRoute
Provides private connectivity to Azure through an ExpressRoute provider connection.
VPN Gateway
= Encrypted VPN tunnel

ExpressRoute
= Private dedicated connectivity
 
⸻
 
Quick Comparison
Requirement	Recommended Technology
Connect two Azure VNets	VNet Peering
High-performance VNet communication	VNet Peering
Cross-region VNet communication	Global VNet Peering
Connect Azure to on-premises	VPN Gateway
Encrypted VPN tunnel	VPN Gateway
Share hub gateway with spokes	Gateway Transit
Control traffic path	UDR
Allow/deny network traffic	NSG
Central traffic inspection	Azure Firewall
 
⸻
 
Key Exam and Interview Takeaways
What is VNet Peering?
VNet Peering directly connects Azure VNets using private Azure networking, providing high-performance and low-latency communication.
What is VPN Gateway?
VPN Gateway provides secure VPN connectivity between Azure and other networks using encrypted VPN tunnels.
What is Gateway Transit?
Gateway Transit allows a peered VNet to use a VPN or ExpressRoute gateway located in another VNet, commonly a hub VNet.
Is VNet Peering transitive?
No. VNet Peering is non-transitive by default.
Which is generally faster for Azure-to-Azure connectivity?
VNet Peering.
Which is commonly used for hybrid connectivity?
VPN Gateway.
 
⸻
 
🧠 Easy Memory Formula
VNet Peering
    ↓
Fast + Private + Azure-to-Azure

VPN Gateway
    ↓
Encrypted + Hybrid Connectivity

Gateway Transit
    ↓
Share Hub Gateway

UDR
    ↓
Control Traffic Path
Golden Rule
Peering connects Azure VNets. VPN Gateway connects networks securely through VPN tunnels. Gateway Transit lets peered VNets share a gateway. UDRs control the path traffic takes.
