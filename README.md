# Network Analysis with Wireshark

## Overview
This project captures live network packets using **Wireshark**, filters them by protocol, and analyzes traffic to identify HTTP, DNS, ICMP, and TCP communications.

---

## Tools Used
- **Wireshark** (free network protocol analyzer)

---

## Basic Wireshark Concepts
- **Packet**: A unit of data transmitted over a network.
- **Protocol**: A set of rules for communication (e.g., HTTP, DNS).
- **Filter**: A query in Wireshark to display only certain packet types.
- **Frame**: The physical layer data containing the packet.

---
---

## Network Interface Findings
During the initial Wireshark setup, we identified multiple network interfaces available on the system.  
These included both **Wi-Fi** and **Ethernet** adapters.

- **Wi-Fi Adapter** → Captures packets over wireless networks.
- **Ethernet Adapter** → Captures packets over wired connections.
- Some virtual or loopback interfaces may also appear, depending on installed software.

**Observation:**  
For this capture session, the **active Wi-Fi interface** was selected to monitor live traffic.

**Screenshot:** [View](./screenshots/) **network_interfaces.png**

---


---

## Protocol Findings

### 1. HTTP (Hypertext Transfer Protocol)
- **Filter**: `http`
- **Example Packet**: HTTP/1.1 404 Not Found
- **Source**: 23.215.0.138  
- **Destination**: 192.168.1.39  
- **Details**: The client requested a webpage; server responded with 404 error.  
- **Screenshot**: [View](./screenshots/)  **http.png**

---

### 2. DNS (Domain Name System)
- **Filter**: `dns`
- **Example Packet**: Query for domain `example.com`
- **Source**: 192.168.1.39  
- **Destination**: 8.8.8.8 (Google DNS)  
- **Details**: Resolving domain name to IP address.  
- **Screenshot**: [View](./screenshots/)  **dns.png**

---

### 3. ICMP (Internet Control Message Protocol)
- **Filter**: `icmp`
- **Example Packet**: Echo request (ping) to `8.8.8.8`
- **Source**: 192.168.1.39  
- **Destination**: 8.8.8.8  
- **Details**: Used to test network connectivity.  
- **Screenshot**: [View](./screenshots/)  **icmp.png**

---

### 4. TCP (Transmission Control Protocol)
- **Filter**: `tcp`
- **Example Packet**: TCP handshake SYN
- **Source**: 192.168.1.39  
- **Destination**: 23.215.0.138  
- **Details**: Establishing a reliable connection between client and server.  
- **Screenshot**: [View](./screenshots/)  **tcp.png**

---

## Files in This Repository
- **`network_capture.pcapng`** → Original capture file
- **`screenshots/`** → Images of protocol packets
- **`README.md`** → Report & findings

---

## How to Open the Capture
1. Install [Wireshark](https://www.wireshark.org/).
2. Open `network_capture.pcapng`.
3. Use filters like `http`, `dns`, `icmp`, `tcp` to view each protocol.

---
