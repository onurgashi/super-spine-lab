# POD01-LEAF2B Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 P2P_LINK_TO_POD01-SPINE1_Ethernet6
Et2                            up             up                 P2P_LINK_TO_POD01-SPINE2_Ethernet6
Et3                            up             up                 MLAG_PEER_POD01-LEAF2A_Ethernet3
Et4                            up             up                 P2P_LINK_TO_ROUTE-SERVER1_Ethernet2
Et5                            up             up                 
Et6                            up             up                 
Et7                            up             up                 
Et8                            up             up                 
Lo0                            up             up                 EVPN_Overlay_Peering
Lo1                            up             up                 VTEP_VXLAN_Tunnel_Source
Ma1                            up             up                 oob_management
Po3                            up             up                 MLAG_PEER_POD01-LEAF2A_Po3
Vl110                          up             up                 Tenant_A_OP_Zone_1
Vl111                          admin down     down               Tenant_A_OP_Zone_2
Vl112                          up             up                 Tenant_A_OP_Zone_3
Vl1009                         up             up                 
Vl4092                         up             up                 L2LEAF_INBAND_MGMT
Vl4093                         up             up                 MLAG_PEER_L3_PEERING
Vl4094                         up             up                 MLAG_PEER
Vx1                            up             up
```
## show ip interface brief

```
Address 
Interface      IP Address         Status         Protocol         MTU   Owner   
-------------- ------------------ -------------- ------------ --------- ------- 
Ethernet1      10.0.3.13/31       up             up              1500           
Ethernet2      10.0.3.15/31       up             up              1500           
Ethernet4      10.0.2.2/31        up             up              1500           
Loopback0      10.1.2.6/32        up             up             65535           
Loopback1      10.1.5.5/32        up             up             65535           
Management1    192.168.1.8/24     up             up              1500           
Vlan110        10.1.10.1/24       up             up              1500           
Vlan111        10.1.11.1/24       admin down     down            1500           
Vlan112        10.1.12.1/24       up             up              1500           
Vlan1009       unassigned         up             up              9164           
Vlan4092       10.160.255.3/24    up             up              1500           
Vlan4093       10.255.0.5/31      up             up              1500           
Vlan4094       10.255.1.5/31      up             up              1500
```
## show lldp neighbors

```
Last table change time   : 4:43:17 ago
Number of table inserts  : 13
Number of table deletes  : 0
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID       Neighbor Port ID    TTL 
---------- ------------------------ ---------------------- --- 
Et1           POD01-SPINE1             Ethernet6           120 
Et2           POD01-SPINE2             Ethernet6           120 
Et3           POD01-LEAF2A             Ethernet3           120 
Et4           ROUTE-SERVER1            Ethernet2           120 
Ma1           SUPER-SPINE1             Management1         120 
Ma1           POD01-LEAF1B             Management1         120 
Ma1           POD01-LEAF2A             Management1         120 
Ma1           POD01-SPINE2             Management1         120 
Ma1           SUPER-SPINE2             Management1         120 
Ma1           POD01-LEAF1A             Management1         120 
Ma1           POD01-SPINE1             Management1         120 
Ma1           POD01-SUBLEAF1A          Management1         120 
Ma1           ROUTE-SERVER1            Management1         120
```
## show running-config

```
! Command: show running-config
! device: POD01-LEAF2B (vEOS, EOS-4.25.0F)
!
! boot system flash:/vEOS-lab.swi
!
vlan internal order ascending range 1006 1199
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname POD01-LEAF2B
ip name-server vrf MGMT 1.2.3.4
!
ntp local-interface vrf MGMT Management1
ntp server vrf MGMT fr.pool.ntp.org
ntp server vrf MGMT uk.pool.ntp.org prefer
!
spanning-tree mode mstp
no spanning-tree vlan-id 4093-4094
spanning-tree mst 0 priority 4096
!
no aaa root
!
username admin privilege 15 role network-admin secret sha512 $6$eJ5TvI8oru5i9e8G$R1X/SbtGTk9xoEHEBQASc7SC2nHYmi.crVgp2pXuCXwxsXEA81e4E0cXgQ6kX08fIeQzauqhv2kS.RGJFCon5/
!
vlan 110
   name Tenant_A_OP_Zone_1
