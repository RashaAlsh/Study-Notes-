# CISM Infrastructure: Routers vs. Firewalls

## 1. Functional Comparison
| Feature | Router | Firewall |
| :--- | :--- | :--- |
| **Primary Goal** | Connect networks & forward packets. | Protect networks & filter packets. |
| **OSI Layer** | Primarily Layer 3 (Network). | Layers 3, 4, and 7 (Application). |
| **Traffic Philosophy**| "Allow everything unless explicitly blocked." | "Block everything unless explicitly allowed." |
| **Inspection Type** | Stateless (Basic ACLs). | Stateful / Deep Packet Inspection (DPI). |

## 2. Architectural Placement
*   **Edge Router:** Sits at the very perimeter, directly facing the ISP. It handles massive throughput and basic outer filtering.
*   **Perimeter Firewall:** Sits immediately behind the edge router. It inspects all incoming/outgoing traffic and manages the **DMZ**.
*   **Internal Firewall:** Sits between internal **VLANs** to enforce micro-segmentation and limit lateral movement.
