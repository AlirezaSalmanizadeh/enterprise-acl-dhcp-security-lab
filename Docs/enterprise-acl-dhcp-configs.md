# 🔧 Enterprise ACL + DHCP Lab — Full Device Configurations

## 🛠 SW1 Configuration

```bash
enable
configure terminal

hostname SW1

vlan 10
name HR

vlan 20
name IT

vlan 30
name FINANCE

vlan 40
name GUEST

vlan 50
name SERVER

interface range fa0/2-3
switchport mode access
switchport access vlan 10

interface range fa0/4-5
switchport mode access
switchport access vlan 20

interface fa0/1
switchport mode trunk

end
write
```

---

## 🛠 R1 Configuration

```bash
enable
configure terminal

hostname R1

interface g0/0
no shutdown

interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

ip dhcp excluded-address 192.168.10.1 192.168.10.10
ip dhcp excluded-address 192.168.20.1 192.168.20.10
ip dhcp excluded-address 192.168.30.1 192.168.30.10
ip dhcp excluded-address 192.168.40.1 192.168.40.10
ip dhcp excluded-address 192.168.50.1 192.168.50.10

ip dhcp pool HR
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 8.8.8.8

ip domain-name enterprise.local

crypto key generate rsa
1024

username admin privilege 15 secret Cisco123

line vty 0 4
transport input ssh
login local

ip ssh version 2

access-list 10 permit 192.168.20.0 0.0.0.255

line vty 0 4
access-class 10 in

ip access-list extended GUEST_BLOCK

deny tcp 192.168.40.0 0.0.0.255 any eq 22
permit ip any any

interface g0/0.40
ip access-group GUEST_BLOCK in

end
write
```
