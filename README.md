# 🏦 Secure Bank Branch Network

A centralized, secure, and scalable banking network designed and simulated using **Cisco Packet Tracer**. This project connects one Head Office with five bank branches, implementing VLAN segmentation, dynamic routing, centralized network services, and access control mechanisms to ensure secure communication across the organization.

---

## 📌 Project Overview

The Secure Bank Branch Network is designed to establish reliable communication between a central Head Office and five geographically distributed bank branches.

The network uses VLANs to logically separate departments, OSPF for dynamic routing, DHCP for automatic IP configuration, and DNS for centralized domain name resolution. Extended Access Control Lists (ACLs) enforce communication policies between departments and branches.

Additional security mechanisms, including Switch Port Security and SSH, help protect network access and administrative management.

### 🎯 Project Objectives

- Establish connectivity between the Head Office and five branches.
- Implement VLAN-based network segmentation.
- Configure inter-VLAN routing using Router-on-a-Stick.
- Automate IP address assignment using DHCP.
- Implement centralized DNS services.
- Enable dynamic routing using OSPF.
- Restrict unauthorized communication using Extended ACLs.
- Secure switch ports using MAC address-based Port Security.
- Enable encrypted remote device management using SSH.

---

## 🏗️ Network Architecture

The network consists of six major locations:

1. Head Office
2. Branch 01
3. Branch 02
4. Branch 03
5. Branch 04
6. Branch 05

The Head Office acts as the centralized network location, hosting the main server and providing centralized services to authorized users across the branches.

Each branch maintains separate VLANs for Staff, ATM, and Guest users.

### Network Topology

The network uses routers to connect different locations and switches to connect end devices within each location.

**Major Components:**

| Component | Purpose |
|---|---|
| Routers | Inter-network and branch connectivity |
| Switches | Local device connectivity |
| PCs | Staff, Admin, IT, and Guest users |
| Bank Server | Centralized server and DNS services |
| WAN Links | Communication between locations |

---

## 🌐 IP Addressing Scheme

### Head Office VLAN Configuration

| VLAN ID | Department | Network Address | Default Gateway |
|---|---|---|---|
| 10 | Admin | 192.168.10.0/24 | 192.168.10.1 |
| 20 | Employee | 192.168.20.0/24 | 192.168.20.1 |
| 30 | IT Management | 192.168.30.0/24 | 192.168.30.1 |
| 40 | Server | 192.168.40.0/24 | 192.168.40.1 |

### Branch VLAN Configuration

Each branch uses three VLANs:

- VLAN 10 – Staff
- VLAN 20 – ATM
- VLAN 30 – Guest

| Branch | Staff Network | ATM Network | Guest Network |
|---|---|---|---|
| Branch 01 | 192.168.50.0/24 | 192.168.60.0/24 | 192.168.70.0/24 |
| Branch 02 | 192.168.80.0/24 | 192.168.90.0/24 | 192.168.100.0/24 |
| Branch 03 | 192.168.110.0/24 | 192.168.120.0/24 | 192.168.130.0/24 |
| Branch 04 | 192.168.140.0/24 | 192.168.150.0/24 | 192.168.160.0/24 |
| Branch 05 | 192.168.170.0/24 | 192.168.180.0/24 | 192.168.190.0/24 |

All internal VLANs use a /24 subnet mask.

---

## ⚙️ Technologies and Protocols

| Technology | Implementation |
|---|---|
| Cisco Packet Tracer | Network design and simulation |
| VLAN | Department-based network segmentation |
| IEEE 802.1Q | VLAN tagging and trunking |
| Router-on-a-Stick | Inter-VLAN routing |
| DHCP | Automatic IP configuration |
| DNS | Domain name resolution |
| OSPF | Dynamic routing |
| Extended ACL | Network traffic filtering |
| Port Security | MAC address-based access control |
| SSH | Secure remote administration |
| IPv4 | Network addressing |

---

## 🔧 Key Implementations

### 1. VLAN Segmentation

Separate VLANs are configured for different departments and user groups to improve network organization, reduce broadcast domains, and support security policies.

### 2. Inter-VLAN Routing

Router-on-a-Stick is implemented using router subinterfaces and IEEE 802.1Q encapsulation to enable controlled communication between VLANs.

### 3. DHCP Configuration

DHCP pools are configured to automatically assign:

- IP addresses
- Subnet masks
- Default gateways
- DNS server addresses

