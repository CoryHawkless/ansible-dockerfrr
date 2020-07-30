
Example  server with loads of things going on

config_network_interfaces: true
enable_configured_interfaces_after_defining: false
network_interfaces:
 - name: 'enp3s0f0'
   configure: true
   method: 'static'
   address: '172.25.112.184'
   #gateway: '172.25.112.1'
   netmask: '255.255.254.0'
   enable: true
 - name: 'enp3s0f1'
   configure: true
   enable: false
   method: 'manual'
 - name: 'enp3s0f2'
   configure: true
   enable: false
   method: 'manual'
 - name: 'enp3s0f3'
   configure: true
   enable: false
   method: 'manual'

 - name: 'ens2f0'
   comment: "Link to 40G Switch"
   auto_bgp_interface: true
   configure: true
   method: 'static'
   address: '{{host_loopback_IP}}'
   netmask: '255.255.255.255'
   enable: true

 - name: 'ens2f1'
   comment: "Link to 10G Switch"
   configure: true
   method: 'manual'
   enable: true

 - name: 'ens3f0'
   comment: "Link to 40G Switch"
   auto_bgp_interface: true
   configure: true
   method: 'static'
   address: '{{host_loopback_IP}}'
   netmask: '255.255.255.255'
   enable: true

 - name: 'ens3f1'
   comment: "Link to 10G Switch"
   configure: true
   method: 'manual'
   enable: true


dns_nameservers:
  - '172.25.110.2'
  - '172.20.0.2'
pri_domain_name: 'bfn.local'

host_loopback_IP: 172.25.4.31
host_ASN:	64653



Example network, no bond, docker frr
host_loopback_IP: 172.25.4.20
host_loopback_IP_v6: 2405:6680:8000:10::4:10
host_ASN:	64642

OOBNET_IP: 172.25.112.174
OOBNET_Netmask: 23
OOBNET_NIC: enp2s0f0

autobgp_interfaces:
 - name: 'enp2s0f1'
   force10G: True
   mtu: 9000
 - name: 'enp2s0f4'
   force10G: True
   mtu: 9000

Example configuration for Dell s6000-ON running Openswitch
host_loopback_IP: 172.25.9.3
host_loopback_IP_v6: 2000:3000:8000:10::9:3
host_ASN:    64661

OOBNET_IP: 172.25.112.196
OOBNET_Netmask: 23

network_interface_breakout_with_vlans:
 - name: 'e101-002-1'
   mtu: 9000
   force10G: True
   vlans:
    - '1001'
    - '1005'
    - '1009'
    - '1013'

 - name: 'e101-002-2'
   mtu: 9000
   force10G: True
   vlans:
    - '1002'
    - '1006'
    - '1010'
    - '1014'

 - name: 'e101-002-3'
   mtu: 9000
   force10G: True
   vlans:
    - '1003'
    - '1007'
    - '1011'
    - '1015'

 - name: 'e101-002-4'
   mtu: 9000
   force10G: True
   vlans:
    - '1004'
    - '1008'
    - '1012'
    - '1016'



 - name: 'e101-003-1'
   mtu: 9000
   force10G: True
   vlans:
    - '1017'
    - '1021'
    - '1025'
    - '1029'

 - name: 'e101-003-2'
   mtu: 9000
   force10G: True
   vlans:
    - '1018'
    - '1022'
    - '1026'
    - '1030'

 - name: 'e101-003-3'
   mtu: 9000
   force10G: True
   vlans:
    - '1019'
    - '1023'
    - '1027'
    - '1031'

 - name: 'e101-003-4'
   mtu: 9000
   force10G: True
   vlans:
    - '1020'
    - '1024'
    - '1028'
    - '1032'





 - name: 'e101-004-1'
   mtu: 9000
   force10G: True
   vlans:
    - '1033'
    - '1037'
    - '1041'
    - '1045'

 - name: 'e101-004-2'
   mtu: 9000
   force10G: True
   vlans:
    - '1034'
    - '1038'
    - '1042'
    - '1046'

 - name: 'e101-004-3'
   mtu: 9000
   force10G: True
   vlans:
    - '1035'
    - '1039'
    - '1043'
    - '1047'

 - name: 'e101-004-4'
   mtu: 9000
   force10G: True
   vlans:
    - '1036'
    - '1040'
    - '1044'
    - '1048'





 - name: 'e101-005-1'
   mtu: 9000
   force10G: True
   vlans:
    - '1049'
    - '1053'
    - '1057'
    - '1061'

 - name: 'e101-005-2'
   mtu: 9000
   force10G: True
   vlans:
    - '1050'
    - '1054'
    - '1058'
    - '1062'

 - name: 'e101-005-3'
   mtu: 9000
   force10G: True
   vlans:
    - '1051'
    - '1055'
    - '1059'
    - '1063'

 - name: 'e101-005-4'
   mtu: 9000
   force10G: True
   vlans:
    - '1052'
    - '1056'
    - '1060'
    - '1064'




 - name: 'e101-006-1'
   mtu: 9000
   force10G: True
   vlans:
    - '1065'
    - '1069'

 - name: 'e101-006-2'
   force10G: True
   mtu: 9000
   vlans:
    - '1066'
    - '1070'

 - name: 'e101-006-3'
   force10G: True
   mtu: 9000
   vlans:
    - '1067'
    - '1071'

 - name: 'e101-006-4'
   force10G: True
   mtu: 9000
   vlans:
    - '1068'
    - '1072'


