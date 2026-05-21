# 🛡️ Enterprise ACL + DHCP Security Lab

## 📌 Project Overview

This project demonstrates an enterprise network implementation using:

- VLAN segmentation
- Inter-VLAN Routing
- DHCP services
- Standard ACL
- Extended ACL
- SSH Security
- Router-on-a-Stick architecture

The goal of this lab is to simulate a secure enterprise environment with multiple departments and controlled network access policies.

---

# 🖧 Network Topology

```text
                    R1
                     |
                  g0/0
                     |
                 fa0/1 TRUNK
                    SW1

-------------------------------------------------

fa0/2   -> PC0  (HR VLAN10)
fa0/3   -> PC1  (HR VLAN10)

fa0/4   -> PC2  (IT VLAN20)
fa0/5   -> PC3  (IT VLAN20)

fa0/6   -> PC4  (Finance VLAN30)
fa0/7   -> PC5  (Finance VLAN30)

fa0/8   -> PC6  (Guest VLAN40)
fa0/9   -> PC7  (Guest VLAN40)

fa0/10  -> PC8  (Server VLAN50)
fa0/11  -> PC9  (Server VLAN50)
```

---

# 🌐 VLAN Design

| VLAN | Department | Network |
|---|---|---|
| 10 | HR | 192.168.10.0/24 |
| 20 | IT | 192.168.20.0/24 |
| 30 | Finance | 192.168.30.0/24 |
| 40 | Guest | 192.168.40.0/24 |
| 50 | Server | 192.168.50.0/24 |

---

# ⚙️ Technologies Used

- Cisco IOS
- Cisco Packet Tracer
- VLAN
- Trunking
- Router-on-a-Stick
- DHCP
- Standard ACL
- Extended ACL
- SSH
- Network Segmentation

---

# 🔐 Security Policies

## IT VLAN
- Full network access
- SSH access allowed

## HR VLAN
- Limited access to servers

## Finance VLAN
- Restricted communication

## Guest VLAN
- SSH blocked
- ICMP blocked
- No access to Server VLAN

---

# 🧪 Verification Commands

```bash
show vlan brief
show interfaces trunk

show ip dhcp binding
show ip dhcp pool

show access-lists

show running-config

show ip interface brief
```

---

# 📸 Verification Screenshots

- VLAN Table
- Trunk Interfaces
- DHCP Bindings
- ACL Hit Counters
- SSH Success
- SSH Denied
- Successful Ping Tests
- Final Topology

---

# 🎯 Skills Demonstrated

- VLAN Configuration
- Inter-VLAN Routing
- DHCP Configuration
- ACL Implementation
- SSH Security
- Enterprise Network Segmentation
- Cisco IOS CLI
- Network Security Fundamentals

---

# 📂 Project Structure

```text
Enterprise-ACL-DHCP-Lab/
│
├── README.md
├── router-configs.md
│
├── configs/
│   └── R1.txt
│
├── screenshots/
│   ├── vlan-table.png
│   ├── trunk.png
│   ├── dhcp-binding.png
│   ├── acl-hit.png
│   ├── ssh-success.png
│   ├── ssh-denied.png
│   └── topology.png
│
├── topology/
│   └── topology.png
│
└── packet-tracer/
    └── enterprise-acl-dhcp-lab.pkt
```

---

# 👨‍💻 Author

Junior Network Engineer  
Cisco & Network Security Enthusiast
