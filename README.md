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

![Screenshot 2025-03-13 174644](https://github.com/user-attachments/assets/8f397210-d6fc-4704-a6dd-f0cf7b4e9007)

![Screenshot 2025-03-13 190156](https://github.com/user-attachments/assets/bcee8c4f-24e4-4995-827b-75bdee982704)

![Screenshot 2025-03-13 191415](https://github.com/user-attachments/assets/5c0a7d67-c2b5-4de8-a9c5-39d3c4473bf3)


Part 4: Rapid PVST+ was deployed with root bridges aligned with HSRP active routers. Portfast and BPDU Guard were enabled on end-host ports.

![Screenshot 2025-03-13 192611](https://github.com/user-attachments/assets/97939947-aab5-4e58-b837-f203792a7111)

![Screenshot 2025-03-13 193047](https://github.com/user-attachments/assets/75d987e2-7a0f-4ecc-961b-b1d7bfa2098b)

Part 5: OSPF was configured in point-to-point mode on all Layer 3 interfaces and loopbacks (as passive). R1 functioned as an ASBR with a static default route.

![Screenshot 2025-03-13 194304](https://github.com/user-attachments/assets/4363aea4-c078-4af8-ae77-8d4a75ad4a66)

![Screenshot 2025-03-13 203913](https://github.com/user-attachments/assets/c1bec0bf-b291-4a22-b772-7371759338bc)

![Screenshot 2025-03-13 203921](https://github.com/user-attachments/assets/20a1f07c-fed8-4363-89ac-9c8c2410e9e7)

Part 6: DHCP pools were created on R1 with relay agents on distribution switches. DNS services were configured on Server1. NTP, SNMP, Syslog, and SSH with ACLs ensured secure and monitored network services. NAT (static and PAT) allowed external access and internet connectivity. LLDP replaced CDP for device discovery.

![Screenshot 2025-03-15 220851](https://github.com/user-attachments/assets/4a3134ae-34d2-49c6-938e-4581f37bfce0)

![Screenshot 2025-03-15 220901](https://github.com/user-attachments/assets/4adce4b3-a8d7-4049-883e-b609d1a56036)

![Screenshot 2025-03-16 220954](https://github.com/user-attachments/assets/c0781dc0-69ce-4f0f-8fdb-c261c38e5a80)

![Screenshot 2025-03-16 231707](https://github.com/user-attachments/assets/5bda25f4-b7dc-4b10-ae07-63ee822e0edf)

Part 7: Extended ACLs permitted ICMP between office PC subnets and blocked other inter-office traffic. Port security, DHCP snooping, and DAI were enabled on access switches for layer 2 security.

![Screenshot 2025-03-16 232420](https://github.com/user-attachments/assets/13f5ba23-4e89-4857-9e14-b9b2c27611d2)

![Screenshot 2025-03-16 233854](https://github.com/user-attachments/assets/3e8ad917-d4f0-461f-a377-3e0202ca8fd4)

![Screenshot 2025-03-16 235333](https://github.com/user-attachments/assets/f77b34be-7f2a-45b2-bd91-f4ff28ded49d)

![Screenshot 2025-03-16 235619](https://github.com/user-attachments/assets/5e608652-e1cc-4ca2-bf95-38abe41fde08)

![Screenshot 2025-03-17 000702](https://github.com/user-attachments/assets/c4452dff-15fb-4989-bbd9-0b52668b8673)


Part 8: IPv6 routing was enabled with EUI-64 addressing and static routes (recursive and floating) on R1.

![Screenshot 2025-03-17 001140](https://github.com/user-attachments/assets/3f568eca-9367-4ec4-9c0d-9790dc7fa130)

![Screenshot 2025-03-17 001604](https://github.com/user-attachments/assets/33ef5937-976a-4fac-9729-dde65e57ab35)

Part 9: A WLC and LWAPs were configured with a WPA2/AES secured WLAN. LWAPs dynamically associated with the controller via a configured dynamic interface.

![Screenshot 2025-03-18 074045](https://github.com/user-attachments/assets/de196db7-fbd1-4bf0-81da-5893911a412d)

![Screenshot 2025-03-18 074911](https://github.com/user-attachments/assets/998bf6de-e2d6-447c-b078-1c424b9056fe)


