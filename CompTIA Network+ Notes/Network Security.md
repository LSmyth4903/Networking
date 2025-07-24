# Network Security 🔒

## Overview
This domain, 14% of the exam, focuses on securing networks. Study in small sections with practical labs to understand security concepts.

## Logical Security 🔐
Protects data and access through software.

- **Encryption**: Secures data in transit or at rest.
  - **Example**: HTTPS for web traffic.
  - **Details**: Uses AES or RSA.
- **PKI**: Manages digital certificates.
  - **Example**: Issuing SSL certificates.
  - **Details**: Includes Certificate Authority.
- **IAM**: Controls user access.
  - **Example**: Assigning admin or user roles.
  - **Details**: Centralizes identity management.
- **MFA**: Requires multiple verification methods.
  - **Example**: Password and SMS code.
  - **Details**: Combines knowledge, possession, or biometrics.
- **SSO**: One login for multiple systems.
  - **Example**: Single login for company apps.
  - **Details**: Reduces password fatigue.
- **RADIUS**: Centralized authentication.
  - **Example**: Authenticating Wi-Fi users.
  - **Details**: Uses UDP, common in enterprises.
- **TACACS+**: Cisco authentication.
  - **Example**: Router admin authentication.
  - **Details**: Separates authentication, authorization, accounting.
- **SAML**: Secure identity exchange.
  - **Example**: SSO for cloud apps.
  - **Details**: XML-based, federated identity.
- **Time-Based Authentication**: Temporary codes.
  - **Example**: Google Authenticator TOTP.
  - **Details**: Codes refresh every 30 seconds.
- **Authorization**: Defines access permissions.
  - **Example**: Read-only database access.
  - **Details**: Controls actions post-authentication.
- **Least Privilege**: Minimum necessary access.
  - **Example**: Restricting user permissions to job functions.
  - **Details**: Reduces attack surface.
- **RBAC**: Access by role.
  - **Example**: Admin vs. guest roles.
  - **Details**: Simplifies access management.
- **Geofencing**: Restricts access by location.
  - **Example**: Allowing access only from the office.
  - **Details**: Uses GPS or IP-based checks.

**Example**: A company uses MFA and RBAC for secure access.

**Homelab Activity**: **Set Up MFA Simulation**
- **Tool**: FreeRADIUS (free, download at freeradius.org) and Packet Tracer.
- **Objective**: Simulate RADIUS-based MFA.
- **Steps**:
  1. Install FreeRADIUS on a PC or VM.
  2. In Packet Tracer, add a router and a PC.
  3. Configure router for RADIUS: `aaa new-model`, `radius-server host <PC_IP> key Secret123`.
  4. Set up 802.1X on router: `dot1x system-auth-control`.
  5. Simulate MFA by requiring a username/password and a second factor (e.g., manual token entry).
  6. Test access from PC to router.
- **Why**: Practices logical security with authentication.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s MFA? (Answer: Multi-factor authentication)
2. What’s least privilege? (Answer: Minimum access needed)

## Physical Security 📹
Protects physical network assets.

- **Cameras**: Monitor facilities.
  - **Example**: Surveillance in a data center.
  - **Details**: IP cameras with motion detection.
- **Locks**: Secure equipment rooms.
  - **Example**: Keycard access to server rooms.
  - **Details**: Biometric or electronic locks.

**Example**: A data center uses cameras and biometric locks.

**Homelab Activity**: **Plan Physical Security**
- **Tool**: Text editor and draw.io.
- **Objective**: Design a physical security plan.
- **Steps**:
  1. In draw.io, create a layout of a small server room.
  2. Mark camera placements (e.g., entry/exit points).
  3. Note lock types (e.g., keycard for server cabinet).
  4. Write a brief plan in a text editor: Camera coverage, lock access rules, and monitoring schedule.
- **Why**: Introduces physical security planning.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a use for cameras? (Answer: Monitor facilities)
2. What type of lock is secure? (Answer: Biometric)

## Deception Technologies 🕵️
Misleads attackers to protect networks.

- **Honeypot**: Fake system to attract attackers.
  - **Example**: Decoy server to detect intrusions.
  - **Details**: Logs attacker behavior.
- **Honeynet**: Network of honeypots.
  - **Example**: Simulating a corporate network.
  - **Details**: Broadens deception for monitoring.

**Example**: A honeypot logs unauthorized access attempts.