!
vlan 111
   name Tenant_A_OP_Zone_2
!
vlan 112
   name Tenant_A_OP_Zone_3
!
vlan 4092
   name L2LEAF_INBAND_MGMT
!
vlan 4093
   name LEAF_PEER_L3
   trunk group LEAF_PEER_L3
!
vlan 4094
   name MLAG_PEER
   trunk group MLAG
!
vrf instance Common_VRF
!
vrf instance MGMT
!
interface Port-Channel3
   description MLAG_PEER_POD01-LEAF2A_Po3
   switchport trunk allowed vlan 2-4094
   switchport mode trunk
   switchport trunk group LEAF_PEER_L3
   switchport trunk group MLAG
   service-profile blah
!
interface Ethernet1
   description P2P_LINK_TO_POD01-SPINE1_Ethernet6
   no switchport
   ip address 10.0.3.13/31
   service-profile blah
!
interface Ethernet2
   description P2P_LINK_TO_POD01-SPINE2_Ethernet6
   no switchport
   ip address 10.0.3.15/31
   service-profile blah
!
interface Ethernet3
   description MLAG_PEER_POD01-LEAF2A_Ethernet3
   channel-group 3 mode active
!
interface Ethernet4
   description P2P_LINK_TO_ROUTE-SERVER1_Ethernet2
   no switchport
   ip address 10.0.2.2/31
   service-profile blah
!
interface Ethernet5
!
interface Ethernet6
!
interface Ethernet7
!
interface Ethernet8
!
interface Loopback0
   description EVPN_Overlay_Peering
   ip address 10.1.2.6/32
!
interface Loopback1
   description VTEP_VXLAN_Tunnel_Source
   ip address 10.1.5.5/32
!
interface Management1
   description oob_management
   vrf MGMT
   ip address 192.168.1.8/24
!
interface Vlan110
   description Tenant_A_OP_Zone_1
   vrf Common_VRF
   ip address virtual 10.1.10.1/24
!
interface Vlan111
   description Tenant_A_OP_Zone_2
   shutdown
   vrf Common_VRF
   ip address virtual 10.1.11.1/24
!
interface Vlan112
   description Tenant_A_OP_Zone_3
   vrf Common_VRF
   ip address virtual 10.1.12.1/24
!
interface Vlan4092
   description L2LEAF_INBAND_MGMT
   ip address 10.160.255.3/24
   ip attached-host route export 19
   ip virtual-router address 10.160.255.1
!
interface Vlan4093
   description MLAG_PEER_L3_PEERING
   ip address 10.255.0.5/31
!
interface Vlan4094
   description MLAG_PEER
   no autostate
   ip address 10.255.1.5/31
!
interface Vxlan1
   vxlan source-interface Loopback1
   vxlan virtual-router encapsulation mac-address mlag-system-id
   vxlan udp-port 4789
   vxlan vlan 110 vni 10110
   vxlan vlan 111 vni 50111
   vxlan vlan 112 vni 50112
   vxlan vrf Common_VRF vni 1025
!
ip virtual-router mac-address 00:1c:73:00:dc:01
!
ip routing
ip routing vrf Common_VRF
no ip routing vrf MGMT
!
ip prefix-list PL-L2LEAF-INBAND-MGMT
   seq 10 permit 10.160.255.0/24
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 10.1.2.0/24 eq 32
   seq 20 permit 10.1.5.0/24 eq 32
!
mlag configuration
   domain-id POD01_LEAF2
   local-interface Vlan4094
   peer-address 10.255.1.4
   peer-link Port-Channel3
   reload-delay mlag 300
   reload-delay non-mlag 330
