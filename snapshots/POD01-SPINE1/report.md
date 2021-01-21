# POD01-SPINE1 Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 P2P_LINK_TO_SUPER-SPINE1_Ethernet1
Et2                            up             up                 P2P_LINK_TO_SUPER-SPINE2_Ethernet1
Et3                            up             up                 P2P_LINK_TO_POD01-LEAF1A_Ethernet1
Et4                            up             up                 P2P_LINK_TO_POD01-LEAF1B_Ethernet1
Et5                            up             up                 P2P_LINK_TO_POD01-LEAF2A_Ethernet1
Et6                            up             up                 P2P_LINK_TO_POD01-LEAF2B_Ethernet1
Et7                            up             up                 
Et8                            up             up                 
Lo0                            up             up                 EVPN_Overlay_Peering
Ma1                            up             up                 oob_management
```
## show ip interface brief

```
Address 
Interface       IP Address         Status      Protocol          MTU    Owner   
--------------- ------------------ ----------- ------------- ---------- ------- 
Ethernet1       10.0.1.1/31        up          up               1500            
Ethernet2       10.0.1.65/31       up          up               1500            
Ethernet3       10.0.3.0/31        up          up               1500            
Ethernet4       10.0.3.4/31        up          up               1500            
Ethernet5       10.0.3.8/31        up          up               1500            
Ethernet6       10.0.3.12/31       up          up               1500            
Loopback0       10.1.2.1/32        up          up              65535            
Management1     192.168.1.3/24     up          up               1500
```
## show lldp neighbors

```
Last table change time   : 4:43:00 ago
Number of table inserts  : 30
Number of table deletes  : 15
Number of table drops    : 0
Number of table age-outs : 6

Port          Neighbor Device ID       Neighbor Port ID    TTL 
---------- ------------------------ ---------------------- --- 
Et1           SUPER-SPINE1             Ethernet1           120 
Et2           SUPER-SPINE2             Ethernet1           120 
Et3           POD01-LEAF1A             Ethernet1           120 
Et4           POD01-LEAF1B             Ethernet1           120 
Et5           POD01-LEAF2A             Ethernet1           120 
Et6           POD01-LEAF2B             Ethernet1           120 
Ma1           POD01-LEAF2A             Management1         120 
Ma1           POD01-SUBLEAF1A          Management1         120 
Ma1           POD01-SPINE2             Management1         120 
Ma1           POD01-LEAF2B             Management1         120 
Ma1           POD01-LEAF1A             Management1         120 
Ma1           POD01-LEAF1B             Management1         120 
Ma1           ROUTE-SERVER1            Management1         120 
Ma1           SUPER-SPINE1             Management1         120 
Ma1           SUPER-SPINE2             Management1         120
```
## show running-config

```
! Command: show running-config
! device: POD01-SPINE1 (vEOS, EOS-4.25.0F)
!
! boot system flash:/vEOS-lab.swi
!
vlan internal order ascending range 1006 1199
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname POD01-SPINE1
ip name-server vrf MGMT 1.2.3.4
!
ntp local-interface vrf MGMT Management1
ntp server vrf MGMT fr.pool.ntp.org
ntp server vrf MGMT uk.pool.ntp.org prefer
!
spanning-tree mode none
!
no aaa root
!
username admin privilege 15 role network-admin secret sha512 $6$eJ5TvI8oru5i9e8G$R1X/SbtGTk9xoEHEBQASc7SC2nHYmi.crVgp2pXuCXwxsXEA81e4E0cXgQ6kX08fIeQzauqhv2kS.RGJFCon5/
!
vrf instance MGMT
!
interface Ethernet1
   description P2P_LINK_TO_SUPER-SPINE1_Ethernet1
   no switchport
   ip address 10.0.1.1/31
   service-profile blah
!
interface Ethernet2
   description P2P_LINK_TO_SUPER-SPINE2_Ethernet1
   no switchport
   ip address 10.0.1.65/31
   service-profile blah
!
interface Ethernet3
   description P2P_LINK_TO_POD01-LEAF1A_Ethernet1
   no switchport
   ip address 10.0.3.0/31
   service-profile blah
!
interface Ethernet4
   description P2P_LINK_TO_POD01-LEAF1B_Ethernet1
   no switchport
   ip address 10.0.3.4/31
   service-profile blah
!
interface Ethernet5
   description P2P_LINK_TO_POD01-LEAF2A_Ethernet1
   no switchport
   ip address 10.0.3.8/31
   service-profile blah
!
interface Ethernet6
   description P2P_LINK_TO_POD01-LEAF2B_Ethernet1
   no switchport
   ip address 10.0.3.12/31
   service-profile blah
!
interface Ethernet7
!
interface Ethernet8
!
interface Loopback0
   description EVPN_Overlay_Peering
   ip address 10.1.2.1/32
!
interface Management1
   description oob_management
   vrf MGMT
   ip address 192.168.1.3/24
!
ip routing
no ip routing vrf MGMT
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 10.1.2.0/24 le 32
!
ip route vrf MGMT 0.0.0.0/0 192.168.1.254
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
!
router bgp 65100
   router-id 10.1.2.1
   no bgp default ipv4-unicast
   distance bgp 20 200 200
   graceful-restart restart-time 300
   graceful-restart
   maximum-paths 4 ecmp 4
   neighbor EVPN-OVERLAY-PEERS peer group
   neighbor EVPN-OVERLAY-PEERS next-hop-unchanged
   neighbor EVPN-OVERLAY-PEERS update-source Loopback0
   neighbor EVPN-OVERLAY-PEERS bfd
   neighbor EVPN-OVERLAY-PEERS ebgp-multihop 15
   neighbor EVPN-OVERLAY-PEERS password 7 q+VNViP5i4rVjW1cxFv2wA==
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor IPv4-UNDERLAY-PEERS peer group
   neighbor IPv4-UNDERLAY-PEERS password 7 AQQvKeimxJu+uGQ/yYvv9w==
   neighbor IPv4-UNDERLAY-PEERS send-community
   neighbor IPv4-UNDERLAY-PEERS maximum-routes 12000
   neighbor 10.0.1.0 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.1.0 remote-as 65001
   neighbor 10.0.1.64 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.1.64 remote-as 65001
   neighbor 10.0.3.1 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.3.1 remote-as 65101
   neighbor 10.0.3.5 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.3.5 remote-as 65101
   neighbor 10.0.3.9 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.3.9 remote-as 65102
   neighbor 10.0.3.13 peer group IPv4-UNDERLAY-PEERS
   neighbor 10.0.3.13 remote-as 65102
   redistribute connected route-map RM-CONN-2-BGP
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
      no neighbor IPv4-UNDERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
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
Hardware MAC address: 50ba.007d.9528
System MAC address: 50ba.007d.9528

Software image version: 4.25.0F
Architecture: i686
Internal build version: 4.25.0F-19426669.4250F
Internal build ID: 3e3fd8c9-cd7e-43fc-b5c7-4bd41eb55161

Uptime: 0 weeks, 0 days, 9 hours and 26 minutes
Total memory: 4008608 kB
Free memory: 3141276 kB
```
