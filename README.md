## Hotel-management-system-in-cisco-packet-tracer

Hotel Management System Network Design (Cisco Packet Tracer):

A complete enterprise-level hotel network infrastructure designed and simulated using Cisco Packet Tracer.
This project demonstrates real-world implementation of routing, segmentation, wireless access, security policies and access control across multiple hotel departments and floors.

The network is structured to ensure secure communication, departmental isolation and controlled internet/server access using a combination of OSPF routing, static routing, default routing, and extended ACLs.

 Project Objectives
* Design a scalable hotel network for multiple departments and floors
* Implement dynamic routing using OSPF
* Use static and default routing for edge and branch routers
* Provide secure WiFi access for lobby users
* Enforce inter-department communication rules using Extended Access Control Lists
* Simulate real enterprise network behavior with proper IP addressing and subnetting


 Network Architecture:
The network consists of:
* 17 Routers
* Multiple departmental LANs
* Wireless Router for lobby WiFi
* Core routing with OSPF Area 1
* Departmental routers connected via point-to-point /30 links
* LAN segments using /28 and /24 subnetting

 Departments Modeled:

| Department               | Network                         | Router          |
| ------------------------ | ------------------------------- | --------------- |
| Security                 | 192.168.16.0/28                 | Router-14       |
| Admin                    | 192.168.15.0/28                 | Router-13       |
| Office                   | 192.168.7.0/28                  | Router-7        |
| Store                    | 192.168.6.0/28                  | Router-8        |
| Reception                | 192.168.5.0/24                  | Router-6        |
| Lobby WiFi               | 192.168.17.0/24                 | Wireless Router |
| Server/Internet Backbone | 192.168.50.0/24, 192.168.8.0/24 | Router-17       |

---

Routing Implementation:

OSPF (Area 1):
Used in the core routers to dynamically exchange routes:
* Router-16
* Router-4

Static & Default Routing:
Used in departmental and edge routers to forward traffic toward the core network and internet/server backbone.

Wireless Network:
A wireless router is configured for lobby users:
* SSID: LobbyWiFi
* Password: hotel1234
* LAN: 192.168.17.1
* WAN: 192.168.5.5

Network Security (Extended ACL):
Extended ACL (Access List 100) is used to strictly control which department can communicate with another.

Communication Policy:

| From      | Allowed To                                  |
| --------- | ------------------------------------------- |
| Security  | Internet, Server                            |
| Admin     | Reception, Office, Server, Floors, Internet |
| Office    | Admin, Store, Server, Internet              |
| Store     | Office, Server, Internet                    |
| Reception | Admin, Server, Internet                     |

ACLs are applied inbound on departmental routers to filter unauthorized access.

Key Networking Concepts Demonstrated:
* OSPF Dynamic Routing
* Static Routing & Default Routes
* IP Subnetting (/30, /28, /24)
* Extended Access Control Lists
* Wireless Network Configuration
* Multi-router enterprise topology
* Departmental network segmentation
* Secure traffic flow design

Tools Used:
* Cisco Packet Tracer
* Cisco IOS CLI Configuration

Learning Outcomes:
This project reflects practical understanding of:
* Enterprise network design
* Secure inter-department communication
* Routing protocol implementation
* Realistic IP planning and subnetting
* Access control and traffic filtering

How to Use:
1. Open the `.pkt` file in Cisco Packet Tracer
2. Power on all routers
3. Verify routing tables using `show ip route`
4. Test connectivity using `ping` between allowed departments
5. Test blocked communication to observe ACL behavior

Author:
Nahida Akter Mohona
Department of CSE
Daffodil International University
