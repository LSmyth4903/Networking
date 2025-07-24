# Network Operations 🖥️

## Overview
This domain, 19% of the exam, focuses on maintaining and monitoring networks. Study in small sections with hands-on labs to master operations.

## Documentation 📝
Tracks network configurations and layouts.

| **Type**            | **Description**                              | **Example**                     | **Details**                              |
|---------------------|----------------------------------------------|---------------------------------|------------------------------------------|
| Physical Diagram    | Hardware layout                             | Server room wiring              | Shows physical connections               |
| Logical Diagram     | Data flow                                   | VLAN assignments               | Maps traffic paths                       |
| Rack Diagram        | Equipment in racks                          | Data center rack layout        | Organizes rack positions                |
| Cable Map           | Cable connections                          | Ethernet cable mapping         | Tracks cable runs                       |
| Network Diagram     | Network structure                          | Corporate LAN diagram          | Visualizes topology                     |
| Asset Inventory     | Lists devices                              | Router/switch inventory        | Tracks hardware details                 |
| IPAM                | Tracks IP assignments                      | IP allocation software         | Manages IP addresses                    |
| SLA                 | Performance expectations                    | 99.9% ISP uptime               | Defines service guarantees              |
| Wireless Survey     | Maps Wi-Fi coverage                        | AP placement optimization      | Identifies signal strength gaps         |

**Example**: A network diagram maps VLANs, and a cable map tracks wiring.

**Homelab Activity**: **Create Network Documentation**
- **Tool**: Packet Tracer and diagramming software (e.g., draw.io, free at draw.io).
- **Objective**: Document a small network.
- **Steps**:
  1. In Packet Tracer, create a network with one router, one switch, and three PCs.
  2. Assign IPs: PC1 (192.168.1.2/24), PC2 (192.168.1.3/24), PC3 (192.168.1.4/24).
  3. Use draw.io to create a physical diagram (show cables, devices).
  4. Create a logical diagram showing IP assignments and data flow.
  5. Save both diagrams and list devices in an asset inventory (e.g., Excel).
- **Why**: Practices documentation for network management.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a logical diagram? (Answer: Shows data flow)
2. Why use IPAM? (Answer: Manage IP addresses)

## Life-Cycle Management 🔄
Manages devices from deployment to retirement.

- **EOL (End of Life)**: Device no longer supported.
  - **Example**: Replacing an EOL router.
  - **Details**: Vendors stop updates or repairs.
- **EOS (End of Support)**: No further updates.
  - **Example**: Upgrading switch firmware before EOS.
  - **Details**: Ensures security and functionality.
- **Software Management**: Updates firmware.
  - **Example**: Patching switch vulnerabilities.
  - **Details**: Prevents security risks.
- **Decommissioning**: Safe equipment removal.
  - **Example**: Recycling old servers after data wiping.
  - **Details**: Follows security and environmental rules.

**Example**: Replacing EOL switches and updating firmware ensures reliability.

**Homelab Activity**: **Simulate Firmware Update**
- **Tool**: GNS3.
- **Objective**: Update router firmware in a virtual lab.
- **Steps**:
  1. In GNS3, add a router (e.g., Cisco IOSv).
  2. Simulate a firmware update: Upload a new IOS image via TFTP (use a TFTP server like tftpd64).
  3. Configure router: `copy tftp flash`, enter TFTP server IP and image name.
  4. Verify with `show version` to confirm new firmware.
- **Why**: Practices software management for device longevity.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s EOL? (Answer: End of device support)
2. Why update firmware? (Answer: Patch vulnerabilities)

## Change Management 🔧
Controls network changes to avoid disruptions.

- **Request Process**: Formal change requests.
  - **Example**: Requesting a new VLAN via ticketing.
  - **Details**: Includes approval, testing, rollback plans.
- **Tracking**: Logs changes for accountability.
  - **Example**: Documenting firewall rule changes.
  - **Details**: Tracks who, what, when, and why.

**Example**: An admin logs a firewall rule change for auditing.

**Homelab Activity**: **Document a Change Request**
- **Tool**: Packet Tracer and text editor.
- **Objective**: Simulate and document a VLAN change.
- **Steps**:
  1. In Packet Tracer, add a switch and two PCs.
  2. Create VLAN 30: `vlan 30`, assign PC1 to it (`switchport access vlan 30`).
  3. In a text editor, write a change request: Describe adding VLAN 30, purpose (e.g., new department), approval (self), and rollback (delete VLAN).
  4. Verify connectivity with `ping` and document results.
