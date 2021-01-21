
# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [Failed Test Results Summary](#failed-test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed |
| ----------- | ------------------ | ------------------ |
| 311 | 280 | 31 |

### Summary Totals Devices Under Tests

| DUT | Total Tests | Tests Passed | Tests Failed | Categories Failed |
| --- | ----------- | ------------ | ------------ | ----------------- |
| POD01-LEAF1A |  41 | 37 | 4 | NTP, Interface State, BGP |
| POD01-LEAF1B |  39 | 36 | 3 | NTP, Interface State, BGP |
| POD01-LEAF2A |  40 | 38 | 2 | NTP, Interface State |
| POD01-LEAF2B |  40 | 38 | 2 | NTP, Interface State |
| POD01-SPINE1 |  40 | 35 | 5 | NTP, BGP |
| POD01-SPINE2 |  40 | 35 | 5 | NTP, BGP |
| POD01-SUBLEAF1A |  7 | 6 | 1 | NTP |
| ROUTE-SERVER1 |  24 | 17 | 7 | NTP, BGP, Routing Table, Loopback0 Reachability |
| SUPER-SPINE1 |  20 | 19 | 1 | NTP |
| SUPER-SPINE2 |  20 | 19 | 1 | NTP |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed |
| ------------- | ----------- | ------------ | ------------ |
| NTP |  10 | 0 | 10 |
| Interface State |  86 | 81 | 5 |
| LLDP Topology |  36 | 36 | 0 |
| MLAG |  4 | 4 | 0 |
| IP Reachability |  28 | 28 | 0 |
| BGP |  57 | 45 | 12 |
| Reload Cause |  10 | 10 | 0 |
| Routing Table |  44 | 42 | 2 |
| Loopback0 Reachability |  36 | 34 | 2 |

## Failed Test Results Summary

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | POD01-LEAF1A | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 2 | POD01-LEAF1B | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 3 | POD01-LEAF2A | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 4 | POD01-LEAF2B | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 5 | POD01-SPINE1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 6 | POD01-SPINE2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 7 | POD01-SUBLEAF1A | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 8 | ROUTE-SERVER1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 9 | SUPER-SPINE1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 10 | SUPER-SPINE2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 50 | POD01-LEAF1A | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - server-1_PortChannel | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 60 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 66 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 72 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 78 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 206 | POD01-LEAF1A | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.3.1 | FAIL | Session state "Active" |
| 207 | POD01-LEAF1B | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.3.1 | FAIL | Session state "Active" |
| 210 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.3 | FAIL | Session state "Connect" |
| 211 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.4 | FAIL | Session state "Connect" |
| 212 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.5 | FAIL | Session state "Connect" |
| 213 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.6 | FAIL | Session state "Connect" |
| 214 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.3 | FAIL | Session state "Connect" |
| 215 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.4 | FAIL | Session state "Connect" |
| 216 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.5 | FAIL | Session state "Connect" |
| 217 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.6 | FAIL | Session state "Connect" |
| 218 | ROUTE-SERVER1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.3 | FAIL | Session state "Active" |
| 219 | ROUTE-SERVER1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.4 | FAIL | Session state "Active" |
| 264 | ROUTE-SERVER1 | Routing Table | Remote Lo0 address | 10.1.2.3 | FAIL | Lo0 10.1.2.3 is not in the routing table |
| 265 | ROUTE-SERVER1 | Routing Table | Remote Lo0 address | 10.1.2.4 | FAIL | Lo0 10.1.2.4 is not in the routing table |
| 300 | ROUTE-SERVER1 | Loopback0 Reachability | Loopback0 Reachability | Source: ROUTE-SERVER1 - 10.1.3.1 Destination: 10.1.2.3 | FAIL | 100% packet loss |
| 301 | ROUTE-SERVER1 | Loopback0 Reachability | Loopback0 Reachability | Source: ROUTE-SERVER1 - 10.1.3.1 Destination: 10.1.2.4 | FAIL | 100% packet loss |

