# CompTIA Network+ 7-Week Theory Study Guide Checklist

---

## Official Syllabus Overview (Exam Domains & Weightings)

### Networking Concepts (23%)
- OSI model layers: physical, data link, network, transport, session, presentation, application.
- Networking appliances: routers, switches, firewalls, IDS/IPS, load balancers, proxies, NAS, SAN, wireless devices.
- Cloud concepts: NFV, VPC, network security groups, cloud gateways, deployment models (public, private, hybrid), service models (SaaS, IaaS, PaaS).
- Ports and protocols: FTP, SFTP, SSH, Telnet, SMTP, DNS, DHCP, HTTP, HTTPS, SNMP, LDAP, RDP, SIP.
- Traffic types: unicast, multicast, anycast, broadcast.
- Transmission media: wireless (802.11, cellular, satellite), wired (fiber, coaxial, DAC).
- Transceivers and connectors: SC, LC, ST, MPO, RJ11, RJ45, F-type, BNC.
- Network topologies: mesh, hybrid, star/hub and spoke, spine and leaf, point-to-point, three-tier, collapsed core.
- IPv4 addressing: public vs. private, APIPA, RFC1918, loopback, subnetting (VLSM, CIDR), address classes (A, B, C, D, E).

### Network Implementation (20%)
- Routing technologies: static and dynamic routing (BGP, EIGRP, OSPF), route selection, NAT, PAT, FHRP, VIP, subinterfaces.
- Switching technologies: VLANs, interface configuration, spanning tree, MTU, jumbo frames.
- Wireless devices: channels, frequency options, SSID, network types, encryption, guest networks, authentication, antennas, access points.
- Physical installations: installation implications, power considerations, environmental factors.

### Network Operations (19%)
- Documentation: physical vs. logical diagrams, rack diagrams, cable maps, network diagrams, asset inventory, IPAM, SLA, wireless surveys.
- Life-cycle management: EOL, EOS, software management, decommissioning.
- Change management: request process tracking.
- Configuration management: production, backup, baseline configurations.
- Network monitoring: SNMP, flow data, packet capture, baseline metrics, log aggregation, API integration, port mirroring.
- Disaster recovery: RPO, RTO, MTTR, MTBF, cold/warm/hot sites, active-active/passive, testing.
- Network services: DHCP, SLAAC, DNS, NTP, PTP, NTS.
- Access and management: VPNs, SSH, GUI, API, console.

### Network Security (14%)
- Logical security: encryption (data in transit/rest), PKI, IAM, MFA, SSO, RADIUS, LDAP, SAML, TACACS+, time-based authentication, authorization, least privilege, role-based access control, geofencing.
- Physical security: cameras and locks.
- Deception technologies: honeypot, honeynet.
- Security terminology: risk, vulnerability, exploit, threat, CIA triad.
- Audits and compliance: data locality, PCI DSS, GDPR.
- Network segmentation: IoT, IIoT, SCADA, ICS, OT, guest, BYOD.
- Types of attacks: DoS/DDoS, VLAN hopping, MAC flooding, ARP poisoning/spoofing, DNS poisoning/spoofing, rogue devices/services, evil twin, on-path attack, social engineering (phishing, dumpster diving, shoulder surfing, tailgating).
- Security features and defense: device hardening, NAC, key management, ACL, URL/content filtering, trusted vs. untrusted zones, screened subnet.

### Network Troubleshooting (24%)
- Troubleshooting methodology: identify problem, establish theory, test, plan and implement solution, verify, document.
- Cabling and physical interface issues: incorrect cable type, signal degradation, improper termination, TX/RX transposed; interface counters and status; hardware issues (PoE, transceiver mismatch, signal strength).
- Network services issues: switching (STP, VLANs, ACLs), routing (routing tables, default routes), address pool exhaustion, incorrect gateway/IP/subnet mask.
- Performance issues: congestion, latency, packet loss, wireless interference.
- Tools and protocols: protocol analyzers, command line tools, cable testers, Wi-Fi analyzers.

---

## Week 1 — Networking Concepts  
- [ ] Day 1: OSI Model Layers 1-3  
  *Understand the physical layer (cables, connectors, signaling), data link layer (MAC addressing, switches, frames), and network layer (IP addressing, routing basics). Review how data travels through these layers.*  
- [ ] Day 2: OSI Model Layers 4-7  
  *Study transport layer protocols (TCP/UDP), session management, presentation layer functions (encryption, compression), and application layer protocols.*  
- [ ] Day 3: Networking Appliances  
  *Explore roles, functions, and configuration basics of routers, switches, firewalls, IDS/IPS.*  
- [ ] Day 4: Additional Appliances  
  *Learn about load balancers, proxies, NAS and SAN storage, wireless devices (APs, controllers).*  
- [ ] Day 5: Cloud Concepts  
  *Study NFV, VPCs, cloud security groups, gateways, plus deployment (public/private/hybrid) and service models (SaaS, IaaS, PaaS).*  
- [ ] Day 6: Ports & Protocols Part 1  
  *Deep dive into FTP, SFTP, SSH, Telnet, SMTP, and DNS — how they work and their typical ports.*  

---

## Week 2 — Networking Concepts & Traffic Types  
- [ ] Day 1: Ports & Protocols Part 2  
  *Study DHCP, HTTP/S, SNMP, LDAP, RDP, and SIP protocols, including use cases and security considerations.*  