- **Why**: Practices change management processes.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s in a change request? (Answer: Approval, testing, rollback)
2. Why track changes? (Answer: Accountability)

## Configuration Management ⚙️
Ensures consistent device settings.

- **Production Configurations**: Active settings.
  - **Example**: Router settings for routing.
  - **Details**: Defines operational state.
- **Backup Configurations**: Saved for recovery.
  - **Example**: Backing up switch configs.
  - **Details**: Stored via TFTP or cloud.
- **Baseline Configurations**: Standard settings.
  - **Example**: Standard VLAN settings for switches.
  - **Details**: Ensures consistency.

**Example**: Baseline configs ensure uniform switch settings, with backups for recovery.

**Homelab Activity**: **Backup Switch Configuration**
- **Tool**: Packet Tracer and TFTP server (e.g., tftpd64).
- **Objective**: Save and restore a switch config.
- **Steps**:
  1. Set up a switch in Packet Tracer with VLAN 10.
  2. Install a TFTP server on your PC.
  3. Save config: `copy running-config tftp`, enter TFTP server IP.
  4. Simulate a failure: Erase config (`erase startup-config`).
  5. Restore: `copy tftp running-config`.
  6. Verify with `show vlan brief`.
- **Why**: Practices configuration backup and recovery.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a baseline configuration? (Answer: Standard settings)
2. Why back up configs? (Answer: For recovery)

## Network Monitoring 📊
Tracks performance and issues.

- **SNMP**: Collects device data.
  - **Example**: Monitoring router CPU usage.
  - **Details**: Uses OIDs for metrics.
- **Flow Data**: Analyzes traffic patterns.
  - **Example**: Detecting spikes with NetFlow.
  - **Details**: Tracks traffic volume.
- **Packet Capture**: Records packets.
  - **Example**: Using Wireshark for analysis.
  - **Details**: Captures raw packet data.
- **Baseline Metrics**: Normal performance benchmarks.
  - **Example**: Typical 100 Mbps usage.
  - **Details**: Deviations indicate issues.
- **Log Aggregation**: Centralizes logs.
  - **Example**: Collecting logs in Splunk.
  - **Details**: Simplifies troubleshooting.
- **API Integration**: Automates monitoring.
  - **Example**: Fetching status via REST API.
  - **Details**: Integrates with tools like Zabbix.
- **Port Mirroring**: Copies traffic for analysis.
  - **Example**: Mirroring traffic to an IDS.
  - **Details**: Duplicates port traffic.

**Example**: SNMP monitors switch performance, and packet capture diagnoses issues.

**Homelab Activity**: **Monitor with SNMP**
- **Tool**: Packet Tracer and SNMP tool (e.g., PRTG, free trial at paessler.com).
- **Objective**: Monitor a switch’s performance.
- **Steps**:
  1. In Packet Tracer, add a switch and two PCs.
  2. Enable SNMP on switch: `snmp-server community public RO`.
  3. Install PRTG on your PC and add the switch as a device (use switch’s IP).
  4. Monitor CPU usage and interface traffic.
  5. Generate traffic by pinging between PCs and observe changes.
- **Why**: Introduces network monitoring with SNMP.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s SNMP used for? (Answer: Device monitoring)
2. What’s packet capture? (Answer: Recording packets)

**Graph**: Monitoring Tools
```
   SNMP        | Device metrics
   Flow Data   | Traffic patterns
   Packet Capture | Detailed analysis
   Log Aggregation | Centralized logs
   API Integration | Automation
```

## Disaster Recovery 🛡️
Ensures continuity during failures.

- **RPO**: Data loss tolerance.
  - **Example**: Hourly backups to lose at most 1 hour.
  - **Details**: Defines backup frequency.
- **RTO**: Downtime tolerance.
  - **Example**: Restoring a server in 2 hours.
  - **Details**: Measures acceptable downtime.
- **MTTR**: Average repair time.
  - **Example**: Fixing a switch in 4 hours.
  - **Details**: Tracks repair efficiency.
- **MTBF**: Device reliability.
  - **Example**: Router uptime of 1 year.
  - **Details**: Indicates longevity.
- **Sites**:
  - **Cold Site**: Basic infrastructure, slow recovery.
  - **Warm Site**: Partial setup, faster recovery.
  - **Hot Site**: Fully operational, immediate recovery.
  - **Example**: Hot site for banking systems.