This reduces manual configuration and minimizes IP addressing errors.

### 4. Centralized DNS

A centralized DNS service is hosted at the Head Office.

| Parameter | Configuration |
|---|---|
| DNS Server IP | 192.168.40.10 |
| Domain Name | bank.local |
| Server Network | 192.168.40.0/24 |

The DNS server translates domain names into their corresponding IP addresses.

### 5. OSPF Dynamic Routing

OSPF is configured to exchange routing information between the Head Office and branch routers.

**Key features:**
- Automatic route discovery
- Dynamic routing updates
- Shortest-path calculation
- Scalable branch connectivity

### 6. Extended Access Control Lists (ACLs)

Extended ACLs control communication based on source IP, destination IP, protocol, and port number.

The intended access policies include:

- Admin users have authorized access to branch networks.
- Employee users have controlled access to authorized networks.
- ATM users have restricted access to banking services.
- Guest users have limited access to internal resources.
- Access to sensitive Head Office resources is restricted.
- DNS traffic is permitted where required by policy.

ACL rules are applied to appropriate router interfaces and subinterfaces.

### 7. Switch Port Security

Port Security is configured on selected switch access ports.

**Implemented features:**
- MAC address learning using Sticky MAC
- Maximum MAC address limitation
- Violation detection
- Shutdown violation mode

### 8. SSH Remote Management

SSH Version 2 is configured to provide encrypted remote access to routers and switches for authorized administrators.

---

## 🧪 Testing and Verification

The following commands are used to verify network configuration and operation.

| Command | Purpose |
|---|---|
| `show ip interface brief` | Verify interface status and IP addresses |
| `show vlan brief` | Verify VLAN configuration |
| `show interfaces trunk` | Verify trunk configuration |
| `show ip dhcp pool` | Verify DHCP pools |
| `show ip dhcp binding` | Check assigned DHCP leases |
| `show ip route` | Verify routing information |
| `show ip ospf neighbor` | Verify OSPF adjacency |
| `show access-lists` | Inspect ACL rules and counters |
| `show port-security` | Verify switch port security |
| `show running-config` | Inspect device configuration |
| `ping` | Test network reachability |
| `tracert` | Trace packet paths |

### Network Testing Checklist

- [ ] Verify DHCP address assignment in every VLAN.
- [ ] Verify default gateway connectivity.
- [ ] Verify centralized DNS resolution.
- [ ] Verify communication between authorized branches.
- [ ] Verify OSPF neighbor relationships.
- [ ] Verify ACL restrictions.
- [ ] Verify Guest network isolation.
- [ ] Verify Port Security violation handling.
- [ ] Verify SSH remote access.

---

## 📂 Project Structure

```text
Secure-Bank-Branch-Network/
│
├── README.md
│
├── Packet-Tracer/
│   └── Secure-Bank-Branch-Network.pkt
│
├── Documentation/
│   ├── Network-Architecture.pdf
│   ├── IP-Addressing-Table.pdf
│   └── Configuration-Guide.pdf
│
└── Screenshots/
    ├── Network-Topology.png
    ├── VLAN-Configuration.png
    ├── OSPF-Configuration.png
    ├── ACL-Configuration.png
    └── Network-Testing.png
```

*Note: This is a suggested repository structure. Include only the folders and files available in your actual repository.*

---

## 🚀 How to Run the Project

1. Install Cisco Packet Tracer.
2. Clone or download this repository.
3. Navigate to the `Packet-Tracer` directory.
4. Open the `.pkt` file using Cisco Packet Tracer.
5. Wait for network devices and connections to initialize.
6. Inspect router and switch configurations through the CLI.
7. Test connectivity and security policies using the verification commands.

---

## 🔮 Future Improvements

Potential improvements for a more advanced banking infrastructure include:

- Site-to-site VPN connectivity.
- Stateful firewall implementation.
- Intrusion Detection and Prevention Systems (IDS/IPS).
- Redundant network devices and failover mechanisms.
- Centralized network monitoring and logging.
- Server redundancy and disaster recovery.
- Enhanced authentication and access management.

---

## 🎓 Academic Project

**Project Name:** Secure Bank Branch Network  
**Platform:** Cisco Packet Tracer  
**Category:** Computer Networking and Network Security

**Developed by Intasar Mostafiz**

This project demonstrates practical implementation of enterprise networking concepts, dynamic routing, network segmentation, and layered network security using Cisco networking technologies.

---
