## 📌 BASIC CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `enable` | `Switch>enable` | Access privileged EXEC mode |
| `conf t` | `Switch# configure terminal` | Access global configuration mode |
| `hostname S1` | `S1(config)# hostname S1` | Set hostname to S1 |
| `no ip domain-lookup` | `S1(config)# no ip domain-lookup` | Disable DNS lookup |
| `enable secret <pwd>` | `S1(config)# enable secret <pwd>` | Set encrypted privileged EXEC password |
| `exit` | `exit` | Exit current mode |
| `end` | `end` | Exit to privileged EXEC mode |
| `copy run start` | `S1# copy running-config startup-config` | Save running config to startup file |
| `reload` | `S1# reload` | Reboot device |
| `erase startup-config` | `S1# erase startup-config` | Remove saved startup config |
| `banner motd #<message>#` | `S1(config)# banner motd #<message>#` | Set message of the day |

## 🔐 CONSOLE & VTY LINES
| Shortcut | Command | Description |
|----------|---------|-------------|
| `line con 0` | `S1(config)# line con 0` | Enter console line configuration mode |
| `line vty 0 4` | `S1(config)# line vty 0 4` | Configure Telnet/SSH access |
| `password <pwd>` | `S1(config-line)# password <pwd>` | Set line password |
| `exec-timeout 5 0` | `S1(config-line)# exec-timeout 5 0` | Auto logout after 5 mins of inactivity |
| `login` | `S1(config-line)# login` | Require login using configured password |
| `logging synchronous` | `S1(config-line)# logging synchronous` | Prevents interruptions by log messages |
| `service password-encryption` | `S1(config)# service password-encryption` | Encrypt all plaintext passwords |

## 🧠 INTERFACE CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `int g0/0` | `R1(config)# int g0/0` | Enter G0/0 interface config |
| `description <text>` | `R1(config-if)# description <text>` | Set interface description |
| `ip address <ip> <mask>` | `R1(config-if)# ip address <ip> <mask>` | Assign IP and subnet mask of interface |
| `no ip address` | `R1(config-if)# no ip address` | Remove ip address from interface |
| `no shut` | `R1(config-if)# no shutdown` | Enable interface |
| `int s0/0/0` | `R1(config)# int s0/0/0` | Enter Serial0/0/0 config |
| `clock rate 128000` | `R1(config-if)# clock rate 128000` | Set clock rate for DCE interfaces |
| `bandwidth 128` | `R1(config-if)# bandwidth 128` | Set bandwidth value for metrics (one-side) |
| `ip ospf cost <x>` | `R1(config-if)# ip ospf cost <x>` | Set OSPF cost manually (one-side) |
| `int lo0` | `R1(config)# int lo0` | Enter loopback interface configuration |
| `show int <x>` | `R1# show int <x>` | Show detailed info for interface x |

## 📶 VLAN CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `vlan <x>` | `S1(config)# vlan <x>` | Create VLAN and enter |
| `no vlan <x>` | `S1(config)# no vlan <x>` | Delete VLAN |
| `name <name>` | `S1(config-vlan)# name <name>` | Name the VLAN |
| `int vlan <x>` | `S1(config)# int vlan <x>` | Enter VLAN interface config mode |
| `ip address <ip> <mask>` | `S1(config-if)# ip address <ip> <mask>` | Assign IP to VLAN interface |
| `interface range f0/11-24` | `S1(config)# interface range f0/11-24` | Configure multiple interfaces |
| `switchport mode access` | `S1(config-if)# switchport mode access` | Set port to access VLAN |
| `switchport mode trunk` | `S1(config-if)# switchport mode trunk` | Set port to trunk mode |
| `switchport mode dynamic desirable` | `S1(config-if)# switchport mode dynamic desirable` | Auto-negotiate trunk if other side agrees |
| `switchport access vlan <x>` | `S1(config-if)# switchport access vlan <x>` | Assign interface to VLAN |
| `no switchport access vlan` | `S1(config-if)# no switchport access vlan` | Remove VLAN assignment |
| `show interfaces trunk` | `S1# show interfaces trunk` | Display trunk interfaces |
| `show ip int brief` | `S1# show ip interface brief` | Show interface status summary |
| `show vlan (brief)?` | `S1# show vlan (brief)?` | Show interface on vlan |
| `show flash` | `S1# show flash` | Show flash contents, e.g., vlan.dat |
| `delete vlan.dat` | `S1# delete vlan.dat` | Delete VLAN database |

## 🚦 STATIC ROUTING
| Shortcut | Command | Description |
|----------|---------|-------------|
| `ip route <d> <m> <nexthop int of other router>` | `R1(config)# ip route <dest> <mask> <nexthop>` | Recursive static route |
| `ip route <d> <m> <exit int of this router >` | `R1(config)# ip route <dest> <mask> <exit int>` | Directly connected static route |
| `ip route 0.0.0.0 0.0.0.0 <x>` | `R1(config)# ip route 0.0.0.0 0.0.0.0 <x>` | Default route|