**Homelab Activity**: **Set Up a Honeypot**
- **Tool**: Dionaea (free, download at github.com/Dionaea).
- **Objective**: Deploy a basic honeypot.
- **Steps**:
  1. Install Dionaea on a VM (e.g., VirtualBox).
  2. Configure Dionaea to simulate services (e.g., HTTP, FTP).
  3. Start Dionaea and monitor logs for connection attempts.
  4. Simulate an attack by connecting to the honeypot’s IP/port from another device.
  5. Review logs to identify attacker actions.
- **Why**: Practices deception technology deployment.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a honeypot? (Answer: Fake system for attackers)
2. What’s a honeynet? (Answer: Network of honeypots)

## Security Terminology 📖
Key security concepts.

| **Term**       | **Definition**                              | **Example**                     | **Details**                              |
|----------------|---------------------------------------------|---------------------------------|------------------------------------------|
| Risk           | Potential for loss                          | Data breach risk               | Quantified by likelihood and impact      |
| Vulnerability  | System weakness                            | Unpatched software             | Exploitable flaw                         |
| Exploit        | Attack on vulnerability                    | Malware exploiting a flaw      | Method to compromise system              |
| Threat         | Potential danger                           | Phishing emails                | Source of potential harm                 |
| CIA Triad      | Confidentiality, Integrity, Availability   | Secure, accurate, accessible data | Core security principles                 |

**Example**: A vulnerability (unpatched router) risks a threat (malware) breaching confidentiality.

**Homelab Activity**: **Identify Vulnerabilities**
- **Tool**: Nmap (free, download at nmap.org).
- **Objective**: Scan for vulnerabilities.
- **Steps**:
  1. Install Nmap on your PC.
  2. Scan your home router: `nmap -sV <router_IP>`.
  3. Identify open ports (e.g., 23/Telnet as a vulnerability).
  4. Document findings in a text file, noting potential exploits (e.g., unencrypted Telnet).
- **Why**: Teaches vulnerability assessment.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a vulnerability? (Answer: System weakness)
2. Name a CIA Triad component. (Answer: Confidentiality)

## Audits and Compliance ✅
Ensures adherence to regulations.

- **Data Locality**: Compliant storage locations.
  - **Example**: Storing EU data in EU servers for GDPR.
  - **Details**: Meets regional laws.
- **PCI DSS**: Secures card transactions.
  - **Example**: Encrypting credit card data.
  - **Details**: Requires encryption and audits.
- **GDPR**: EU data protection.
  - **Example**: Obtaining user consent.
  - **Details**: Enforces user rights.

**Example**: A retailer encrypts card data for PCI DSS compliance.

**Homelab Activity**: **Simulate Compliance Check**
- **Tool**: Text editor.
- **Objective**: Create a PCI DSS checklist.
- **Steps**:
  1. Research PCI DSS requirements (e.g., encryption, access controls).
  2. In a text editor, list 5 requirements (e.g., “Use HTTPS for web traffic”).
  3. For each, note how a home network could comply (e.g., enable HTTPS on router).
  4. Simulate checking: Verify router settings (e.g., WPA3 enabled).
- **Why**: Introduces compliance planning.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s GDPR? (Answer: EU data protection regulation)
2. What’s PCI DSS for? (Answer: Securing card transactions)

## Network Segmentation 🛠️
Isolates network segments for security.

- **IoT/IIoT**: Separates smart devices.
  - **Example**: Isolating IoT thermostats.
  - **Details**: Uses VLANs to limit vulnerabilities.
- **SCADA/ICS/OT**: Secures industrial systems.
  - **Example**: Isolating factory equipment.
  - **Details**: Critical for operational safety.
- **Guest/BYOD**: Isolates visitor devices.
  - **Example**: Guest Wi-Fi separate from employee network.
  - **Details**: Prevents unauthorized access.

**Example**: A factory isolates SCADA systems using VLANs.

**Homelab Activity**: **Segment a Network**
- **Tool**: Packet Tracer.
- **Objective**: Create IoT and guest VLANs.
- **Steps**:
  1. Add a switch, an AP, and four PCs in Packet Tracer.
  2. Create VLAN 10 (IoT) and VLAN 20 (Guest): `vlan 10`, `vlan 20`.
  3. Assign PC1 and PC2 to VLAN 10, PC3 and PC4 to VLAN 20.
  4. Configure AP with SSIDs: “IoT” (VLAN 10), “Guest” (VLAN 20).
  5. Test isolation by pinging between VLANs (should fail).
