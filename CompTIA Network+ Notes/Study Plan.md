# ✅ CompTIA Network+ Theory Study Guide Checklist

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



# ✅ CompTIA Network+ N10-009 Study Tracker

## 1.0 Networking Concepts (23%)

### 1.1 OSI Reference Model
- [x] Layer 1 - Physical  
- [x] Layer 2 - Data Link  
- [x] Layer 3 - Network  
- [x] Layer 4 - Transport  
- [x] Layer 5 - Session  
- [x] Layer 6 - Presentation  
- [x] Layer 7 - Application  

### 1.2 Networking Appliances, Applications, and Functions
#### Appliances
- [x] Router  
- [x] Switch  
- [x] Firewall  
- [x] IDS/IPS  
- [x] Load balancer  
- [x] Proxy  
- [x] NAS  
- [x] SAN  
- [x] Wireless (AP, Controller)  

#### Applications
- [ ] CDN (Content Delivery Network)  

#### Functions
- [x] VPN (Virtual Private Network)  
- [ ] QoS (Quality of Service)  
- [ ] TTL (Time to Live)  

### 1.3 Cloud Concepts & Connectivity
#### Concepts
- [x] NFV (Network Functions Virtualization)  
- [x] VPC (Virtual Private Cloud)  
- [x] Network Security Groups  
- [x] Cloud Gateways (Internet, NAT)  

#### Connectivity
- [x] VPN  
- [x] Direct Connect  

#### Deployment Models
- [x] Public  
- [x] Private  
- [x] Hybrid  

#### Service Models
- [x] SaaS  
- [x] IaaS  
- [x] PaaS  

#### Other Concepts
- [x] Scalability  
- [x] Elasticity  
- [ ] Multitenancy  

### 1.4 Ports, Protocols, and Traffic Types
#### Protocols/Ports
- [x] FTP (20/21)  
- [x] SFTP (22)  
- [x] SSH (22)  
- [x] Telnet (23)  
- [x] SMTP (25)  
- [x] DNS (53)  
- [x] DHCP (67/68)  
- [x] TFTP (69)  
- [x] HTTP (80)  
- [x] NTP (123)  
- [x] SNMP (161/162)  
- [x] LDAP (389)  
- [x] HTTPS (443)  
- [x] SMB (445)  
- [x] Syslog (514)  
- [x] SMTPS (587)  
- [x] LDAPS (636)  
- [x] SQL Server (1433)  
- [x] RDP (3389)  
- [x] SIP (5060/5061)  

#### IP Types
- [ ] ICMP  
- [ ] TCP  
- [ ] UDP  
- [ ] GRE  
- [ ] IPSec (AH, ESP, IKE)  

#### Traffic Types
- [ ] Unicast  
- [ ] Multicast  
- [ ] Anycast  
- [ ] Broadcast  

### 1.5 Transmission Media & Transceivers
#### Wireless
- [ ] 802.11 Standards  
- [ ] Cellular  
- [ ] Satellite  

#### Wired
- [ ] 802.3 Standards  
- [ ] Single-mode vs. Multi-mode Fiber  
- [ ] DAC Cable  
- [ ] Twinaxial  
- [ ] Coaxial  
- [ ] Cable Speeds  
- [ ] Plenum vs. Non-Plenum  

#### Transceivers
- [ ] Ethernet  
- [ ] Fibre Channel  

#### Form Factors
- [ ] SFP  
- [ ] QSFP  

#### Connector Types
- [ ] SC  
- [ ] LC  
- [ ] ST  
- [ ] MPO  
- [ ] RJ11  
- [ ] RJ45  
- [ ] BNC  
- [ ] F-Type  

### 1.6 Network Topologies, Architectures, and Traffic Flows
- [ ] Mesh  
- [ ] Distribution  
- [ ] Hybrid  
- [ ] Access  
- [ ] Star/Hub & Spoke  
- [ ] Collapsed Core  
- [ ] Spine and Leaf  
- [ ] Three-tier Hierarchical Model  
- [ ] Point-to-Point  
- [ ] North-South  
- [ ] East-West  

### 1.7 IPv4 Addressing
- [ ] Public vs. Private  
- [ ] APIPA  
- [ ] RFC1918  
- [ ] Loopback  
- [ ] Subnetting  
- [ ] VLSM  
- [ ] CIDR  
- [ ] IPv4 Classes (A, B, C, D, E)  