## All Test Results

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | POD01-LEAF1A | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 2 | POD01-LEAF1B | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 3 | POD01-LEAF2A | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 4 | POD01-LEAF2B | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 5 | POD01-SPINE1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 6 | POD01-SPINE2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 7 | POD01-SUBLEAF1A | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 8 | ROUTE-SERVER1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 9 | SUPER-SPINE1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 10 | SUPER-SPINE2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 11 | POD01-LEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-SPINE1_Ethernet3 | PASS |  |
| 12 | POD01-LEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-SPINE2_Ethernet3 | PASS |  |
| 13 | POD01-LEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - MLAG_PEER_POD01-LEAF1B_Ethernet3 | PASS |  |
| 14 | POD01-LEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - POD01-SUBLEAF1A_Ethernet1 | PASS |  |
| 15 | POD01-LEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - server-1_Eth1 | PASS |  |
| 16 | POD01-LEAF1B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-SPINE1_Ethernet4 | PASS |  |
| 17 | POD01-LEAF1B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-SPINE2_Ethernet4 | PASS |  |
| 18 | POD01-LEAF1B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - MLAG_PEER_POD01-LEAF1A_Ethernet3 | PASS |  |
| 19 | POD01-LEAF1B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - POD01-SUBLEAF1A_Ethernet2 | PASS |  |
| 20 | POD01-LEAF2A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-SPINE1_Ethernet5 | PASS |  |
| 21 | POD01-LEAF2A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-SPINE2_Ethernet5 | PASS |  |
| 22 | POD01-LEAF2A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - MLAG_PEER_POD01-LEAF2B_Ethernet3 | PASS |  |
| 23 | POD01-LEAF2A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_ROUTE-SERVER1_Ethernet1 | PASS |  |
| 24 | POD01-LEAF2B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-SPINE1_Ethernet6 | PASS |  |
| 25 | POD01-LEAF2B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-SPINE2_Ethernet6 | PASS |  |
| 26 | POD01-LEAF2B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - MLAG_PEER_POD01-LEAF2A_Ethernet3 | PASS |  |
| 27 | POD01-LEAF2B | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_ROUTE-SERVER1_Ethernet2 | PASS |  |
| 28 | POD01-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_POD01-LEAF1A_Ethernet1 | PASS |  |
| 29 | POD01-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_POD01-LEAF1B_Ethernet1 | PASS |  |
| 30 | POD01-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_POD01-LEAF2A_Ethernet1 | PASS |  |
| 31 | POD01-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_POD01-LEAF2B_Ethernet1 | PASS |  |
| 32 | POD01-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_SUPER-SPINE1_Ethernet1 | PASS |  |
| 33 | POD01-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_SUPER-SPINE2_Ethernet1 | PASS |  |
| 34 | POD01-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_POD01-LEAF1A_Ethernet2 | PASS |  |
| 35 | POD01-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_POD01-LEAF1B_Ethernet2 | PASS |  |
| 36 | POD01-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_POD01-LEAF2A_Ethernet2 | PASS |  |
| 37 | POD01-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_POD01-LEAF2B_Ethernet2 | PASS |  |
| 38 | POD01-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_SUPER-SPINE1_Ethernet2 | PASS |  |
| 39 | POD01-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_SUPER-SPINE2_Ethernet2 | PASS |  |
| 40 | POD01-SUBLEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - POD01-LEAF1A_Ethernet4 | PASS |  |
| 41 | POD01-SUBLEAF1A | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - POD01-LEAF1B_Ethernet4 | PASS |  |
| 42 | ROUTE-SERVER1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-LEAF2A_Ethernet4 | PASS |  |
| 43 | ROUTE-SERVER1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-LEAF2B_Ethernet4 | PASS |  |
| 44 | SUPER-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-SPINE1_Ethernet1 | PASS |  |
| 45 | SUPER-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-SPINE2_Ethernet1 | PASS |  |
| 46 | SUPER-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_POD01-SPINE1_Ethernet2 | PASS |  |
| 47 | SUPER-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_POD01-SPINE2_Ethernet2 | PASS |  |
| 48 | POD01-LEAF1A | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - POD01_SUBLEAF1_Po1 | PASS |  |
| 49 | POD01-LEAF1A | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - MLAG_PEER_POD01-LEAF1B_Po3 | PASS |  |
| 50 | POD01-LEAF1A | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - server-1_PortChannel | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 51 | POD01-LEAF1B | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - POD01_SUBLEAF1_Po1 | PASS |  |
| 52 | POD01-LEAF1B | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - MLAG_PEER_POD01-LEAF1A_Po3 | PASS |  |
| 53 | POD01-LEAF2A | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - MLAG_PEER_POD01-LEAF2B_Po3 | PASS |  |
| 54 | POD01-LEAF2B | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - MLAG_PEER_POD01-LEAF2A_Po3 | PASS |  |
| 55 | POD01-SUBLEAF1A | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel1 - POD01-LEAF1A_Po4 | PASS |  |
| 56 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 57 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 58 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4092 - L2LEAF_INBAND_MGMT | PASS |  |
| 59 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - Tenant_A_OP_Zone_1 | PASS |  |
| 60 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 61 | POD01-LEAF1A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - Tenant_A_OP_Zone_3 | PASS |  |
| 62 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 63 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 64 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4092 - L2LEAF_INBAND_MGMT | PASS |  |
| 65 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - Tenant_A_OP_Zone_1 | PASS |  |
| 66 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 67 | POD01-LEAF1B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - Tenant_A_OP_Zone_3 | PASS |  |
| 68 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 69 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 70 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4092 - L2LEAF_INBAND_MGMT | PASS |  |
| 71 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - Tenant_A_OP_Zone_1 | PASS |  |
| 72 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 73 | POD01-LEAF2A | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - Tenant_A_OP_Zone_3 | PASS |  |
| 74 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 75 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 76 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4092 - L2LEAF_INBAND_MGMT | PASS |  |
| 77 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - Tenant_A_OP_Zone_1 | PASS |  |
| 78 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - Tenant_A_OP_Zone_2 | FAIL | interface status: adminDown - line protocol status: down |
| 79 | POD01-LEAF2B | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - Tenant_A_OP_Zone_3 | PASS |  |
| 80 | POD01-LEAF1A | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 81 | POD01-LEAF1B | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 82 | POD01-LEAF2A | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 83 | POD01-LEAF2B | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 84 | POD01-LEAF1A | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 85 | POD01-LEAF1A | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 86 | POD01-LEAF1B | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 87 | POD01-LEAF1B | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 88 | POD01-LEAF2A | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 89 | POD01-LEAF2A | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 90 | POD01-LEAF2B | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 91 | POD01-LEAF2B | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 92 | POD01-SPINE1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 93 | POD01-SPINE2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 94 | ROUTE-SERVER1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 95 | SUPER-SPINE1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 96 | SUPER-SPINE2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 97 | POD01-LEAF1A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-SPINE1_Ethernet3 | PASS |  |
| 98 | POD01-LEAF1A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-SPINE2_Ethernet3 | PASS |  |
| 99 | POD01-LEAF1A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: POD01-LEAF1B_Ethernet3 | PASS |  |
| 100 | POD01-LEAF1A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: POD01-SUBLEAF1A_Ethernet1 | PASS |  |
| 101 | POD01-LEAF1B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-SPINE1_Ethernet4 | PASS |  |
| 102 | POD01-LEAF1B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-SPINE2_Ethernet4 | PASS |  |
| 103 | POD01-LEAF1B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: POD01-LEAF1A_Ethernet3 | PASS |  |
| 104 | POD01-LEAF1B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: POD01-SUBLEAF1A_Ethernet2 | PASS |  |
| 105 | POD01-LEAF2A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-SPINE1_Ethernet5 | PASS |  |
| 106 | POD01-LEAF2A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-SPINE2_Ethernet5 | PASS |  |
| 107 | POD01-LEAF2A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: POD01-LEAF2B_Ethernet3 | PASS |  |
| 108 | POD01-LEAF2A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: ROUTE-SERVER1_Ethernet1 | PASS |  |
| 109 | POD01-LEAF2B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-SPINE1_Ethernet6 | PASS |  |
| 110 | POD01-LEAF2B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-SPINE2_Ethernet6 | PASS |  |
| 111 | POD01-LEAF2B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: POD01-LEAF2A_Ethernet3 | PASS |  |
| 112 | POD01-LEAF2B | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: ROUTE-SERVER1_Ethernet2 | PASS |  |
| 113 | POD01-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: POD01-LEAF1A_Ethernet1 | PASS |  |
| 114 | POD01-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: POD01-LEAF1B_Ethernet1 | PASS |  |
| 115 | POD01-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet5 - remote: POD01-LEAF2A_Ethernet1 | PASS |  |
| 116 | POD01-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet6 - remote: POD01-LEAF2B_Ethernet1 | PASS |  |
| 117 | POD01-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: SUPER-SPINE1_Ethernet1 | PASS |  |
| 118 | POD01-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: SUPER-SPINE2_Ethernet1 | PASS |  |
| 119 | POD01-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: POD01-LEAF1A_Ethernet2 | PASS |  |
| 120 | POD01-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: POD01-LEAF1B_Ethernet2 | PASS |  |
| 121 | POD01-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet5 - remote: POD01-LEAF2A_Ethernet2 | PASS |  |
| 122 | POD01-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet6 - remote: POD01-LEAF2B_Ethernet2 | PASS |  |
| 123 | POD01-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: SUPER-SPINE1_Ethernet2 | PASS |  |
| 124 | POD01-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: SUPER-SPINE2_Ethernet2 | PASS |  |
| 125 | POD01-SUBLEAF1A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-LEAF1A_Ethernet4 | PASS |  |
| 126 | POD01-SUBLEAF1A | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-LEAF1B_Ethernet4 | PASS |  |
| 127 | ROUTE-SERVER1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-LEAF2A_Ethernet4 | PASS |  |
| 128 | ROUTE-SERVER1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-LEAF2B_Ethernet4 | PASS |  |
| 129 | SUPER-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-SPINE1_Ethernet1 | PASS |  |
| 130 | SUPER-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-SPINE2_Ethernet1 | PASS |  |
| 131 | SUPER-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: POD01-SPINE1_Ethernet2 | PASS |  |
| 132 | SUPER-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: POD01-SPINE2_Ethernet2 | PASS |  |
| 133 | POD01-LEAF1A | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 134 | POD01-LEAF1B | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 135 | POD01-LEAF2A | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 136 | POD01-LEAF2B | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 137 | POD01-LEAF1A | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF1A_Ethernet1 - Destination: POD01-SPINE1_Ethernet3 | PASS |  |
| 138 | POD01-LEAF1A | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF1A_Ethernet2 - Destination: POD01-SPINE2_Ethernet3 | PASS |  |
| 139 | POD01-LEAF1B | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF1B_Ethernet1 - Destination: POD01-SPINE1_Ethernet4 | PASS |  |
| 140 | POD01-LEAF1B | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF1B_Ethernet2 - Destination: POD01-SPINE2_Ethernet4 | PASS |  |
| 141 | POD01-LEAF2A | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF2A_Ethernet1 - Destination: POD01-SPINE1_Ethernet5 | PASS |  |
| 142 | POD01-LEAF2A | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF2A_Ethernet2 - Destination: POD01-SPINE2_Ethernet5 | PASS |  |
| 143 | POD01-LEAF2A | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF2A_Ethernet4 - Destination: ROUTE-SERVER1_Ethernet1 | PASS |  |
| 144 | POD01-LEAF2B | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF2B_Ethernet1 - Destination: POD01-SPINE1_Ethernet6 | PASS |  |
| 145 | POD01-LEAF2B | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF2B_Ethernet2 - Destination: POD01-SPINE2_Ethernet6 | PASS |  |
| 146 | POD01-LEAF2B | IP Reachability | ip reachability test p2p links | Source: POD01-LEAF2B_Ethernet4 - Destination: ROUTE-SERVER1_Ethernet2 | PASS |  |
| 147 | POD01-SPINE1 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE1_Ethernet3 - Destination: POD01-LEAF1A_Ethernet1 | PASS |  |
| 148 | POD01-SPINE1 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE1_Ethernet4 - Destination: POD01-LEAF1B_Ethernet1 | PASS |  |
| 149 | POD01-SPINE1 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE1_Ethernet5 - Destination: POD01-LEAF2A_Ethernet1 | PASS |  |
| 150 | POD01-SPINE1 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE1_Ethernet6 - Destination: POD01-LEAF2B_Ethernet1 | PASS |  |
| 151 | POD01-SPINE1 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE1_Ethernet1 - Destination: SUPER-SPINE1_Ethernet1 | PASS |  |
| 152 | POD01-SPINE1 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE1_Ethernet2 - Destination: SUPER-SPINE2_Ethernet1 | PASS |  |
| 153 | POD01-SPINE2 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE2_Ethernet3 - Destination: POD01-LEAF1A_Ethernet2 | PASS |  |
| 154 | POD01-SPINE2 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE2_Ethernet4 - Destination: POD01-LEAF1B_Ethernet2 | PASS |  |
| 155 | POD01-SPINE2 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE2_Ethernet5 - Destination: POD01-LEAF2A_Ethernet2 | PASS |  |
| 156 | POD01-SPINE2 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE2_Ethernet6 - Destination: POD01-LEAF2B_Ethernet2 | PASS |  |
| 157 | POD01-SPINE2 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE2_Ethernet1 - Destination: SUPER-SPINE1_Ethernet2 | PASS |  |
| 158 | POD01-SPINE2 | IP Reachability | ip reachability test p2p links | Source: POD01-SPINE2_Ethernet2 - Destination: SUPER-SPINE2_Ethernet2 | PASS |  |
| 159 | ROUTE-SERVER1 | IP Reachability | ip reachability test p2p links | Source: ROUTE-SERVER1_Ethernet1 - Destination: POD01-LEAF2A_Ethernet4 | PASS |  |
| 160 | ROUTE-SERVER1 | IP Reachability | ip reachability test p2p links | Source: ROUTE-SERVER1_Ethernet2 - Destination: POD01-LEAF2B_Ethernet4 | PASS |  |
| 161 | SUPER-SPINE1 | IP Reachability | ip reachability test p2p links | Source: SUPER-SPINE1_Ethernet1 - Destination: POD01-SPINE1_Ethernet1 | PASS |  |
| 162 | SUPER-SPINE1 | IP Reachability | ip reachability test p2p links | Source: SUPER-SPINE1_Ethernet2 - Destination: POD01-SPINE2_Ethernet1 | PASS |  |
| 163 | SUPER-SPINE2 | IP Reachability | ip reachability test p2p links | Source: SUPER-SPINE2_Ethernet1 - Destination: POD01-SPINE1_Ethernet2 | PASS |  |
| 164 | SUPER-SPINE2 | IP Reachability | ip reachability test p2p links | Source: SUPER-SPINE2_Ethernet2 - Destination: POD01-SPINE2_Ethernet2 | PASS |  |
| 165 | POD01-LEAF1A | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 166 | POD01-LEAF1B | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 167 | POD01-LEAF2A | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 168 | POD01-LEAF2B | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 169 | POD01-SPINE1 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 170 | POD01-SPINE2 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 171 | ROUTE-SERVER1 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 172 | SUPER-SPINE1 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 173 | SUPER-SPINE2 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 174 | POD01-LEAF1A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.0 | PASS |  |
| 175 | POD01-LEAF1A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.2 | PASS |  |
| 176 | POD01-LEAF1A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.0.1 | PASS |  |
| 177 | POD01-LEAF1B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.4 | PASS |  |
| 178 | POD01-LEAF1B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.6 | PASS |  |
| 179 | POD01-LEAF1B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.0.0 | PASS |  |
| 180 | POD01-LEAF2A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.8 | PASS |  |
| 181 | POD01-LEAF2A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.10 | PASS |  |
| 182 | POD01-LEAF2A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.0.5 | PASS |  |
| 183 | POD01-LEAF2A | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.2.1 | PASS |  |
| 184 | POD01-LEAF2B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.12 | PASS |  |
| 185 | POD01-LEAF2B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.14 | PASS |  |
| 186 | POD01-LEAF2B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.0.4 | PASS |  |
| 187 | POD01-LEAF2B | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.2.3 | PASS |  |
| 188 | POD01-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.1 | PASS |  |
| 189 | POD01-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.5 | PASS |  |
| 190 | POD01-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.9 | PASS |  |
| 191 | POD01-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.13 | PASS |  |
| 192 | POD01-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.0 | PASS |  |
| 193 | POD01-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.64 | PASS |  |
| 194 | POD01-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.3 | PASS |  |
| 195 | POD01-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.7 | PASS |  |
| 196 | POD01-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.11 | PASS |  |
| 197 | POD01-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.3.15 | PASS |  |
| 198 | POD01-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.2 | PASS |  |
| 199 | POD01-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.66 | PASS |  |
| 200 | ROUTE-SERVER1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.2.0 | PASS |  |
| 201 | ROUTE-SERVER1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.2.2 | PASS |  |
| 202 | SUPER-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.1 | PASS |  |
| 203 | SUPER-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.3 | PASS |  |
| 204 | SUPER-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.65 | PASS |  |
| 205 | SUPER-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.0.1.67 | PASS |  |
| 206 | POD01-LEAF1A | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.3.1 | FAIL | Session state "Active" |
| 207 | POD01-LEAF1B | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.3.1 | FAIL | Session state "Active" |
| 208 | POD01-LEAF2A | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.3.1 | PASS |  |
| 209 | POD01-LEAF2B | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.3.1 | PASS |  |
| 210 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.3 | FAIL | Session state "Connect" |
| 211 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.4 | FAIL | Session state "Connect" |
| 212 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.5 | FAIL | Session state "Connect" |
| 213 | POD01-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.6 | FAIL | Session state "Connect" |
| 214 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.3 | FAIL | Session state "Connect" |
| 215 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.4 | FAIL | Session state "Connect" |
| 216 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.5 | FAIL | Session state "Connect" |
| 217 | POD01-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.6 | FAIL | Session state "Connect" |
| 218 | ROUTE-SERVER1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.3 | FAIL | Session state "Active" |
| 219 | ROUTE-SERVER1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.4 | FAIL | Session state "Active" |
| 220 | ROUTE-SERVER1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.5 | PASS |  |
| 221 | ROUTE-SERVER1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.1.2.6 | PASS |  |
| 222 | POD01-LEAF1A | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 223 | POD01-LEAF1B | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 224 | POD01-LEAF2A | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 225 | POD01-LEAF2B | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 226 | POD01-SPINE1 | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 227 | POD01-SPINE2 | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 228 | POD01-SUBLEAF1A | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 229 | ROUTE-SERVER1 | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 230 | SUPER-SPINE1 | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 231 | SUPER-SPINE2 | Reload Cause | Reload Cause: Reload requested by the user | Reload Cause | PASS |  |
| 232 | POD01-LEAF1A | Routing Table | Remote Lo1 address | 10.1.5.3 | PASS |  |
| 233 | POD01-LEAF1A | Routing Table | Remote Lo1 address | 10.1.5.5 | PASS |  |
| 234 | POD01-LEAF1B | Routing Table | Remote Lo1 address | 10.1.5.3 | PASS |  |
| 235 | POD01-LEAF1B | Routing Table | Remote Lo1 address | 10.1.5.5 | PASS |  |
| 236 | POD01-LEAF2A | Routing Table | Remote Lo1 address | 10.1.5.3 | PASS |  |
| 237 | POD01-LEAF2A | Routing Table | Remote Lo1 address | 10.1.5.5 | PASS |  |
| 238 | POD01-LEAF2B | Routing Table | Remote Lo1 address | 10.1.5.3 | PASS |  |
| 239 | POD01-LEAF2B | Routing Table | Remote Lo1 address | 10.1.5.5 | PASS |  |
| 240 | POD01-LEAF1A | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 241 | POD01-LEAF1A | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 242 | POD01-LEAF1A | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 243 | POD01-LEAF1A | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 244 | POD01-LEAF1B | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 245 | POD01-LEAF1B | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 246 | POD01-LEAF1B | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 247 | POD01-LEAF1B | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 248 | POD01-LEAF2A | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 249 | POD01-LEAF2A | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 250 | POD01-LEAF2A | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 251 | POD01-LEAF2A | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 252 | POD01-LEAF2B | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 253 | POD01-LEAF2B | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 254 | POD01-LEAF2B | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 255 | POD01-LEAF2B | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 256 | POD01-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 257 | POD01-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 258 | POD01-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 259 | POD01-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 260 | POD01-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 261 | POD01-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 262 | POD01-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 263 | POD01-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 264 | ROUTE-SERVER1 | Routing Table | Remote Lo0 address | 10.1.2.3 | FAIL | Lo0 10.1.2.3 is not in the routing table |
| 265 | ROUTE-SERVER1 | Routing Table | Remote Lo0 address | 10.1.2.4 | FAIL | Lo0 10.1.2.4 is not in the routing table |
| 266 | ROUTE-SERVER1 | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 267 | ROUTE-SERVER1 | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 268 | SUPER-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 269 | SUPER-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 270 | SUPER-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 271 | SUPER-SPINE1 | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 272 | SUPER-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.3 | PASS |  |
| 273 | SUPER-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.4 | PASS |  |
| 274 | SUPER-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.5 | PASS |  |
| 275 | SUPER-SPINE2 | Routing Table | Remote Lo0 address | 10.1.2.6 | PASS |  |
| 276 | POD01-LEAF1A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1A - 10.1.2.3 Destination: 10.1.2.3 | PASS |  |
| 277 | POD01-LEAF1A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1A - 10.1.2.3 Destination: 10.1.2.4 | PASS |  |
| 278 | POD01-LEAF1A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1A - 10.1.2.3 Destination: 10.1.2.5 | PASS |  |
| 279 | POD01-LEAF1A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1A - 10.1.2.3 Destination: 10.1.2.6 | PASS |  |
| 280 | POD01-LEAF1B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1B - 10.1.2.4 Destination: 10.1.2.3 | PASS |  |
| 281 | POD01-LEAF1B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1B - 10.1.2.4 Destination: 10.1.2.4 | PASS |  |
| 282 | POD01-LEAF1B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1B - 10.1.2.4 Destination: 10.1.2.5 | PASS |  |
| 283 | POD01-LEAF1B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF1B - 10.1.2.4 Destination: 10.1.2.6 | PASS |  |
| 284 | POD01-LEAF2A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2A - 10.1.2.5 Destination: 10.1.2.3 | PASS |  |
| 285 | POD01-LEAF2A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2A - 10.1.2.5 Destination: 10.1.2.4 | PASS |  |
| 286 | POD01-LEAF2A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2A - 10.1.2.5 Destination: 10.1.2.5 | PASS |  |
| 287 | POD01-LEAF2A | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2A - 10.1.2.5 Destination: 10.1.2.6 | PASS |  |
| 288 | POD01-LEAF2B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2B - 10.1.2.6 Destination: 10.1.2.3 | PASS |  |
| 289 | POD01-LEAF2B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2B - 10.1.2.6 Destination: 10.1.2.4 | PASS |  |
| 290 | POD01-LEAF2B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2B - 10.1.2.6 Destination: 10.1.2.5 | PASS |  |
| 291 | POD01-LEAF2B | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-LEAF2B - 10.1.2.6 Destination: 10.1.2.6 | PASS |  |
| 292 | POD01-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE1 - 10.1.2.1 Destination: 10.1.2.3 | PASS |  |
| 293 | POD01-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE1 - 10.1.2.1 Destination: 10.1.2.4 | PASS |  |
| 294 | POD01-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE1 - 10.1.2.1 Destination: 10.1.2.5 | PASS |  |
| 295 | POD01-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE1 - 10.1.2.1 Destination: 10.1.2.6 | PASS |  |
| 296 | POD01-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE2 - 10.1.2.2 Destination: 10.1.2.3 | PASS |  |
| 297 | POD01-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE2 - 10.1.2.2 Destination: 10.1.2.4 | PASS |  |
| 298 | POD01-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE2 - 10.1.2.2 Destination: 10.1.2.5 | PASS |  |
| 299 | POD01-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: POD01-SPINE2 - 10.1.2.2 Destination: 10.1.2.6 | PASS |  |
| 300 | ROUTE-SERVER1 | Loopback0 Reachability | Loopback0 Reachability | Source: ROUTE-SERVER1 - 10.1.3.1 Destination: 10.1.2.3 | FAIL | 100% packet loss |
| 301 | ROUTE-SERVER1 | Loopback0 Reachability | Loopback0 Reachability | Source: ROUTE-SERVER1 - 10.1.3.1 Destination: 10.1.2.4 | FAIL | 100% packet loss |
| 302 | ROUTE-SERVER1 | Loopback0 Reachability | Loopback0 Reachability | Source: ROUTE-SERVER1 - 10.1.3.1 Destination: 10.1.2.5 | PASS |  |
| 303 | ROUTE-SERVER1 | Loopback0 Reachability | Loopback0 Reachability | Source: ROUTE-SERVER1 - 10.1.3.1 Destination: 10.1.2.6 | PASS |  |
| 304 | SUPER-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE1 - 10.1.1.1 Destination: 10.1.2.3 | PASS |  |
| 305 | SUPER-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE1 - 10.1.1.1 Destination: 10.1.2.4 | PASS |  |
| 306 | SUPER-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE1 - 10.1.1.1 Destination: 10.1.2.5 | PASS |  |
| 307 | SUPER-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE1 - 10.1.1.1 Destination: 10.1.2.6 | PASS |  |
| 308 | SUPER-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE2 - 10.1.1.2 Destination: 10.1.2.3 | PASS |  |
| 309 | SUPER-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE2 - 10.1.1.2 Destination: 10.1.2.4 | PASS |  |
| 310 | SUPER-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE2 - 10.1.1.2 Destination: 10.1.2.5 | PASS |  |
| 311 | SUPER-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: SUPER-SPINE2 - 10.1.1.2 Destination: 10.1.2.6 | PASS |  |
