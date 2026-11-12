# Enterprise Network Segmentation – Cisco Packet Tracer

A multi-department enterprise networking lab built with Cisco Packet Tracer, demonstrating VLAN segmentation, inter-VLAN routing, DHCP, OSPF dynamic routing and Access Control Lists (ACLs).

## Project Overview

This project simulates an enterprise network with four departments:

- Human Resources (HR)
- Sales
- Production
- Quality Assurance (QA)

Each department operates in a separate VLAN and IP subnet. Two Cisco 2911 routers provide routing between the departmental networks using OSPF.

The project focuses on network design, configuration, troubleshooting, segmentation and network security.

## Network Topology

![Network Topology](Screenshots/Network%20Topology.png)

*The complete Packet Tracer topology.*

## Network Components

| Component | Quantity |
|---|---:|
| Cisco 2911 Routers | 2 |
| Cisco 2960 Switches | 4 |
| Departmental VLANs | 4 |
| End Devices | 8 |

## IP Addressing and VLAN Design

| Department | VLAN | Network | Default Gateway |
|---|---:|---|---|
| HR | 10 | 192.168.10.0/26 | 192.168.10.1 |
| Sales | 20 | 192.168.10.64/26 | 192.168.10.65 |
| Production | 30 | 192.168.10.128/26 | 192.168.10.129 |
| QA | 40 | 192.168.10.192/26 | 192.168.10.193 |

**Router-to-router network:** `192.168.99.0/30`

## Technologies and Protocols

- Cisco Packet Tracer
- VLAN configuration and network segmentation
- IEEE 802.1Q trunking
- Router-on-a-stick inter-VLAN routing
- DHCP configuration and automatic IP allocation
- OSPF dynamic routing
- Extended Access Control Lists (ACLs)
- SSH-based device management
- Switch port security
- Spanning Tree security features
- Cisco IOS command-line configuration

## Network Design Objectives

1. Separate departmental networks using VLANs.
2. Configure automatic IP address allocation through DHCP.
3. Enable communication between routers using OSPF.
4. Restrict unauthorized communication between departments using ACLs.
5. Implement secure network device management and switch security controls.
6. Design the network to support authorized access to a centralized Data Warehouse as a planned enhancement.

## Security Implementation

The project implements departmental traffic isolation through extended ACLs.

Additional security measures include:

- SSH-based network device management
- Switch port security
- Disabling unused switch ports
- Spanning Tree PortFast and BPDU Guard
- DHCP snooping, where supported
- OSPF authentication, where supported

## Implementation Status

- [x] Four departmental VLANs
- [x] Router-on-a-stick configuration
- [x] DHCP configuration
- [x] Two-router topology
- [x] OSPF neighbor adjacency and route exchange
- [x] Departmental isolation using ACLs
- [x] SSH-based network device management
- [x] Additional security hardening and verification
- [ ] Data Warehouse connectivity

## Testing and Verification

The following Cisco IOS commands are used to verify network operation:

| Command | Purpose |
|---|---|
| `show vlan brief` | Verify VLAN assignments |
| `show interfaces trunk` | Verify trunk configuration |
| `show ip interface brief` | Check interface status |
| `show ip dhcp binding` | Verify DHCP leases |
| `show ip ospf neighbor` | Verify OSPF adjacency |
| `show ip route` | Inspect routing table |
| `show access-lists` | Inspect ACL rules |
| `show port-security` | Verify switch port security |

### Verification Screenshots

**DHCP Binding**

![DHCP Binding](Screenshots/DHCP%20Binding.png)

**OSPF Neighbor Adjacency**

![OSPF Neighbor](Screenshots/OSPF%20Neighbor.png)

## Repository Structure
```text
enterprise-network-segmentation-packet-tracer/
├── Config/
│   ├── R1-config.txt
│   ├── R2-config.txt
│   ├── Sw-HR-config.txt
│   ├── Sw-Production-config.txt
│   ├── Sw-QA-config.txt
│   └── Sw-Sales-config.txt
├── Screenshots/
│   ├── Network Topology.png
│   ├── DHCP Binding.png
│   ├── OSPF Neighbor.png
│   └── .gitkeep
├── ciscoproject.pkt
└── README.md
```

## Tools

- Cisco Packet Tracer
- Cisco IOS CLI
- Networking fundamentals: VLANs, DHCP, OSPF, ACLs and routing

## Disclaimer

This is a simulated networking lab developed using Cisco Packet Tracer. It demonstrates practical networking concepts and configuration skills in an educational environment. It is not a live enterprise deployment.
