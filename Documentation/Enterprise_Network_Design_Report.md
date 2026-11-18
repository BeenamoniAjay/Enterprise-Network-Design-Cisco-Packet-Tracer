# Enterprise Network Design – Cisco Packet Tracer

## 1. Project Overview

This project demonstrates the design and implementation of a multi-branch enterprise network using Cisco Packet Tracer.

The network connects a Hyderabad Head Office with branch offices in Chennai and Bangalore through an ISP network.

**Project objectives:**
- Design a multi-branch enterprise network.
- Configure routing and switching.
- Implement VLANs and inter-VLAN communication.
- Configure centralized DHCP services.
- Implement NAT/PAT for external connectivity.
- Apply access control and secure remote management.
- Verify network connectivity and configurations.

## 2. Network Topology

The simulated network contains:

- Hyderabad Head Office
- Chennai Branch Office
- Bangalore Branch Office
- ISP Network

### Devices Used

| Device | Quantity |
|---|---:|
| Cisco 2911 Routers | 4 |
| Cisco 2960 Switches | 4 |
| PCs | 8 |
| Server-PT | 1 |

## 3. Technologies Implemented

### Switching
- VLAN configuration
- Access and trunk ports
- 802.1Q trunking
- Inter-VLAN routing
- Layer 2 and Layer 3 networking concepts

### Routing
- Static routing concepts
- OSPF dynamic routing
- OSPF area 0
- Routing table verification

### Network Services
- DHCP server configuration
- DHCP relay using `ip helper-address`
- NAT and PAT configuration
- ISP connectivity using a default route

### Network Security
- Standard and extended ACL concepts
- Traffic filtering between departments
- SSH remote management
- Router password protection

### Network Administration
- Router and switch configuration
- Interface status verification
- Connectivity testing
- Configuration verification using Cisco IOS commands

## 4. IP Addressing Plan

### WAN Links

| Connection | Network | IP Addresses |
|---|---|---|
| Hyderabad–Chennai | 10.0.12.0/30 | 10.0.12.1, 10.0.12.2 |
| Hyderabad–Bangalore | 10.0.13.0/30 | 10.0.13.1, 10.0.13.2 |
| Hyderabad–ISP | 203.0.113.0/30 | 203.0.113.2, 203.0.113.1 |

### Hyderabad VLANs

| VLAN | Department | Network | Gateway |
|---|---|---|---|
| 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Finance | 192.168.30.0/24 | 192.168.30.1 |
| 40 | Servers | 192.168.40.0/24 | 192.168.40.1 |

### Branch Networks

| Location | Network | Gateway |
|---|---|---|
| Chennai | 192.168.100.0/24 | 192.168.100.1 |
| Bangalore | 192.168.200.0/24 | 192.168.200.1 |

### Server

- IP address: 192.168.40.10
- Subnet mask: 255.255.255.0
- Default gateway: 192.168.40.1

## 5. Routing Configuration

OSPF was configured to provide dynamic routing between the Hyderabad Head Office and branch networks.

The OSPF configuration uses:
- Process ID: 1
- Area: 0
- Hyderabad router ID: 1.1.1.1
- Chennai router ID: 2.2.2.2
- Bangalore router ID: 3.3.3.3

The routing table was checked using:

```text
show ip route
```

The Hyderabad routing table displayed OSPF routes to the Chennai and Bangalore networks.

## 6. DHCP Configuration

The central server was configured to provide dynamic IP addresses to client devices.

DHCP pools were created for:
- Hyderabad HR
- Hyderabad IT
- Hyderabad Finance
- Chennai Branch
- Bangalore Branch