autobgp_interfaces:


 - name: 'e101-007-1'
   mtu: 9000
   force10G: True
 - name: 'e101-007-2'
   mtu: 9000
   force10G: True
 - name: 'e101-007-3'
   mtu: 9000
   force10G: True
 - name: 'e101-007-4'
   mtu: 9000
   force10G: True

 - name: 'e101-008-1'
   mtu: 9000
   force10G: True
 - name: 'e101-008-2'
   mtu: 9000
   force10G: True
 - name: 'e101-008-3'
   mtu: 9000
   force10G: True
 - name: 'e101-008-4'
   mtu: 9000
   force10G: True

 - name: 'e101-009-1'
   mtu: 9000
   force10G: True
 - name: 'e101-009-2'
   mtu: 9000
   force10G: True
 - name: 'e101-009-3'
   mtu: 9000
   force10G: True
 - name: 'e101-009-4'
   mtu: 9000
   force10G: True

 - name: 'e101-010-1'
   mtu: 9000
   force10G: True
 - name: 'e101-010-2'
   mtu: 9000
   force10G: True
 - name: 'e101-010-3'
   mtu: 9000
   force10G: True
 - name: 'e101-010-4'
   mtu: 9000
   force10G: True




 - name: 'e101-013-0'
   mtu: 9000
 - name: 'e101-014-0'
   mtu: 9000
 - name: 'e101-015-0'
   mtu: 9000
 - name: 'e101-016-0'
   mtu: 9000
 - name: 'e101-017-0'
   mtu: 9000

 - name: 'e101-019-0'
   mtu: 9000
 - name: 'e101-020-0'
   mtu: 9000
 - name: 'e101-021-0'
   mtu: 9000

 - name: 'e101-027-0'
   mtu: 9000
   auto40G: True
 - name: 'e101-028-0'
   mtu: 9000
   auto40G: True
 - name: 'e101-029-0'
   mtu: 9000
   auto40G: True
 - name: 'e101-030-0'
   mtu: 9000
   auto40G: True
 - name: 'e101-031-0'
   mtu: 9000
   auto40G: True
 - name: 'e101-032-0'
   mtu: 9000
   auto40G: True

breakout_ports:
 - name: 'e101-001-0'
 - name: 'e101-002-0'
 - name: 'e101-003-0'
 - name: 'e101-004-0'
 - name: 'e101-005-0'
 - name: 'e101-006-0'
 - name: 'e101-007-0'
 - name: 'e101-008-0'
 - name: 'e101-009-0'
 - name: 'e101-010-0'

 - name: 'e101-018-0'

 - name: 'e101-026-0'

addressed_interfaces:
 - name: 'e101-026-1'
   mtu: 9000
   ip_address: '10.251.251.21'
   ip_netmask: '30'
   force10G: True

 - name: 'e101-018-1'
   mtu: 9000
   ip_address: '10.251.251.25'
   ip_netmask: '30'
   force10G: True

frr_other_peers:
 - name: "Services Router"
   ip: "10.251.251.22"
   remote_ASN: "64700"
