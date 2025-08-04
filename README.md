# TaskoneElevatelabs
# Task 1: Port Scanning & Network Reconnaissance

## 🔧 Tools Used
- Nmap
- Wireshark

---

## 📍 Objective
To scan the local network for open ports and analyze traffic to understand network exposure and service visibility.

---

## 🚀 Nmap Scan Command Used
    ```bash
    nmap -sS 192.168.1.0/24

---

## 🔍 Wireshark Analysis

### Screenshot 1: SYN Packets Sent
Wireshark captured TCP SYN packets from my machine to all hosts in the network. These packets are the first part of a TCP handshake and are used by Nmap to probe open ports.

### Screenshot 2: SYN-ACK Response (Open Port)
Wireshark shows that 192.168.**.* responded to the SYN probe with a SYN-ACK packet, meaning the port (53) is open and accepting connections.

### Screenshot 3: RST-ACK Response (Closed Port)
This shows that some devices responded with a TCP Reset (RST), which indicates the scanned port is closed.

> ⚠️ All IP addresses shown are part of a local, private test network (`192.168.31.0/24`). No public or sensitive data is exposed.

### 🔐 Security Risks Identified

- **192.168.31.1 (JioFiber Router)**
  - Port 80 (HTTP): Unencrypted; vulnerable to credential theft.
  - Ports 8080, 8443, 7443: Often expose admin panels. If not password-protected, can be critical.
  - Port 53: Can be abused for DNS attacks if open to public.

- **192.168.31.111 (Windows PC)**
  - Ports 135, 139, 445: Related to SMB and RPC services. Vulnerable to known exploits like EternalBlue.
  - UPnP ports (2869, 10243): Risky if device is accessible over the internet.
  - Dynamic ports (49152+): Should be monitored for unusual activity.
