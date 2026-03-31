# Enterprise-LAN-Security-Assessment

## Overview

This project demonstrates the design, implementation, and security assessment of a multi-site enterprise network using Cisco Packet Tracer.

The network was designed with three separate LANs connected by routers and switches. The project includes IP addressing, static routing, MAC address verification, HTTP and HTTPS testing, SSH access testing, and Shellshock vulnerability analysis.

The purpose of this lab was to understand how enterprise networks are built, how communication flows between devices, and how insecure services can be abused by attackers.

---

## Objectives

* Build a multi-LAN enterprise network in Cisco Packet Tracer
* Configure routers, switches, PCs, and a server
* Assign IP addresses and default gateways
* Configure static routing between networks
* Verify connectivity with ping tests
* Examine switch MAC address tables
* Compare HTTP vs HTTPS
* Compare SSH vs Telnet
* Compare TCP vs UDP
* Demonstrate and analyze the Shellshock vulnerability
* Recommend mitigation strategies and security improvements

---

## Network Topology

The network consists of three different LAN segments:

| Network        | Subnet          |
| -------------- | --------------- |
| IT Network     | 10.1.10.0/24    |
| OT Network     | 192.168.50.0/24 |
| Remote Network | 172.16.5.0/24   |

Devices included:

* 3 Routers
* 3 Switches
* 6 PCs
* 1 Server

## Topology Screenshot

![Topology](proof/topology.png)

---

## Routing Configuration

Static routes were configured on all routers so that each LAN could communicate with the others.

### Router Configuration Screenshots

![Router 1](proof/route1.png)

![Router 2](proof/route2.png)

![Router 3](proof/route3.png)

---

## MAC Address Table Verification

The MAC address table on the switches was used to verify that the switches learned the MAC addresses of connected devices.

![MAC Address Table](proof/MACaddress.png)

---

## Connectivity Testing

Connectivity was verified using ping commands between:

* PCs and default gateways
* PCs and the server
* Different LAN networks

The successful ping results confirmed that routing and communication between all networks were functioning correctly.

---

## HTTP and HTTPS Testing

The server was configured with web services and tested using both HTTP and HTTPS.

### HTTP Screenshot

![HTTP](proof/http.png)

### HTTPS Screenshot

![HTTPS](proof/https.png)

### HTTP vs HTTPS

HTTP sends data in plaintext and can be intercepted easily.

HTTPS encrypts communication using TLS/SSL, making it much safer for users because attackers cannot easily read or modify transmitted information.

---

## SSH Testing

SSH was used to demonstrate secure remote access to network devices.

![SSH](proof/SSH.png)

### SSH vs Telnet

SSH encrypts both credentials and session traffic.

Telnet sends usernames and passwords in plaintext, making it insecure in enterprise environments.

---

## Shellshock Vulnerability Demonstration

The project also included a demonstration of the Shellshock vulnerability.

The Shellshock exploit targets vulnerable Bash CGI scripts on Linux web servers. A specially crafted HTTP request can allow attackers to execute remote commands on the server.

![Shellshock](proof/Shellshock.png)

### Potential Impact

* Unauthorized remote access
* Data theft
* Malware installation
* Lateral movement across the network
* Disruption of OT systems and SCADA devices

### Recommended Mitigations

* Patch Bash immediately
* Disable unnecessary CGI scripts
* Restrict remote access
* Segment OT and IT networks
* Use firewalls and IDS/IPS tools
* Monitor logs for suspicious activity

---

## TCP vs UDP

TCP is connection-oriented and reliable because it confirms delivery and retransmits lost packets.

UDP is faster but connectionless and does not guarantee delivery.

TCP is commonly used for:

* HTTP
* HTTPS
* SSH

UDP is commonly used for:

* SNMP
* Streaming
* VoIP

---

## OSI Layer Mapping

| Layer                 | Example from Lab               |
| --------------------- | ------------------------------ |
| Layer 1 - Physical    | Cables, routers, switches, PCs |
| Layer 2 - Data Link   | Switch MAC address tables      |
| Layer 3 - Network     | IP addresses and routing       |
| Layer 4 - Transport   | TCP and UDP                    |
| Layer 7 - Application | HTTP, HTTPS, SSH               |

---

## Files Included

```text
Enterprise-LAN-Security-Assessment/
│
├── README.md
├── Lab04-Enterprise-LAN-Security-Report.pdf
│
└── proof/
    ├── topology.png
    ├── route1.png
    ├── route2.png
    ├── route3.png
    ├── MACaddress.png
    ├── http.png
    ├── https.png
    ├── SSH.png
    ├── Shellshock.png
    ├── brief1.png
    ├── brief2.png
    └── brief3.png
```

---

## Key Takeaways

This project demonstrated the importance of secure protocols, proper routing, network segmentation, and vulnerability management.

The lab showed how a vulnerable server can become an entry point into an enterprise network and why organizations must patch systems, secure remote access, and monitor network activity.

---

## Author

Mohammed Jarah
