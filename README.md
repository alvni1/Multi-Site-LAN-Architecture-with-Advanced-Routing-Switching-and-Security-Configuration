<h1>Multi-Site LAN Architecture with Advanced Routing, Switching, and Security Configuration </h1>



<h2>Description</h2>
Project consisted of: 

- <b>Designed and implemented a secure, scalable 3-tier LAN architecture connecting two office sites via a core layer, with R1 providing redundant internet access and serving as the network’s gateway and DHCP server.</b>
- <b>Configured Layer 2 and Layer 3 protocols including EtherChannel (PAgP/LACP), VTPv2, Rapid PVST+, HSRPv2, and OSPF (point-to-point) for optimized network performance, redundancy, and convergence.</b>
- <b>Deployed comprehensive network services including DHCP relay, DNS, NTP, SNMP, Syslog, SSH with ACLs, and NAT (static and PAT), ensuring centralized management, secure remote access, and internet connectivity.</b>
- <b>Implemented Layer 2 security controls such as Port Security, DHCP Snooping, and Dynamic ARP Inspection (DAI), along with extended ACLs to control inter-office traffic and enforce access policies.</b>
- <b>Configured a Wireless LAN Controller (WLC) and Lightweight Access Points (LWAPs) with WPA2/AES encryption, enabling secure wireless connectivity and dynamic AP association.</b>

<h2>Languages and Utilities Used</h2>

- <b>Cisco CLI</b> 


<h2>Environments Used </h2>

- <b>Cisco Packet Tracer</b> 


<h2>Program walk-through:</h2>

Part 1 – Device Security:

Type 9/5 Hashing: Secure password storage methods; Type 9 (scrypt) is stronger than Type 5 (MD5).
Console Login with Local User: Ensures only authorized users access devices locally.
Inactivity Timeout & Synchronous Logging: Enhances security and usability.
Part 2 – VLANs & EtherChannels:

EtherChannel: Combines multiple physical links into one logical link for redundancy and speed.
PAgP (Port Aggregation Protocol): Cisco proprietary EtherChannel negotiation.
LACP (Link Aggregation Control Protocol): Open standard EtherChannel negotiation.
DTP (Dynamic Trunking Protocol): Automatically negotiates trunking; disabled for security.
VLAN (Virtual LAN): Logically separates networks on the same physical switch.
VTPv2 (VLAN Trunking Protocol): Distributes VLAN info across switches.
Trunk Links: Carry multiple VLANs over a single link.
Native VLAN: VLAN for untagged traffic; VLAN 1000 here.
Access Mode: Ports assigned to a single VLAN (e.g., for PCs or phones).
Part 3 – IP Addressing & Redundancy:

IPv4: Core addressing system for devices.
Loopback Interface: Virtual interface used for management and routing stability.
HSRPv2 (Hot Standby Router Protocol v2): Provides gateway redundancy. Active router takes priority; preemption ensures failover.
Part 4 – Spanning Tree Protocol:

Rapid PVST+ (Rapid Per VLAN Spanning Tree Plus): Prevents Layer 2 loops while allowing rapid convergence.
PortFast: Speeds up port activation for end devices.
BPDU Guard: Prevents rogue switches from affecting STP by disabling ports sending BPDUs.
Part 5 – Routing:

OSPF (Open Shortest Path First): Link-state routing protocol for dynamic route exchange.
Point-to-Point Network Type: Simplifies OSPF setup; no DR/BDR election.
ASBR (Autonomous System Boundary Router): R1 connects OSPF to external networks.
Static Default Route: Used to direct unknown traffic to the internet.
Part 6 – Network Services:

DHCP (Dynamic Host Configuration Protocol): Assigns IP addresses to clients.
DHCP Relay: Forwards DHCP requests from clients to servers across networks.
DNS (Domain Name System): Translates domain names (e.g., google.com) to IPs.
NTP (Network Time Protocol): Synchronizes time across devices.
SNMP (Simple Network Management Protocol): Monitors network devices; community string allows "get" (read-only) access.
Syslog: Collects system logs centrally for monitoring.
SSH (Secure Shell): Encrypted remote access.
ACL (Access Control List): Filters traffic; here, limits SSH access.
NAT (Network Address Translation):
Static NAT: Maps one internal IP to one public IP (e.g., server access).
PAT (Port Address Translation): Multiple devices share one public IP for internet access.
CDP (Cisco Discovery Protocol): Disabled for security; replaced by LLDP (Link Layer Discovery Protocol), an open standard for device discovery.
Part 7 – Security Features:

Extended ACLs: Filters traffic by IP and protocol; here, allows ICMP between subnets.
Port Security: Limits the number of MAC addresses per port.
DHCP Snooping: Blocks unauthorized DHCP servers.
DAI (Dynamic ARP Inspection): Prevents ARP spoofing attacks.
Part 8 – IPv6 Configuration:

IPv6: Next-gen IP addressing.
EUI-64: Automatically generates interface IDs.
Recursive & Floating Routes: Static IPv6 routes for redundancy and backup paths.
Part 9 – Wireless LAN Configuration:

WLC (Wireless LAN Controller): Manages wireless access points (LWAPs).
LWAP (Lightweight Access Point): Relies on WLC for management.
WLAN (Wireless LAN): Configured with WPA2/AES encryption for secure wireless access.
