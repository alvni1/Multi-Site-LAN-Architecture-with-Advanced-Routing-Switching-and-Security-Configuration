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

This network is a 3-tier LAN architecture spanning two offices—Office A and Office B—connected via a core layer. R1 serves as the gateway to the internet with two redundant connections for high availability.

![Screenshot 2025-03-29 013040](https://github.com/user-attachments/assets/0bdcd447-c4c8-4534-8be6-f3d18ad9c153)

Part 1: Device security was implemented with local user authentication, console login restrictions, inactivity timeouts, and synchronous logging. Passwords were hashed using type 9 (or type 5 if unavailable).

![Screenshot 2025-03-13 093802](https://github.com/user-attachments/assets/2893a07b-ffaa-49ee-ad37-bf93bc6fd596)

![Screenshot 2025-03-13 094313](https://github.com/user-attachments/assets/22c653bc-0a11-4659-a6d7-42761c0755a8)

![Screenshot 2025-03-13 094557](https://github.com/user-attachments/assets/e8717138-1476-4e6d-aaf7-7863d4c5f0db)

Part 2: Layer 2 EtherChannels were established—PAgP in Office A and LACP in Office B. All links between Access and Distribution switches were trunked with VLANs 10, 20, 30/40, 99, and native VLAN 1000. VTPv2 was configured with domain jeremysitlab. VLANs were created and named, and DTP was disabled. Unused ports were administratively shut down.

![Screenshot 2025-03-13 100644](https://github.com/user-attachments/assets/274f9756-a143-48af-b454-4791a8166a8a)

![Screenshot 2025-03-13 102702](https://github.com/user-attachments/assets/4e1b7f76-691f-4ed2-9670-139e11b9522a)

![Screenshot 2025-03-13 162721](https://github.com/user-attachments/assets/29683991-cfe3-41fb-ac8b-0b609936e900)

![Screenshot 2025-03-13 173118](https://github.com/user-attachments/assets/683fb148-0723-4098-b0d0-5691ece82dd6)

Part 3: IPv4 addressing was implemented, including loopback interfaces. HSRPv2 provided gateway redundancy with preemption and priority settings.


Part 4: Rapid PVST+ was deployed with root bridges aligned with HSRP active routers. Portfast and BPDU Guard were enabled on end-host ports.


Part 5: OSPF was configured in point-to-point mode on all Layer 3 interfaces and loopbacks (as passive). R1 functioned as an ASBR with a static default route.


Part 6: DHCP pools were created on R1 with relay agents on distribution switches. DNS services were configured on Server1. NTP, SNMP, Syslog, and SSH with ACLs ensured secure and monitored network services. NAT (static and PAT) allowed external access and internet connectivity. LLDP replaced CDP for device discovery.


Part 7: Extended ACLs permitted ICMP between office PC subnets and blocked other inter-office traffic. Port security, DHCP snooping, and DAI were enabled on access switches for layer 2 security.


Part 8: IPv6 routing was enabled with EUI-64 addressing and static routes (recursive and floating) on R1.


Part 9: A WLC and LWAPs were configured with a WPA2/AES secured WLAN. LWAPs dynamically associated with the controller via a configured dynamic interface.
