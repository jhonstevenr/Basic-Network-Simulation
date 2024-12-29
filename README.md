# Basic Network Simulation with Packet Tracer

## Overview
This project demonstrates the setup of a simple network using Cisco Packet Tracer. The network consists of a router and two end devices (PCs), showcasing basic IP configuration and connectivity testing using `ping`.

---

## Objectives
1. Configure a network with two PCs connected to a router.
2. Assign IP addresses to the devices and router interfaces.
3. Test connectivity between devices using the `ping` command.

---

## Network Topology
- **Devices:**
  - 1 Router (Cisco 1941 series)
  - 2 PCs (End devices)
- **Connections:**
  - Router GigabitEthernet0/0 → PC-PT PC0
  - Router GigabitEthernet0/1 → Laptop-PT Laptop0

---

## Configuration Details

### IP Addressing Plan
| **Device/Interface**   | **IP Address**   | **Subnet Mask**     | **Default Gateway**   |
|-------------------------|------------------|----------------------|------------------------|
| Router GigabitEthernet0/0 | 192.168.1.1      | 255.255.255.0        | N/A                    |
| Router GigabitEthernet0/1 | 192.168.2.1      | 255.255.255.0        | N/A                    |
| PC-PT PC0                 | 192.168.1.2      | 255.255.255.0        | 192.168.1.1            |
| Laptop-PT Laptop0         | 192.168.2.2      | 255.255.255.0        | 192.168.2.1            |

---

## Steps to Recreate

### 1. Setup the Topology
- Drag and drop the following devices into the workspace:
  - 1 Router (Cisco 1941 series)
  - 2 PCs (End devices)
- Connect the devices using **Copper Straight-Through Cables**:
  - Router GigabitEthernet0/0 → PC-PT PC0 FastEthernet0
  - Router GigabitEthernet0/1 → Laptop-PT Laptop0 FastEthernet0

### 2. Configure the Router
Access the CLI of the router and configure IP addresses on its interfaces:
```bash
Router> enable
Router# configure terminal
Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface gigabitEthernet 0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
