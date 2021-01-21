# POD01-SUBLEAF1A Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 POD01-LEAF1A_Ethernet4
Et2                            up             up                 POD01-LEAF1B_Ethernet4
Et3                            up             up                 
Et4                            up             up                 
Et5                            up             up                 
Et6                            up             up                 
Et7                            up             up                 
Et8                            up             up                 
Ma1                            up             up                 oob_management
Po1                            up             up                 POD01-LEAF1A_Po4
Vl4092                         up             up                 L2LEAF_INBAND_MGMT
```
## show ip interface brief

```
Address 
Interface       IP Address          Status      Protocol         MTU    Owner   
--------------- ------------------- ----------- ------------- --------- ------- 
Management1     192.168.1.9/24      up          up              1500            
Vlan4092        10.160.255.8/24     up          up              1500
```
## show lldp neighbors

```
Last table change time   : 4:43:17 ago
Number of table inserts  : 20
Number of table deletes  : 9
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID       Neighbor Port ID    TTL 
---------- ------------------------ ---------------------- --- 
Et1           POD01-LEAF1A             Ethernet4           120 
Et2           POD01-LEAF1B             Ethernet4           120 
Ma1           ROUTE-SERVER1            Management1         120 
Ma1           SUPER-SPINE1             Management1         120 
Ma1           POD01-SPINE2             Management1         120 
Ma1           POD01-LEAF1A             Management1         120 
Ma1           POD01-LEAF2B             Management1         120 
Ma1           SUPER-SPINE2             Management1         120 
Ma1           POD01-SPINE1             Management1         120 
Ma1           POD01-LEAF2A             Management1         120 
Ma1           POD01-LEAF1B             Management1         120
```
## show running-config

```
! Command: show running-config
! device: POD01-SUBLEAF1A (vEOS, EOS-4.25.0F)
!
! boot system flash:/vEOS-lab.swi
!
vlan internal order ascending range 1006 1199
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname POD01-SUBLEAF1A
ip name-server vrf MGMT 1.2.3.4
!
ntp local-interface vrf MGMT Management1
ntp server vrf MGMT fr.pool.ntp.org
ntp server vrf MGMT uk.pool.ntp.org prefer
!
spanning-tree mode mstp
spanning-tree mst 0 priority 16384
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
vrf instance MGMT
!
interface Port-Channel1
   description POD01-LEAF1A_Po4
   switchport trunk allowed vlan 110-112,4092
   switchport mode trunk
   service-profile blah
!
interface Ethernet1
   description POD01-LEAF1A_Ethernet4
   channel-group 1 mode active
!
interface Ethernet2
   description POD01-LEAF1B_Ethernet4
   channel-group 1 mode active
!
interface Ethernet3
!
interface Ethernet4
!
interface Ethernet5
!
interface Ethernet6
!
interface Ethernet7
!
interface Ethernet8
!
interface Management1
   description oob_management
   vrf MGMT
   ip address 192.168.1.9/24
!
interface Vlan4092
   description L2LEAF_INBAND_MGMT
   ip address 10.160.255.8/24
!
ip routing
no ip routing vrf MGMT
!
ip route 0.0.0.0/0 10.160.255.1
ip route vrf MGMT 0.0.0.0/0 192.168.1.254
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
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
Hardware MAC address: 50ba.004e.a0e1
System MAC address: 50ba.004e.a0e1

Software image version: 4.25.0F
Architecture: i686
Internal build version: 4.25.0F-19426669.4250F
Internal build ID: 3e3fd8c9-cd7e-43fc-b5c7-4bd41eb55161

Uptime: 0 weeks, 0 days, 9 hours and 22 minutes
Total memory: 4008608 kB
Free memory: 3150628 kB
```
