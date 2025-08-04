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

# ✅ CompTIA Network+ 6-Week Theory Study Guide Checklist

---

## Week 1 — OSI Model, Devices, and Cloud Fundamentals

- [ ] **Day 1: OSI Model Overview** (1.1)  
  Understand all 7 OSI layers and how data moves through each one.

- [ ] **Day 2: Networking Devices** (1.1)  
  Routers, switches, firewalls, IDS/IPS, load balancers, proxies, NAS, SAN, wireless devices.

- [ ] **Day 3: Network Functions** (1.2)  
  Core network services and their roles.

- [ ] **Day 4: Designing the Cloud** (1.3)  
  NFV, VPC, cloud security groups, gateways.

- [ ] **Day 5: Cloud Models** (1.3)  
  Deployment models (Public, Private, Hybrid) and Service models (SaaS, IaaS, PaaS).

- [ ] **Day 6: Introduction to IP** (1.4)  
  IPv4 basics, address types (public/private, loopback, APIPA).

---

## Week 2 — Protocols, Wireless, and Media

- [ ] **Day 1: Common Ports & Protocols** (1.4)  
  FTP, SFTP, SSH, Telnet, SMTP, DNS, DHCP, HTTP, HTTPS, SNMP, LDAP, RDP, SIP.

- [ ] **Day 2: Other Useful Protocols & Traffic Types** (1.4)  
  NTP, Syslog, ICMP; traffic types: unicast, multicast, anycast, broadcast.

- [ ] **Day 3: Wireless Networking** (1.5)  
  802.11 standards, frequencies, channels, encryption, AP types.

- [ ] **Day 4: Ethernet Standards & Optical Fiber** (1.5)  
  Ethernet speeds, full/half duplex, single-mode vs multi-mode fiber.

- [ ] **Day 5: Copper Cabling & Transceivers** (1.5)  
  Coax, twisted pair, DAC; SFP/QSFP/GBIC and connectors (SC, LC, RJ45, etc.).

- [ ] **Day 6: Network Topologies** (1.6)  
  Star, mesh, hub-spoke, spine-leaf, three-tier, point-to-point.

---

## Week 3 — IPv4 Addressing and Subnetting

- [ ] **Day 1: IPv4 Addressing Basics** (1.7)  
  Public vs private, APIPA, loopback, RFC1918.

- [ ] **Day 2: Classful Addressing and Subnet Masks** (1.7)  
  Address classes A-E, default masks.

- [ ] **Day 3: Calculating IPv4 Subnets and Hosts** (1.7)  
  Practice subnet calculations, usable hosts, CIDR.

- [ ] **Day 4: Magic Number & 7-Second Subnetting** (1.7)  
  Speed subnetting techniques.

- [ ] **Day 5: IPv6 Addressing** (1.8)  
  Structure, shorthand, address types (link-local, global).

- [ ] **Day 6: Software Defined Networking & VXLAN** (1.8)  
  SDN concepts, VXLAN overlays and tunneling.

---

## Week 4 — Routing & Switching

- [ ] **Day 1: Dynamic Routing** (2.1)  
  Routing protocols: RIP, OSPF, EIGRP, BGP.

- [ ] **Day 2: NAT and PAT** (2.1)  
  Static NAT, Dynamic NAT, PAT scenarios.

- [ ] **Day 3: VLANs and Trunking** (2.2)  
  VLAN concepts, trunk ports, native VLANs.

- [ ] **Day 4: Interface Config & Spanning Tree** (2.2)  
  Speed/duplex settings, STP loop prevention.

- [ ] **Day 5: Wireless Technologies** (2.3)  
  Channels, SSID, guest networks, authentication, encryption types.

- [ ] **Day 6: Network Types & Wireless Encryption** (2.3)  
  Enterprise vs personal modes, WPA2/WPA3, open networks.

---

## Week 5 — Network Operations & Services

- [ ] **Day 1: Installing Networks & Power** (2.4)  
  Cabling, rack setup, PoE, UPS, grounding.

- [ ] **Day 2: Environmental Factors & Topologies** (2.4, 1.6)  
  Cooling, EMI, airflow; revisit topologies in context.

- [ ] **Day 3: Documentation & Life-cycle Mgmt** (3.1)  
  Diagrams, asset inventory, IPAM, EOL/EOS.

- [ ] **Day 4: Configuration & Change Mgmt** (3.1)  
  Backups, baselines, change request process.

- [ ] **Day 5: SNMP, Logs & Monitoring** (3.2)  
  SNMP v2/v3, flow data, packet capture, log aggregation.

- [ ] **Day 6: Redundancy & Disaster Recovery** (3.3)  
  MTTR, RTO, hot/warm/cold sites, active-active/passive.

---

## Week 6 — Core Services, Security & Troubleshooting

- [ ] **Day 1: Network Services** (3.4)  
  DHCP, SLAAC, DNS records, NTP/PTP/NTS.

- [ ] **Day 2: VPNs & Remote Access** (3.5)  
  Split tunnel, full tunnel, client setup, SSH, console.

- [ ] **Day 3: Security Concepts & Authentication** (4.1)  
  CIA triad, MFA, IAM, RADIUS, SAML, PKI.

- [ ] **Day 4: Attacks & Vulnerabilities** (4.2)  
  DoS/DDoS, VLAN hopping, ARP/DNS poisoning, phishing, rogue services.

- [ ] **Day 5: Device Security & ACLs** (4.3)  
  Hardening, ACLs, trusted zones, NAC, segmentation.

- [ ] **Day 6: Troubleshooting Methodology** (5.1)  
  Problem identification, hypothesis, plan, implement, verify, document.


