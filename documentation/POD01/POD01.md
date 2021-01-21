# POD01

## Table of Contents

- [POD01](#pod01 )
  - [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Topology](#fabric-topology)
  - [Fabric IP Allocation](#fabric-ip-allocation)
    - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
    - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
    - [Overlay Loopback Interfaces (BGP EVPN Peering)](#overlay-loopback-interfaces-bgp-evpn-peering)
    - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
    - [VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-leafs-only)
    - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

## Fabric Switches and Management IP

| Node | Management IP | Platform | Provisioned in Cloudvision |
| ---- | ------------- | -------- | -------------------------- |
| POD01-SPINE1 | 192.168.1.3/24 | vEOS-LAB | Provisioned |
| POD01-SPINE2 | 192.168.1.4/24 | vEOS-LAB | Provisioned |
| POD01-LEAF1A | 192.168.1.5/24 | vEOS-LAB | Provisioned |
| POD01-LEAF1B | 192.168.1.6/24 | vEOS-LAB | Provisioned |
| POD01-LEAF2A | 192.168.1.7/24 | vEOS-LAB | Provisioned |
| POD01-LEAF2B | 192.168.1.8/24 | vEOS-LAB | Provisioned |
| POD01-SUBLEAF1A | 192.168.1.9/24 | vEOS-LAB | Provisioned |

> Provision status is based on Ansible inventory declaration and do not represent real status from Cloudvision.

## Fabric Topology

| Type | Leaf Node | Leaf Interface | Peer Node | Peer Interface |
| ---- | --------- | -------------- | --------- | -------------- |
| L3 Leaf | POD01-LEAF1A | Ethernet1 | POD01-SPINE1 | Ethernet3 |
| L3 Leaf | POD01-LEAF1A | Ethernet2 | POD01-SPINE2 | Ethernet3 |
| L3 Leaf | POD01-LEAF1B | Ethernet1 | POD01-SPINE1 | Ethernet4 |
| L3 Leaf | POD01-LEAF1B | Ethernet2 | POD01-SPINE2 | Ethernet4 |
| L3 Leaf | POD01-LEAF2A | Ethernet1 | POD01-SPINE1 | Ethernet5 |
| L3 Leaf | POD01-LEAF2A | Ethernet2 | POD01-SPINE2 | Ethernet5 |
| L3 Leaf | POD01-LEAF2B | Ethernet1 | POD01-SPINE1 | Ethernet6 |
| L3 Leaf | POD01-LEAF2B | Ethernet2 | POD01-SPINE2 | Ethernet6 |
| L2 Leaf | POD01-SUBLEAF1A | Ethernet1 | POD01-LEAF1A | Ethernet4 |
| L2 Leaf | POD01-SUBLEAF1A | Ethernet2 | POD01-LEAF1B | Ethernet4 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| P2P Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ----------- | ------------------- | ------------------ | ------------------ |
| 10.0.3.0/24 | 256 | 16 | 6.25 % |

### Point-To-Point Links Node Allocation

| Leaf Node | Leaf Interface | Leaf IP Address | Spine Node | Spine Interface | Spine IP Address |
| --------- | -------------- | --------------- | ---------- | --------------- | ---------------- |
| POD01-LEAF1A | Ethernet1 | 10.0.3.1/31 | POD01-SPINE1 | Ethernet3 | 10.0.3.0/31 |
| POD01-LEAF1A | Ethernet2 | 10.0.3.3/31 | POD01-SPINE2 | Ethernet3 | 10.0.3.2/31 |
| POD01-LEAF1B | Ethernet1 | 10.0.3.5/31 | POD01-SPINE1 | Ethernet4 | 10.0.3.4/31 |
| POD01-LEAF1B | Ethernet2 | 10.0.3.7/31 | POD01-SPINE2 | Ethernet4 | 10.0.3.6/31 |
| POD01-LEAF2A | Ethernet1 | 10.0.3.9/31 | POD01-SPINE1 | Ethernet5 | 10.0.3.8/31 |
| POD01-LEAF2A | Ethernet2 | 10.0.3.11/31 | POD01-SPINE2 | Ethernet5 | 10.0.3.10/31 |
| POD01-LEAF2B | Ethernet1 | 10.0.3.13/31 | POD01-SPINE1 | Ethernet6 | 10.0.3.12/31 |
| POD01-LEAF2B | Ethernet2 | 10.0.3.15/31 | POD01-SPINE2 | Ethernet6 | 10.0.3.14/31 |

### Overlay Loopback Interfaces (BGP EVPN Peering)

| Overlay Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------------ | ------------------- | ------------------ | ------------------ |
| 10.1.2.0/24 | 256 | 6 | 2.35 % |

### Loopback0 Interfaces Node Allocation

| Node | Loopback0 |
| ---- | --------- |
| POD01-SPINE1 | 10.1.2.1/32 |
| POD01-SPINE2 | 10.1.2.2/32 |
| POD01-LEAF1A | 10.1.2.3/32 |
| POD01-LEAF1B | 10.1.2.4/32 |
| POD01-LEAF2A | 10.1.2.5/32 |
| POD01-LEAF2B | 10.1.2.6/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)

| VTEP Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 10.1.5.0/24 | 256 | 4 | 1.57 % |

### VTEP Loopback Node allocation

| Node | Loopback1 |
| ---- | --------- |
| POD01-LEAF1A | 10.1.5.3/32 |
| POD01-LEAF1B | 10.1.5.3/32 |
| POD01-LEAF2A | 10.1.5.5/32 |
| POD01-LEAF2B | 10.1.5.5/32 |