- **Why**: Practices network segmentation for security.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. Why segment IoT devices? (Answer: Limit vulnerabilities)
2. What’s a guest network for? (Answer: Isolate visitor devices)

## Types of Attacks 🚨
Common network attacks.

| **Attack**            | **Description**                              | **Example**                     | **Details**                              |
|-----------------------|----------------------------------------------|---------------------------------|------------------------------------------|
| DoS/DDoS             | Overwhelms resources                        | Flooding a website             | Disrupts availability                    |
| VLAN Hopping          | Unauthorized VLAN access                    | Accessing restricted VLAN      | Exploits misconfigured switches          |
| MAC Flooding          | Overloads MAC tables                        | Disrupting switch operations   | Causes flooding                         |
| ARP Poisoning         | Misleads ARP tables                         | Redirecting traffic            | Spoofs MAC addresses                    |
| DNS Poisoning         | Corrupts DNS responses                     | Fake website redirection       | Alters DNS cache                        |
| Rogue Devices         | Unauthorized devices                        | Rogue access point            | Mimics legitimate devices                |
| Evil Twin            | Fake Wi-Fi network                         | Mimicking legitimate Wi-Fi     | Steals credentials                      |
| On-Path Attack       | Intercepts data                            | Eavesdropping on traffic       | Man-in-the-middle attack                |
| Social Engineering   | Manipulates users                          | Phishing emails                | Exploits human trust                    |

**Example**: An evil twin Wi-Fi network steals credentials.

**Homelab Activity**: **Simulate ARP Poisoning**
- **Tool**: Packet Tracer and Wireshark.
- **Objective**: Observe ARP behavior.
- **Steps**:
  1. In Packet Tracer, add a switch, two PCs, and a router.
  2. Assign IPs: PC1 (192.168.1.2/24), PC2 (192.168.1.3/24).
  3. Use Wireshark to capture ARP traffic on your PC.
  4. Ping PC2 from PC1 to generate ARP requests.
  5. Observe ARP packets in Wireshark (filter: `arp`).
  6. Simulate poisoning by manually sending a fake ARP reply (advanced; use tools like Cain & Abel if comfortable).
- **Why**: Understands ARP poisoning mechanics.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a DoS attack? (Answer: Overwhelms resources)
2. What’s an evil twin? (Answer: Fake Wi-Fi network)

## Security Features and Defense 🛡️
Protects networks from attacks.

- **Device Hardening**: Secure configurations.
  - **Example**: Disabling unused switch ports.
  - **Details**: Includes firmware updates, disabling Telnet.
- **NAC**: Enforces device compliance.
  - **Example**: Requiring antivirus for access.
  - **Details**: Uses 802.1X or agent-based checks.
- **Key Management**: Secure key storage.
  - **Example**: Managing SSL keys.
  - **Details**: Uses Hardware Security Modules.
- **ACL**: Filters traffic.
  - **Example**: Blocking port 23 (Telnet).
  - **Details**: Rules based on IP, port, or protocol.
- **URL/Content Filtering**: Blocks harmful content.
  - **Example**: Blocking malicious websites.
  - **Details**: Uses proxy or firewall.
- **Trusted vs. Untrusted Zones**: Separates network areas.
  - **Example**: DMZ for public servers.
  - **Details**: Isolates sensitive systems.
- **Screened Subnet**: Isolated network segment.
  - **Example**: DMZ for web servers.
  - **Details**: Controlled by firewalls.

**Example**: A company hardens devices and uses ACLs to block unauthorized traffic.

**Homelab Activity**: **Configure an ACL**
- **Tool**: Packet Tracer.
- **Objective**: Block Telnet with an ACL.
- **Steps**:
  1. Add a router, switch, and two PCs in Packet Tracer.
  2. Configure router: `access-list 101 deny tcp any any eq 23`, `access-list 101 permit ip any any`.
  3. Apply ACL to interface: `interface Gig0/0`, `ip access-group 101 in`.
  4. Attempt Telnet from PC1 to router (should fail).
  5. Verify with `show access-lists`.
- **Why**: Practices traffic filtering for security.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s device hardening? (Answer: Secure configurations)
2. What’s a screened subnet? (Answer: Isolated network segment)

**Graph**: Security Defense Layers
```
   Device Hardening | Secure configs
   NAC             | Device compliance
   ACL             | Traffic filtering
   URL Filtering   | Content control
   Screened Subnet | Isolated zones
```
