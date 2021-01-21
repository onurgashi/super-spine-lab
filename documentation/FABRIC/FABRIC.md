# FABRIC

## Table of Contents

- [FABRIC](#fabric )
  - [Spine, Super-Spine Switches and Overlay Controller Management IP](#spine-super-spine-switches-and-overlay-controller-management-ip)
  - [Super Spine and Overlay Controller Fabric Topology](#super-spine-and-overlay-controller-fabric-topology)
  - [Super Spine Fabric IP Allocation](#super-spine-fabric-ip-allocation)
    - [Super Spine Fabric Point-To-Point Links](#super-spine-fabric-point-to-point-links)
    - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
    - [Super Spine Overlay Loopback Interfaces (BGP EVPN Peering, if required)](#super-spine-overlay-loopback-interfaces-bgp-evpn-peering-if-required)
    - [Loopback0 Interfaces To Super Spine Node Allocation](#loopback0-interfaces-to-super-spine-node-allocation)
  - [Overlay Controller IP Allocation](#overlay-controller-ip-allocation)
    - [Overlay Controller Point-To-Point Links](#overlay-controller-point-to-point-links)
    - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
    - [Overlay Controller Loopback Interfaces (BGP EVPN Peering, if required)](#overlay-controller-loopback-interfaces-bgp-evpn-peering-if-required)
    - [Loopback0 Interfaces To Overlay Controller Node Allocation](#loopback0-interfaces-to-overlay-controller-node-allocation)

## Spine, Super-Spine Switches and Overlay Controller Management IP

| Node | Management IP | Platform |
| ---- | ------------- | -------- |
| SUPER-SPINE1 | 192.168.1.1/24 | vEOS-LAB |
| SUPER-SPINE2 | 192.168.1.2/24 | vEOS-LAB |
| POD01-SPINE1 | 192.168.1.3/24 | vEOS-LAB |
| POD01-SPINE2 | 192.168.1.4/24 | vEOS-LAB |
| ROUTE-SERVER1 | 192.168.1.10/24 | vEOS-LAB |

## Super Spine and Overlay Controller Fabric Topology

| Type | Node | Interface | Peer Node | Peer Interface |
| ---- | --------- | -------------- | --------- | -------------- |
| super-spine | SUPER-SPINE1 | Ethernet1 | POD01-SPINE1 | Ethernet1 |
| super-spine | SUPER-SPINE1 | Ethernet2 | POD01-SPINE2 | Ethernet1 |
| super-spine | SUPER-SPINE2 | Ethernet1 | POD01-SPINE1 | Ethernet2 |
| super-spine | SUPER-SPINE2 | Ethernet2 | POD01-SPINE2 | Ethernet2 |
| overlay-controller | ROUTE-SERVER1 | Ethernet1 | POD01-LEAF2A | Ethernet4 |
| overlay-controller | ROUTE-SERVER1 | Ethernet2 | POD01-LEAF2B | Ethernet4 |

## Super Spine Fabric IP Allocation

### Super Spine Fabric Point-To-Point Links

| POD Number | P2P Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ----------- | ----------- | ------------------- | ------------------ | ------------------ |
| 1 | 10.0.1.0/24 | 256 | 8 | 3.13 % |

### Point-To-Point Links Node Allocation

| Super-Spine Node | Super-Spine Interface | Super-Spine IP Address | Spine Node | Spine Interface | Spine IP Address |
| --------- | -------------- | --------------- | ---------- | --------------- | ---------------- |
| SUPER-SPINE1 | Ethernet1 | 10.0.1.0/31| POD01-SPINE1| Ethernet1 | 10.0.1.1/31 |
| SUPER-SPINE1 | Ethernet2 | 10.0.1.2/31| POD01-SPINE2| Ethernet1 | 10.0.1.3/31 |
| SUPER-SPINE2 | Ethernet1 | 10.0.1.64/31| POD01-SPINE1| Ethernet2 | 10.0.1.65/31 |
| SUPER-SPINE2 | Ethernet2 | 10.0.1.66/31| POD01-SPINE2| Ethernet2 | 10.0.1.67/31 |

### Super Spine Overlay Loopback Interfaces (BGP EVPN Peering, if required)

| Overlay Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------------ | ------------------- | ------------------ | ------------------ |
| 10.1.1.0/24 | 256 | 2 | 0.79 % |

### Loopback0 Interfaces to Super Spine Node Allocation

| Node | Loopback0 |
| ---- | --------- |
| SUPER-SPINE1 | 10.1.1.1/32 |
| SUPER-SPINE2 | 10.1.1.2/32 |
| POD01-SPINE1 | 10.1.2.1/32 |
| POD01-SPINE2 | 10.1.2.2/32 |

## Overlay Controller IP Allocation

### Overlay Controller Point-To-Point Links

| P2P Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ----------- | ------------------- | ------------------ | ------------------ |
| 10.0.2.0/24 | 256 | 4 | 1.57 % |

### Point-To-Point Links Node Allocation

| Overlay-Controller Node | Overlay-Controller Interface | Overlay-Controller IP Address | Node | Interface | IP Address |
| ----------------------- | ---------------------------- | ----------------------------- | ---- | --------- | ---------- |
| ROUTE-SERVER1 | Ethernet1 | 10.0.2.1/31| POD01-LEAF2A| Ethernet4 | 10.0.2.0/31 |
| ROUTE-SERVER1 | Ethernet2 | 10.0.2.3/31| POD01-LEAF2B| Ethernet4 | 10.0.2.2/31 |

### Overlay Controller Loopback Interfaces (BGP EVPN Peering, if required)

| Overlay Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------------ | ------------------- | ------------------ | ------------------ |
| 10.1.3.0/24 | 256 | 1 | 0.4 % |

### Loopback0 Interfaces to Overlay Controller Node Allocation

| Node | Loopback0 |
| ---- | --------- |
| ROUTE-SERVER1 | 10.1.3.1/32 |