- **Active-Active/Passive**: Redundancy models.
  - **Example**: Active-active for load-balanced servers.
  - **Details**: Active-active uses all devices; active-passive uses standby.
- **Testing**: Validates recovery plans.
  - **Example**: Simulating a server failure.
  - **Details**: Ensures plans are effective.

**Example**: A bank uses a hot site and hourly backups for minimal downtime.

**Homelab Activity**: **Test Backup and Recovery**
- **Tool**: Packet Tracer and text editor.
- **Objective**: Simulate a disaster recovery plan.
- **Steps**:
  1. Configure a router with a basic setup (e.g., IP 192.168.1.1/24).
  2. Save config to TFTP: `copy running-config tftp`.
  3. Simulate failure: Erase config (`erase startup-config`).
  4. Restore config: `copy tftp running-config`.
  5. Document RPO (e.g., 1 hour) and RTO (e.g., 10 minutes) for this scenario.
- **Why**: Practices disaster recovery processes.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s RPO? (Answer: Data loss tolerance)
2. What’s a hot site? (Answer: Fully operational recovery site)

## Network Services 🌐
Core network functions.

- **DHCP**: Assigns IPs dynamically.
  - **Example**: Assigning IPs to office devices.
  - **Details**: Uses DORA process.
- **SLAAC**: IPv6 address assignment.
  - **Example**: Auto-configuring IPv6.
  - **Details**: Uses router advertisements.
- **DNS**: Resolves domain names to IPs.
  - **Example**: Resolving google.com to 142.250.190.78.
  - **Details**: Uses hierarchical servers.
- **NTP**: Synchronizes time.
  - **Example**: Aligning server clocks.
  - **Details**: Uses stratum levels.
- **PTP**: High-precision time sync.
  - **Example**: Financial systems needing microsecond accuracy.
  - **Details**: More precise than NTP.
- **NTS**: Secures time sync.
  - **Example**: Protecting NTP from attacks.
  - **Details**: Uses encryption.

**Example**: A network uses DHCP for IPs and DNS for website access.

**Homelab Activity**: **Configure DHCP and DNS**
- **Tool**: Packet Tracer.
- **Objective**: Set up a DHCP server and test DNS.
- **Steps**:
  1. Add a router, switch, and two PCs in Packet Tracer.
  2. Configure router as DHCP server: `ip dhcp pool LAN`, `network 192.168.1.0 255.255.255.0`, `default-router 192.168.1.1`.
  3. Set PCs to obtain IPs via DHCP.
  4. Simulate DNS: On router, add `ip host example.com 192.168.1.100`.
  5. Ping “example.com” from a PC to verify DNS resolution.
- **Why**: Practices DHCP and DNS configuration.[](https://www.howtonetwork.com/courses/comptia/comptia-network-n10-009/)

**Quiz**:
1. What’s DHCP’s job? (Answer: Assign IPs)
2. What does DNS do? (Answer: Resolves domain names)

## Access and Management 🔐
Methods for network management.

- **VPNs**: Secure remote access.
  - **Example**: Remote employee access.
  - **Details**: Uses IPsec or OpenVPN.
- **SSH**: Secure command-line access.
  - **Example**: Configuring a router remotely.
  - **Details**: Encrypts sessions.
- **GUI**: Graphical management tools.
  - **Example**: Web-based router interface.
  - **Details**: Simplifies configuration.
- **API**: Automates tasks.
  - **Example**: Scripting switch configurations.
  - **Details**: Integrates with automation tools.
- **Console**: Direct device access.
  - **Example**: Serial port switch connection.
  - **Details**: Used for initial setup.

**Example**: An admin uses SSH for router configuration and a GUI for monitoring.

**Homelab Activity**: **Set Up SSH Access**
- **Tool**: Packet Tracer.
- **Objective**: Configure SSH on a router.
- **Steps**:
  1. Add a router and a PC in Packet Tracer.
  2. Configure router: `hostname R1`, `ip domain-name example.com`, `crypto key generate rsa` (1024 bits).
  3. Enable SSH: `line vty 0 4`, `transport input ssh`, `login local`.
  4. Create user: `username admin password Secure123`.
  5. From PC, use SSH client (e.g., PuTTY in Packet Tracer) to connect to router’s IP.
- **Why**: Practices secure remote access.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s SSH used for? (Answer: Secure remote access)
2. What’s a GUI’s benefit? (Answer: Simplifies management)