### 1.8 Modern Network Environments
- [ ] SDN & SD-WAN  
- [ ] Application Aware  
- [ ] Zero-touch Provisioning  
- [ ] Transport Agnostic  
- [ ] Central Policy Management  
- [ ] VXLAN  
- [ ] DCI  
- [ ] ZTA (Zero Trust Architecture)  
- [ ] Policy-based Auth  
- [ ] Least Privilege  
- [ ] SASE/SSE  

#### IaC (Infrastructure as Code)
- [ ] Playbooks/Templates  
- [ ] Config Drift/Compliance  
- [ ] Upgrades  
- [ ] Dynamic Inventory  
- [ ] Source Control (Version control, Branching, Conflicts)  

#### IPv6
- [ ] Mitigating Address Exhaustion  
- [ ] Compatibility  
- [ ] Tunneling  
- [ ] Dual Stack  
- [ ] NAT64  


---

## 2.0 Network Implementation (20%)

### 2.1 Routing Technologies
- [ ] Static Routing  
- [ ] Dynamic Routing (BGP, EIGRP, OSPF)  
- [ ] Administrative Distance  
- [ ] Prefix Length  
- [ ] Metric  
- [ ] NAT  
- [ ] PAT  
- [ ] FHRP  
- [ ] VIP  
- [ ] Subinterfaces  

### 2.2 Switching Technologies
- [ ] VLAN  
- [ ] VLAN Database  
- [ ] SVI  
- [ ] Interface Configuration  
- [ ] Native VLAN  
- [ ] Voice VLAN  
- [ ] 802.1Q Tagging  
- [ ] Link Aggregation  
- [ ] Speed  
- [ ] Duplex  
- [ ] Spanning Tree  
- [ ] MTU  
- [ ] Jumbo Frames  

### 2.3 Wireless Technologies
- [ ] Channel Width  
- [ ] Non-overlapping Channels  
- [ ] Regulatory Impacts (802.11h)  
- [ ] Frequency Options (2.4GHz, 5GHz, 6GHz)  
- [ ] Band Steering  
- [ ] SSID, BSSID, ESSID  
- [ ] Mesh, Ad Hoc, Point to Point, Infrastructure  
- [ ] Encryption (WPA2, WPA3)  
- [ ] Guest Networks  
- [ ] Captive Portals  
- [ ] Authentication (PSK vs. Enterprise)  
- [ ] Omnidirectional vs. Directional Antennas  
- [ ] Autonomous vs. Lightweight APs  

### 2.4 Physical Installations
- [ ] IDF  
- [ ] MDF  
- [ ] Rack Size  
- [ ] Port-side Exhaust/Intake  
- [ ] Patch Panel  
- [ ] Fiber Distribution Panel  
- [ ] Lockable Equipment  
- [ ] UPS  
- [ ] PDU  
- [ ] Power Load  
- [ ] Voltage  
- [ ] Humidity  
- [ ] Fire Suppression  
- [ ] Temperature  

---

## 3.0 Network Operations (19%)

### 3.1 Organizational Processes
- [ ] Physical vs. Logical Diagrams  
- [ ] Rack Diagrams  
- [ ] Cable Maps  
- [ ] Network Diagrams (Layer 1/2/3)  
- [ ] Asset Inventory  
- [ ] IPAM  
- [ ] SLA  
- [ ] Wireless Survey / Heat Map  
- [ ] EOL / EOS  
- [ ] Patch/Firmware Management  
- [ ] Decommissioning  
- [ ] Change Management  
- [ ] Configuration Management  
- [ ] Backup / Baseline / Golden Image  

### 3.2 Network Monitoring
- [ ] Flow Data  
- [ ] Baseline Metrics  
- [ ] Anomaly Alerting  
- [ ] SNMP (v2c, v3, MIB, Traps, Community Strings)  
- [ ] Log Aggregation (Syslog, SIEM)  
- [ ] API Integration  
- [ ] Port Mirroring  
- [ ] Network Discovery  
- [ ] Traffic Analysis  
- [ ] Performance/Availability Monitoring  

### 3.3 Disaster Recovery
- [ ] RPO  
- [ ] RTO  
- [ ] MTTR  
- [ ] MTBF  
- [ ] Cold Site  
- [ ] Warm Site  
- [ ] Hot Site  
- [ ] Active-Active  
- [ ] Active-Passive  
- [ ] Tabletop Exercises  
- [ ] Validation Tests  

### 3.4 IPv4 and IPv6 Services
- [ ] DHCP (Reservations, Scope, Lease, Options, Relay, Exclusions)  
- [ ] SLAAC  
- [ ] DNS (DNSSEC, DoH, DoT, Record Types, Zones, Authoritative vs. Non-authoritative, Primary vs. Secondary, Recursive)  
- [ ] Hosts File  
- [ ] NTP  
- [ ] PTP  
- [ ] NTS  

