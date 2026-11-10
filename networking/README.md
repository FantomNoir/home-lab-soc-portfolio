
# Networking Lab

## Purpose
Document practical networking exercises and configurations.

## Learning Objectives
- Understand IP addressing and subnetting
- Configure and understand network gateways
- Learn DNS and DHCP
- Understand VLANs
- Practice network troubleshooting
- Learn packet analysis with Wireshark

## Lab Environment
- MacBook M2
- macOS
- Existing ISP-provided router
- Cisco Packet Tracer (planned)

## Exercises
- [ ] Identify my local IP address
- [ ] Identify my default gateway
- [ ] Understand DNS resolution
- [ ] Practice subnetting
- [ ] Build a basic network topology

## Notes
This folder will contain networking notes, diagrams, configurations, and lab results.

## Lab 1 - Local Network Discovery

Objective: Identify my local IP address, subnet mask,
default gateway, and DNS configuration.

Tools Used:
- macOS Terminal
- ifconfig
- ipconfig
- route
- scutil

Skills Practiced:
- IPv4 addressing
- Subnet identification
- Network discovery
- Basic network troubleshooting

## Lab 2 - Network Connectivity Testing

### Objective
Validate local connectivity, external IP reachability,
DNS resolution, and network routing.

### Tools Used
- ping
- nslookup
- traceroute

### Test Results
- Local gateway: 4/4 replies, 0% loss, 6.254 ms average.
- External IP: 4/4 replies, 0% loss, 20.578 ms average.
- DNS: Successfully resolved google.com.
- Traceroute: Destination responded at hop 12.

### Findings
Local and external connectivity were successful.
DNS resolution worked. Some intermediate traceroute
probes timed out, but the destination responded.

### SOC Relevance
These tools help investigate endpoint connectivity,
DNS failures, and routing problems during triage.
