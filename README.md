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
Wireshark shows that 192.168.31.1 responded to the SYN probe with a SYN-ACK packet, meaning the port (53) is open and accepting connections.

### Screenshot 3: RST-ACK Response (Closed Port)
This shows that some devices responded with a TCP Reset (RST), which indicates the scanned port is closed.