### 3.5 Network Access and Management
- [ ] VPN (Site-to-site, Client-to-site, Split/Full Tunnel)  
- [ ] SSH  
- [ ] GUI  
- [ ] API  
- [ ] Console  
- [ ] Jump Box / Host  
- [ ] In-band vs. Out-of-band  

---

## 4.0 Network Security (17%)

### 4.1 Basic Network Security
- [ ] Encryption (In Transit / At Rest)  
- [ ] Certificates (PKI, Self-signed)  
- [ ] IAM (AuthN, MFA, SSO, RADIUS, LDAP, SAML, TACACS+, Time-based)  
- [ ] Authorization (Least Privilege, Role-based)  
- [ ] Geofencing  
- [ ] Cameras  
- [ ] Locks  
- [ ] Honeypot / Honeynet  
- [ ] Risk / Vulnerability / Exploit / Threat  
- [ ] CIA Triad  
- [ ] Audits  
- [ ] Data Locality  
- [ ] PCI DSS / GDPR  
- [ ] Network Segmentation (IoT/IIoT, SCADA/ICS/OT, Guest, BYOD)  

### 4.2 Attacks and Impact
- [ ] DoS/DDoS  
- [ ] VLAN Hopping  
- [ ] MAC Flooding  
- [ ] ARP Poisoning/Spoofing  
- [ ] DNS Poisoning/Spoofing  
- [ ] Rogue DHCP / AP Devices  
- [ ] Evil Twin  
- [ ] On-path Attacks  
- [ ] Phishing  
- [ ] Dumpster Diving  
- [ ] Shoulder Surfing  
- [ ] Tailgating  
- [ ] Malware  

### 4.3 Security Solutions
- [ ] Disable Unused Ports/Services  
- [ ] Change Default Passwords  
- [ ] NAC  
- [ ] Port Security  
- [ ] 802.1X  
- [ ] MAC Filtering  
- [ ] Key Management  
- [ ] ACL  
- [ ] URL Filtering  
- [ ] Content Filtering  
- [ ] Trusted vs. Untrusted Zones  
- [ ] Screened Subnet  

---

## 5.0 Network Troubleshooting (21%)

### 5.1 Troubleshooting Methodology
- [ ] Identify the Problem  
- [ ] Establish a Theory  
- [ ] Test the Theory  
- [ ] Plan of Action  
- [ ] Implement or Escalate  
- [ ] Verify Functionality  
- [ ] Document Findings  

### 5.2 Cabling and Interface Issues
- [ ] Incorrect Cable (SMF vs MMF, Cat 5–8, STP/UTP)  
- [ ] Crosstalk, Interference, Attenuation  
- [ ] Improper Termination  
- [ ] TX/RX Transposed  
- [ ] CRC, Runts, Giants, Drops  
- [ ] Error Disabled, Admin Down, Suspended Ports  
- [ ] PoE Budget or Standards Mismatch  
- [ ] Transceiver Mismatch  

### 5.3 Network Services Issues
- [ ] Network Loops  
- [ ] Root Bridge Selection  
- [ ] Port States  
- [ ] VLAN Assignment  
- [ ] ACL  
- [ ] Routing Table  
- [ ] Route Selection  
- [ ] Default Routes  
- [ ] Address Pool Exhaustion  
- [ ] Incorrect Default Gateway  
- [ ] Duplicate IP  
- [ ] Incorrect Subnet Mask  
- [ ] Congestion / Bottlenecks  
- [ ] Latency / Packet Loss / Jitter  
- [ ] Channel Overlap  
- [ ] Wireless Signal Loss  
- [ ] Client Disassociation  
- [ ] Roaming Issues  

### 5.4 Troubleshooting Tools
#### Software Tools
- [ ] Protocol Analyzer  
- [ ] ping  
- [ ] traceroute/tracert  
- [ ] nslookup  
- [ ] tcpdump  
- [ ] dig  
- [ ] netstat  
- [ ] ip/ifconfig/ipconfig  
- [ ] arp  
- [ ] Nmap  
- [ ] LLDP/CDP  
- [ ] Speed Tester  

#### Hardware Tools
- [ ] Toner  
- [ ] Cable Tester  
- [ ] Taps  
- [ ] Wi-Fi Analyzer  
- [ ] Visual Fault Locator  

#### Device Commands
- [ ] show mac-address-table  
- [ ] show route  
- [ ] show interface  
- [ ] show config  
- [ ] show arp  
- [ ] show vlan  
- [ ] show power  
