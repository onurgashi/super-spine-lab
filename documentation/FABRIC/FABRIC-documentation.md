# FABRIC

## Table of Contents

- [FABRIC](#fabric)
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

| POD | Type | Node | Management IP | Platform | Provisioned in Cloudvision |
| --- | ---- | ---- | ------------- | -------- | -------------------------- |
| POD01 | l3leaf | POD01-LEAF1A | 192.168.1.5/24 | vEOS-LAB | Provisioned |
| POD01 | l3leaf | POD01-LEAF1B | 192.168.1.6/24 | vEOS-LAB | Provisioned |
| POD01 | l3leaf | POD01-LEAF2A | 192.168.1.7/24 | vEOS-LAB | Provisioned |
| POD01 | l3leaf | POD01-LEAF2B | 192.168.1.8/24 | vEOS-LAB | Provisioned |
| POD01 | spine | POD01-SPINE1 | 192.168.1.3/24 | vEOS-LAB | Provisioned |
| POD01 | spine | POD01-SPINE2 | 192.168.1.4/24 | vEOS-LAB | Provisioned |
| POD01 | l2leaf | POD01-SUBLEAF1A | 192.168.1.9/24 | vEOS-LAB | Provisioned |
| POD02 | l3leaf | POD02-LEAF3A | 192.168.1.13/24 | vEOS-LAB | Provisioned |
| POD02 | l3leaf | POD02-LEAF3B | 192.168.1.14/24 | vEOS-LAB | Provisioned |
| POD02 | l3leaf | POD02-LEAF4A | 192.168.1.15/24 | vEOS-LAB | Provisioned |
| POD02 | spine | POD02-SPINE3 | 192.168.1.11/24 | vEOS-LAB | Provisioned |
| POD02 | spine | POD02-SPINE4 | 192.168.1.12/24 | vEOS-LAB | Provisioned |
| POD02 | l2leaf | POD02-SUBLEAF2A | 192.168.1.16/24 | vEOS-LAB | Provisioned |
| DC | overlay-controller | ROUTE-SERVER1 | 192.168.1.10/24 | vEOS-LAB | Provisioned |
| DC | super-spine | SUPER-SPINE1 | 192.168.1.1/24 | vEOS-LAB | Provisioned |
| DC | super-spine | SUPER-SPINE2 | 192.168.1.2/24 | vEOS-LAB | Provisioned |

> Provision status is based on Ansible inventory declaration and do not represent real status from Cloudvision.

## Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |
| l3leaf | POD01-LEAF1A | Ethernet1 | spine | POD01-SPINE1 | Ethernet3 |
| l3leaf | POD01-LEAF1A | Ethernet2 | spine | POD01-SPINE2 | Ethernet3 |
| l3leaf | POD01-LEAF1A | Ethernet3 | mlag_peer | POD01-LEAF1B | Ethernet3 |
| l3leaf | POD01-LEAF1A | Ethernet4 | l2leaf | POD01-SUBLEAF1A | Ethernet1 |
| l3leaf | POD01-LEAF1B | Ethernet1 | spine | POD01-SPINE1 | Ethernet4 |
| l3leaf | POD01-LEAF1B | Ethernet2 | spine | POD01-SPINE2 | Ethernet4 |
| l3leaf | POD01-LEAF1B | Ethernet4 | l2leaf | POD01-SUBLEAF1A | Ethernet2 |
| l3leaf | POD01-LEAF2A | Ethernet1 | spine | POD01-SPINE1 | Ethernet5 |
| l3leaf | POD01-LEAF2A | Ethernet2 | spine | POD01-SPINE2 | Ethernet5 |
| l3leaf | POD01-LEAF2A | Ethernet3 | mlag_peer | POD01-LEAF2B | Ethernet3 |
| l3leaf | POD01-LEAF2B | Ethernet1 | spine | POD01-SPINE1 | Ethernet6 |
| l3leaf | POD01-LEAF2B | Ethernet2 | spine | POD01-SPINE2 | Ethernet6 |
| spine | POD01-SPINE1 | Ethernet1 | super-spine | SUPER-SPINE1 | Ethernet1 |
| spine | POD01-SPINE1 | Ethernet2 | super-spine | SUPER-SPINE2 | Ethernet1 |
| spine | POD01-SPINE2 | Ethernet1 | super-spine | SUPER-SPINE1 | Ethernet2 |
| spine | POD01-SPINE2 | Ethernet2 | super-spine | SUPER-SPINE2 | Ethernet2 |
| l3leaf | POD02-LEAF3A | Ethernet1 | spine | POD02-SPINE3 | Ethernet3 |
| l3leaf | POD02-LEAF3A | Ethernet2 | spine | POD02-SPINE4 | Ethernet3 |
| l3leaf | POD02-LEAF3A | Ethernet3 | mlag_peer | POD02-LEAF3B | Ethernet3 |
| l3leaf | POD02-LEAF3A | Ethernet4 | l2leaf | POD02-SUBLEAF2A | Ethernet1 |
| l3leaf | POD02-LEAF3B | Ethernet1 | spine | POD02-SPINE3 | Ethernet4 |
| l3leaf | POD02-LEAF3B | Ethernet2 | spine | POD02-SPINE4 | Ethernet4 |
| l3leaf | POD02-LEAF3B | Ethernet4 | l2leaf | POD02-SUBLEAF2A | Ethernet2 |
| l3leaf | POD02-LEAF4A | Ethernet1 | spine | POD02-SPINE3 | Ethernet5 |
| l3leaf | POD02-LEAF4A | Ethernet2 | spine | POD02-SPINE4 | Ethernet5 |
| spine | POD02-SPINE3 | Ethernet1 | super-spine | SUPER-SPINE1 | Ethernet3 |
| spine | POD02-SPINE3 | Ethernet2 | super-spine | SUPER-SPINE2 | Ethernet3 |
| spine | POD02-SPINE4 | Ethernet1 | super-spine | SUPER-SPINE1 | Ethernet4 |
| spine | POD02-SPINE4 | Ethernet2 | super-spine | SUPER-SPINE2 | Ethernet4 |
| overlay-controller | ROUTE-SERVER1 | Ethernet1 | l3leaf | POD01-LEAF2A | Ethernet4 |
| overlay-controller | ROUTE-SERVER1 | Ethernet2 | l3leaf | POD01-LEAF2B | Ethernet4 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| P2P Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ----------- | ------------------- | ------------------ | ------------------ |
| 10.0.1.0/24 | 256 | 4 | 1.57 % |
| 10.0.2.0/24 | 256 | 4 | 1.57 % |
| 10.0.3.0/24 | 256 | 16 | 6.25 % |
| 10.0.4.0/24 | 256 | 12 | 4.69 % |
| 10.0.11.0/24 | 256 | 4 | 1.57 % |

### Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |
| POD01-LEAF1A | Ethernet1 | 10.0.3.1/31 | POD01-SPINE1 | Ethernet3 | 10.0.3.0/31 |
| POD01-LEAF1A | Ethernet2 | 10.0.3.3/31 | POD01-SPINE2 | Ethernet3 | 10.0.3.2/31 |
| POD01-LEAF1B | Ethernet1 | 10.0.3.5/31 | POD01-SPINE1 | Ethernet4 | 10.0.3.4/31 |
| POD01-LEAF1B | Ethernet2 | 10.0.3.7/31 | POD01-SPINE2 | Ethernet4 | 10.0.3.6/31 |
| POD01-LEAF2A | Ethernet1 | 10.0.3.9/31 | POD01-SPINE1 | Ethernet5 | 10.0.3.8/31 |
| POD01-LEAF2A | Ethernet2 | 10.0.3.11/31 | POD01-SPINE2 | Ethernet5 | 10.0.3.10/31 |
| POD01-LEAF2B | Ethernet1 | 10.0.3.13/31 | POD01-SPINE1 | Ethernet6 | 10.0.3.12/31 |
| POD01-LEAF2B | Ethernet2 | 10.0.3.15/31 | POD01-SPINE2 | Ethernet6 | 10.0.3.14/31 |
| POD02-LEAF3A | Ethernet1 | 10.0.4.1/31 | POD02-SPINE3 | Ethernet3 | 10.0.4.0/31 |
| POD02-LEAF3A | Ethernet2 | 10.0.4.3/31 | POD02-SPINE4 | Ethernet3 | 10.0.4.2/31 |
| POD02-LEAF3B | Ethernet1 | 10.0.4.5/31 | POD02-SPINE3 | Ethernet4 | 10.0.4.4/31 |
| POD02-LEAF3B | Ethernet2 | 10.0.4.7/31 | POD02-SPINE4 | Ethernet4 | 10.0.4.6/31 |
| POD02-LEAF4A | Ethernet1 | 10.0.4.9/31 | POD02-SPINE3 | Ethernet5 | 10.0.4.8/31 |
| POD02-LEAF4A | Ethernet2 | 10.0.4.11/31 | POD02-SPINE4 | Ethernet5 | 10.0.4.10/31 |
| ROUTE-SERVER1 | Ethernet1 | 10.0.2.1/31 | POD01-LEAF2A | Ethernet4 | 10.0.2.0/31 |
| ROUTE-SERVER1 | Ethernet2 | 10.0.2.3/31 | POD01-LEAF2B | Ethernet4 | 10.0.2.2/31 |

### Overlay Loopback Interfaces (BGP EVPN Peering)

| Overlay Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------------ | ------------------- | ------------------ | ------------------ |
| 10.1.1.0/24 | 256 | 2 | 0.79 % |
| 10.1.2.0/24 | 256 | 6 | 2.35 % |
| 10.1.3.0/24 | 256 | 5 | 1.96 % |
| 10.11.33.0/24 | 256 | 1 | 0.4 % |

### Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| POD01 | POD01-LEAF1A | 10.1.2.3/32 |
| POD01 | POD01-LEAF1B | 10.1.2.4/32 |
| POD01 | POD01-LEAF2A | 10.1.2.5/32 |
| POD01 | POD01-LEAF2B | 10.1.2.6/32 |
| POD01 | POD01-SPINE1 | 10.1.2.1/32 |
| POD01 | POD01-SPINE2 | 10.1.2.2/32 |
| POD02 | POD02-LEAF3A | 10.1.3.3/32 |
| POD02 | POD02-LEAF3B | 10.1.3.4/32 |
| POD02 | POD02-LEAF4A | 10.1.3.5/32 |
| POD02 | POD02-SPINE3 | 10.1.3.1/32 |
| POD02 | POD02-SPINE4 | 10.1.3.2/32 |
| DC | ROUTE-SERVER1 | 10.11.33.1/32 |
| DC | SUPER-SPINE1 | 10.1.1.1/32 |
| DC | SUPER-SPINE2 | 10.1.1.2/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)

| VTEP Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 10.1.5.0/24 | 256 | 4 | 1.57 % |
| 10.1.6.0/24 | 256 | 3 | 1.18 % |

### VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
| POD01 | POD01-LEAF1A | 10.1.5.3/32 |
| POD01 | POD01-LEAF1B | 10.1.5.3/32 |
| POD01 | POD01-LEAF2A | 10.1.5.5/32 |
| POD01 | POD01-LEAF2B | 10.1.5.5/32 |
| POD02 | POD02-LEAF3A | 10.1.6.3/32 |
| POD02 | POD02-LEAF3B | 10.1.6.3/32 |
| POD02 | POD02-LEAF4A | 10.1.6.5/32 |