- [ ] Day 2: Traffic Types  
  *Understand unicast, multicast, anycast, and broadcast traffic and scenarios where each is used.*  
- [ ] Day 3: Wireless Transmission Media  
  *Learn wireless standards (802.11 variants), cellular networks, satellite communications, and their characteristics.*  
- [ ] Day 4: Wired Transmission Media  
  *Explore fiber optic, coaxial, and direct attached copper (DAC) cables, with pros/cons and typical uses.*  
- [ ] Day 5: Transceivers & Connectors  
  *Understand types like SC, LC, ST, MPO, and cable connectors like RJ45, RJ11, F-type, BNC.*  
- [ ] Day 6: Network Topologies Part 1  
  *Review mesh, hybrid, and star/hub-spoke topologies — advantages, disadvantages, and use cases.*  

---

## Week 3 — Network Topologies & IPv4 Addressing  
- [ ] Day 1: Network Topologies Part 2  
  *Study spine-leaf, point-to-point, three-tier, and collapsed core topologies.*  
- [ ] Day 2: IPv4 Addressing Basics  
  *Understand public vs private addressing, APIPA, loopback, and RFC1918 reserved ranges.*  
- [ ] Day 3: IPv4 Address Classes & Subnetting Basics  
  *Learn address classes (A-E) and practice basic subnetting concepts.*  
- [ ] Day 4: Advanced Subnetting  
  *Practice VLSM and CIDR to create efficient subnet masks.*  
- [ ] Day 5: Routing Basics  
  *Understand static vs dynamic routing, routing tables, and route metrics.*  
- [ ] Day 6: Routing Protocols  
  *Overview of BGP, EIGRP, and OSPF: purposes, operation, and characteristics.*  

---

## Week 4 — Routing & Switching Technologies  
- [ ] Day 1: Route Selection, NAT, PAT  
  *Learn how routers select routes and use NAT/PAT for IP address translation.*  
- [ ] Day 2: FHRP and VIPs  
  *Understand First Hop Redundancy Protocols (HSRP, VRRP) and Virtual IP addresses.*  
- [ ] Day 3: VLANs & Interface Configuration  
  *Study VLAN concepts, configuration, tagging, and trunking.*  
- [ ] Day 4: Spanning Tree, MTU, Jumbo Frames  
  *Learn STP operation and frame size considerations.*  
- [ ] Day 5: Wireless Devices  
  *Review wireless channels, frequencies, SSIDs, encryption types.*  
- [ ] Day 6: Wireless Authentication & Antennas  
  *Understand authentication methods and antenna types/use cases.*  

---

## Week 5 — Physical Installations & Network Operations  
- [ ] Day 1: Physical Installations  
  *Cabling standards, power delivery, environmental factors like cooling and grounding.*  
- [ ] Day 2: Power Considerations  
  *Learn about PoE types, UPS basics, and grounding best practices.*  
- [ ] Day 3: Documentation  
  *Create physical & logical network diagrams, cable maps, asset inventories, and IP address management.*  
- [ ] Day 4: Life-cycle Management  
  *Understand equipment EOL, EOS, software upgrades, and decommissioning.*  
- [ ] Day 5: Change Management  
  *Study change request processes, approval, and documentation.*  
- [ ] Day 6: Configuration Management  
  *Backup and restore configurations, baseline config concepts.*  

---

## Week 6 — Network Monitoring & Disaster Recovery  
- [ ] Day 1: Network Monitoring  
  *Use of SNMP, flow data, packet capture tools, and baseline metric tracking.*  
- [ ] Day 2: Log Aggregation & API Integration  
  *Learn centralized logging and integration methods for monitoring.*  
- [ ] Day 3: Disaster Recovery Concepts  
  *Review Recovery Point Objective (RPO), Recovery Time Objective (RTO), MTTR, MTBF.*  
- [ ] Day 4: Disaster Recovery Sites  
  *Understand cold, warm, hot sites, active-active and active-passive configurations.*  
- [ ] Day 5: Network Services  
  *Study DHCP, SLAAC, DNS, NTP, PTP, and Network Time Security.*  
- [ ] Day 6: Access & Management  
  *Explore VPNs, SSH, GUI management, APIs, and console access.*  

---

## Week 7 — Network Security & Troubleshooting  
- [ ] Day 1: Logical Security  
  *Encryption basics, PKI, IAM, MFA, SSO, and authentication protocols (RADIUS, LDAP, SAML, TACACS+).*  
- [ ] Day 2: Authorization Models & Physical Security  
  *Least privilege, RBAC, geofencing; physical controls like cameras and locks.*  
- [ ] Day 3: Deception Technologies & Security Terminology  
  *Honeypots, honeynets, risk/vulnerability/threat concepts, CIA triad.*  
- [ ] Day 4: Audits, Compliance & Network Segmentation  
  *PCI DSS, GDPR, IoT/IIoT segmentation, SCADA, guest networks, BYOD.*  
- [ ] Day 5: Types of Attacks & Social Engineering  
  *DoS/DDoS, VLAN hopping, ARP/DNS poisoning, rogue devices, phishing, tailgating, and others.*  
- [ ] Day 6: Security Features & Troubleshooting Methodology  
  *Device hardening, NAC, ACLs, URL filtering; problem identification, theory testing, implementation, verification, documentation.*  

---
