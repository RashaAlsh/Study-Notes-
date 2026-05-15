# CISM Operations: Virtual LAN (VLAN) Segmentation

## 1. Definition
A logical grouping of network devices that behave as if they are connected to the same wire, regardless of their physical location.

## 2. Primary Security Benefits
*   **Isolates Broadcast Domains:** Stops network sniffing tools from seeing traffic on neighboring segments.
*   **Enables Micro-segmentation:** Acts as the foundation for modern Zero Trust network architectures.
*   **Simplifies Firewall Rules:** Allows firewalls to sit between VLANs to inspect, log, and filter internal traffic.

## 3. Hardening Checklist
1. Disable unused switch ports and assign them to an isolated "black hole" VLAN.
2. Explicitly configure ports as either Access or Trunk (never leave them on 'Auto').
3. Change the native VLAN on all trunk links to a non-default ID.