## 🧭 OSPF CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `router ospf <process_id>` | `R1(config)# router ospf 1` | Enable&Advertise OSPF process_id |
| `network <network_ip> <wildcard> area <x>` | `R1(config-router)# network <network_ip> <inv-mask> area <x>` | Assign network to OSPF area |
| `router-id <id>` | `R1(config-router)# router-id <id>` | Manually assign router ID |
| `clear ip ospf process` | `R1(config)# clear ip ospf process` | To enable router-id ip |
| `passive-interface <x>` | `R1(config-router)# passive-interface <x>` | Disable hello packets on interface |
| `passive-interface default` | `R1(config-router)# passive-interface default` | Make all interfaces passive |
| `no passive-interface <x>` | `R1(config-router)# no passive-interface <x>` | Enable hello packets again on interface |
| `auto-cost reference-bandwidth 10000` | `R1(config-router)# auto-cost reference-bandwidth 10000` | Adjust cost calculation based on bandwidth |
| `show ip ospf neighbor` | `R1# show ip ospf neighbor` | List other routers in network as neighbor |
| `show ip ospf` | `R1# show ip ospf` | Examine the OSPF process ID and router ID |
| `show ip ospf interface <int?>` | `R1# show ip ospf interface <int?>` | Show OSPF settings for interface, Cost|
| `show ip route ospf` | `R1# show ip route ospf` | Display OSPF learned routes |
| `show ip protocols` | `R1# show ip protocols` | Verify OSPF configuration information |

## 📦 RIP CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `router rip` | `R1(config)# router rip` | Enable RIP routing protocol |
| `version 2` | `R1(config-router)# version 2` | Use RIP v2 |
| `network <ip>` | `R1(config-router)# network <ip>` | Advertise network in RIP |
| `no auto-summary` | `R1(config-router)# no auto-summary` | Disable automatic summarization |
| `default-information originate` | `R2(config-router)# default-information originate` | Advertise default route via RIP |

## 🖧 DHCP CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `ip dhcp excluded-address <start> <end>` | `R1(config)# ip dhcp excluded-address <x> <y>` | Exclude ip address range |
| `ip dhcp pool <name>` | `R1(config)# ip dhcp pool <name>` | Create DHCP pool |
| `network <ip> <mask>` | `R1(dhcp-config)# network <ip> <mask>` | Assign pool to network |
| `default-router <ip>` | `R1(dhcp-config)# default-router <ip>` | Set pool default gateway |
| `dns-server <ip>` | `R1(dhcp-config)# dns-server <ip>` | Set DNS server in pool |
| `int g0/0` | `R1(config)# int g0/0` | Enter G0/0 |
| `ip helper-address <ip>` | `R1(config-if)# ip helper-address <ip>` | Config helper address for G0/0 LAN |

## 🌍 NAT CONFIGURATION
| Shortcut | Command | Description |
|----------|---------|-------------|
| `ip nat inside source static <priv> <pub>` | `Gateway(config)# ip nat inside source static <priv> <pub>` | Create static one-to-one NAT mapping |
| `no ip nat inside source static <priv> <pub>` | `Gateway(config)# no ip nat inside source static <priv> <pub>` | Remove static NAT entry |
| `int <x>` → `ip nat inside` | `Gateway(config-if)# ip nat inside` | Mark interface as inside NAT |
| `int <y>` → `ip nat outside` | `Gateway(config-if)# ip nat outside` | Mark interface as outside NAT |
| `access-list <n> permit <ip> <wc>` | `Gateway(config)# access-list <n> permit <ip> <wildcard>` | ACL for NAT inside traffic |
| `ip nat pool <name> <start> <end> netmask <mask>` | `Gateway(config)# ip nat pool <name> <start> <end> netmask <mask>` | Create NAT public address pool |
| `ip nat inside source list <n> pool <name>` | `Gateway(config)# ip nat inside source list <n> pool <name>` | Apply NAT using ACL and pool |
| `show ip nat translations` | `Gateway# show ip nat translations` | View NAT mappings |
| `show ip nat statistics` | `Gateway# show ip nat statistics` | View NAT performance/usage |
| `clear ip nat translation *` | `Gateway# clear ip nat translation *` | Clear all NAT translations |

## 🕓 MISCELLANEOUS
| Shortcut | Command | Description |
|----------|---------|-------------|
| `clock set <time> <date>` | `R1# clock set 17:00:00 18 Feb 2013` | Set router's internal clock |
| `show` | `R1# show` | Generic show command |
| `show startup-config` | `R1# show startup-config` | Show saved configuration |
| `show ip route` | `R1# show ip route` | Show current routing table |
| `show int <x>` | `R1# show interface <x>` | Show details of an interface, Bandwidth |

