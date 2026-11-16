# IPv6 Inter-VLAN Routing Using Cisco Multilayer Switch

## 📌 Project Overview

This project demonstrates IPv6 Inter-VLAN Routing using a Cisco Multilayer Switch (Core MLS) in Cisco Packet Tracer.

The network is designed to separate Faculty and Student departments into different VLANs while allowing communication between them through Layer 3 switching.

Three access switches are connected to a central Core Multilayer Switch using IEEE 802.1Q trunk links.

## 🖥️ Network Topology

**Network Devices:**
- 1 Cisco Multilayer Switch (Core_MLS)
- 3 Cisco 2960 Access Switches (S1, S2, S3)
- 6 End Devices (3 Faculty PCs and 3 Student PCs)

## 🔧 VLAN Configuration

| VLAN ID | VLAN Name | Purpose |
|---|---|---|
| 10 | Faculty | Faculty department |
| 20 | Student | Student department |
| 90 | Native | Native VLAN for trunk links |
| 100 | Unused | Unused switch ports |

## 🌐 IPv6 Addressing Scheme

| Device | IPv6 Address | Default Gateway |
|---|---|---|
| Faculty1 | 2001:DB8:ACAD:10::2/64 | FE80::1 |
| Faculty2 | 2001:DB8:ACAD:10::3/64 | FE80::1 |
| Faculty3 | 2001:DB8:ACAD:10::4/64 | FE80::1 |
| Student1 | 2001:DB8:ACAD:20::2/64 | FE80::2 |
| Student2 | 2001:DB8:ACAD:20::3/64 | FE80::2 |
| Student3 | 2001:DB8:ACAD:20::4/64 | FE80::2 |

### Core Multilayer Switch IPv6 Gateways

| VLAN | IPv6 Address |
|---|---|
| VLAN 10 | 2001:DB8:ACAD:10::1/64 |
| VLAN 10 Link-Local | FE80::1 |
| VLAN 20 | 2001:DB8:ACAD:20::1/64 |
| VLAN 20 Link-Local | FE80::2 |

## ⚙️ Key Configurations

### 1. VLAN Creation
Created VLANs 10, 20, 90 and 100 on the Core MLS and all access switches.

### 2. Trunk Configuration
Configured IEEE 802.1Q trunk links between the Core MLS and access switches.

- Native VLAN: 90
- Allowed VLANs: 10, 20, 90

### 3. IPv6 Routing
Enabled IPv6 routing on the Core Multilayer Switch:

```cisco
ipv6 unicast-routing
```

### 4. SVI Configuration
Configured Switched Virtual Interfaces (SVIs) for VLAN 10 and VLAN 20 to provide IPv6 default gateways.

### 5. Access Port Configuration
Assigned end-device ports to the appropriate VLANs:
- Faculty PCs → VLAN 10
- Student PCs → VLAN 20

### 6. Unused Port Security
Assigned unused access-switch ports to VLAN 100 and administratively shut them down.

## 🧪 Verification Commands

The following commands can be used to verify the network configuration:

```cisco
show vlan brief
show interfaces trunk
show ipv6 interface brief
show running-config
show sdm prefer
```

Use the following commands from the PCs to test connectivity:

```text
ping 2001:DB8:ACAD:10::2
ping 2001:DB8:ACAD:20::2
```

Test communication between Faculty and Student VLANs to verify inter-VLAN routing.

## 🎯 Skills Demonstrated

- Cisco Packet Tracer
- IPv6 Addressing and Configuration
- VLAN Creation and Management
- Inter-VLAN Routing
- Layer 3 Switching
- IEEE 802.1Q Trunking
- Native VLAN Configuration
- Switch Port Security Practices
- Network Troubleshooting

## 📚 Learning Outcomes

Through this project, I gained practical experience in configuring IPv6-based networks, implementing VLAN segmentation, configuring trunk links, and enabling communication between different VLANs using a Cisco Multilayer Switch.

## 🛠️ Software Used

- Cisco Packet Tracer
- Cisco IOS CLI

## 👨‍💻 Project Type

Networking Lab Project | IPv6 | Cisco Switching | Inter-VLAN Routing
