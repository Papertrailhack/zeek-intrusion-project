# Zeek Intrusion Detection Project

**Author**: Brett Banks  
**Environment**: Kali Linux (Attacker) & Windows 10 (Victim)  
**Date**: June 1, 2025  
**Tools Used**: Zeek, Wireshark, tcpdump, FTP, nslookup, nmap  

---

## 🔍 Project Overview

This project simulates common network-based attacks within a virtual lab to demonstrate how network traffic can be captured, analyzed, and reported using Zeek and Wireshark. The lab highlights the importance of monitoring cleartext protocols and extracting Indicators of Compromise (IOCs) from PCAP files.

---

## 🧪 Lab Setup

| Component      | Configuration                               |
|----------------|---------------------------------------------|
| Kali Linux     | Attacker and monitoring machine (Zeek, Wireshark) |
| Windows 10     | Victim machine with FTP service enabled     |
| Network Type   | Host-only VirtualBox adapter (192.168.84.0/24) |
| Capture Method | `tcpdump -i eth1 -w ftp_test.pcap`          |

---

## ⚙️ Attack Simulation

- **FTP Login (Cleartext)**  
  Attacker logs into Windows FTP service using fake credentials (`testuser / weakpass`).  
  Captured via `tcpdump` and analyzed with Zeek.

- **Zeek Analysis Output**  
  Logs such as `conn.log`, `ftp.log`, `packet_filter.log` were generated.  
  Credentials observed in plaintext.

---

## 📝 Key Findings

| Threat | Description |
|--------|-------------|
| **FTP Credential Exposure** | Username and password transmitted in plaintext |
| **Mitre ATT&CK Mapping** | T1078 – Valid Accounts |

---

## 📂 Project Structure