!
ip route vrf MGMT 0.0.0.0/0 192.168.1.254
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
!
route-map RM-CONN-2-BGP permit 20
   match ip address prefix-list PL-L2LEAF-INBAND-MGMT
!
route-map RM-MLAG-PEER-IN permit 10
   description Make routes learned over MLAG Peer-link less preferred on spines to ensure optimal routing
   set origin incomplete
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
!
router bgp 65102
   router-id 10.1.2.6
   no bgp default ipv4-unicast
   distance bgp 20 200 200
   graceful-restart restart-time 300
   graceful-restart
   maximum-paths 4 ecmp 4
   neighbor EVPN-OVERLAY-PEERS peer group
   neighbor EVPN-OVERLAY-PEERS remote-as 65100
   neighbor EVPN-OVERLAY-PEERS update-source Loopback0
   neighbor EVPN-OVERLAY-PEERS bfd
   neighbor EVPN-OVERLAY-PEERS ebgp-multihop 15
   neighbor EVPN-OVERLAY-PEERS password 7 q+VNViP5i4rVjW1cxFv2wA==
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor IPv4-UNDERLAY-PEERS peer group
   neighbor IPv4-UNDERLAY-PEERS remote-as 65100
   neighbor IPv4-UNDERLAY-PEERS password 7 AQQvKeimxJu+uGQ/yYvv9w==
   neighbor IPv4-UNDERLAY-PEERS send-community
   neighbor IPv4-UNDERLAY-PEERS maximum-routes 12000
   neighbor MLAG-IPv4-UNDERLAY-PEER peer group
   neighbor MLAG-IPv4-UNDERLAY-PEER remote-as 65102
   neighbor MLAG-IPv4-UNDERLAY-PEER next-hop-self
   neighbor MLAG-IPv4-UNDERLAY-PEER route-map RM-MLAG-PEER-IN in
   neighbor MLAG-IPv4-UNDERLAY-PEER password 7 vnEaG8gMeQf3d3cN6PktXQ==
   neighbor MLAG-IPv4-UNDERLAY-PEER send-community
   neighbor MLAG-IPv4-UNDERLAY-PEER maximum-routes 12000
   neighbor 10.0.2.3 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.2.3 remote-as 65100
   neighbor 10.0.2.3 description ROUTE-SERVER1
   neighbor 10.0.3.12 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.3.14 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.1.3.1 peer group EVPN-OVERLAY-PEERS
   neighbor 10.1.3.1 remote-as 65100
   neighbor 10.1.3.1 description ROUTE-SERVER1
   neighbor 10.255.0.4 peer group MLAG-IPv4-UNDERLAY-PEER
   redistribute connected route-map RM-CONN-2-BGP
   redistribute attached-host
   !
   vlan 110
      rd 65102:10110
      route-target both 65000:10110
      redistribute learned
   !
   vlan 111
      rd 65102:50111
      route-target both 65000:50111
      redistribute learned
   !
   vlan 112
      rd 65102:50112
      route-target both 65000:50112
      redistribute learned
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
      no neighbor IPv4-UNDERLAY-PEERS activate
      no neighbor MLAG-IPv4-UNDERLAY-PEER activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
      neighbor MLAG-IPv4-UNDERLAY-PEER activate
   !
   vrf Common_VRF
      rd 65102:1025
      route-target import evpn 65000:1025
      route-target export evpn 65000:1025
      router-id 10.1.2.6
      redistribute connected
!
management api http-commands
   no shutdown
   !
   vrf MGMT
      no shutdown
!
end
```
## show version

```
vEOS
Hardware version: 
Serial number: 
Hardware MAC address: 50ba.0019.e550
System MAC address: 50ba.0019.e550

Software image version: 4.25.0F
Architecture: i686
Internal build version: 4.25.0F-19426669.4250F
Internal build ID: 3e3fd8c9-cd7e-43fc-b5c7-4bd41eb55161

Uptime: 0 weeks, 0 days, 9 hours and 23 minutes
Total memory: 4008608 kB
Free memory: 3071724 kB
```
