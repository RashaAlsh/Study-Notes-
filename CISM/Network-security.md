# CISM Operations: Network Security Fundamentals

## 1. Zero Trust Architecture (ZTA)
*   **Philosophy:** "Never Trust, Always Verify."
*   **Application:** Access is granted based on identity and context, not just network location.

## 2. Secure Protocols
Always prefer encrypted versions of common protocols:
*   **SSH (22)** instead of Telnet (23).
*   **HTTPS (443)** instead of HTTP (80).
*   **SFTP/SCP** instead of FTP (21).
*   **SNMPv3** instead of v1 or v2 (for network management).

## 3. Defensive Layers
1. **Perimeter:** Firewalls, DDoS protection, WAF.
2. **Internal:** NAC, Segmentation, Micro-segmentation.
3. **Detection:** NIDS, SIEM, Honey-pots.
