# Zeek Intrusion Detection Project

**Author**: Brett Banks  
**Date**: June 1, 2025  
**Environment**: Kali Linux (Attacker) & Windows 10 (Victim)  
**Tools Used**: Zeek, Wireshark, tcpdump, FTP, nslookup, nmap  

##  Overview

This project simulates network-based attacks within a controlled virtual lab environment to demonstrate how packet captures (PCAPs) can be analyzed with Zeek and Wireshark. The focus is on identifying insecure protocols, extracting Indicators of Compromise (IOCs), and producing actionable insights in the context of security operations.

The lab specifically captures and analyzes FTP login activity using cleartext credentials, highlighting the risks of using unencrypted communication protocols.

##  Lab Configuration

| Component     | Description                                |
|--------------|--------------------------------------------|
| Kali Linux    | Attacker + Network Monitor (Zeek, Wireshark) |
| Windows 10    | Victim Machine with FTP Server              |
| Network Type  | VirtualBox Host-Only (192.168.84.0/24)      |
| Packet Capture| `tcpdump -i eth1 -w ftp_test.pcap`         |

##  Attack Simulation

- Attacker initiates an FTP connection to the Windows 10 target.
- Credentials used: `testuser` / `weakpass`
- The login was captured in a `.pcap` file and then analyzed using Zeek.

##  Zeek Log Analysis

Zeek processed the PCAP and generated logs including:

- `conn.log` – General connection metadata
- `packet_filter.log` – Packet capture filtering details
- (Optional) `ftp.log` – If FTP analyzer was activated manually

Key observation: FTP credentials were visible in cleartext.

##  Key Findings

| Threat                | Description                                                  |
|-----------------------|--------------------------------------------------------------|
| FTP Credential Leak   | FTP login details (user/pass) transmitted unencrypted        |
| MITRE ATT&CK Mapping  | T1078 – Valid Accounts                                        |
| Risk Impact           | Attackers could intercept credentials on flat networks       |



##  Outcomes

- Successfully simulated a network-based attack
- Captured evidence with `tcpdump`
- Detected and analyzed behavior using Zeek logs
- Produced a PDF report suitable for SOC analyst review or portfolio

##  Future Improvements

- Enable deeper logging via Zeek analyzers (e.g., full FTP analysis)
- Simulate DNS tunneling or port scanning behaviors
- Add automated Zeek scripts for threat correlation

##  License

MIT License – see [LICENSE](LICENSE) if applicable.

##  Tags

`zeek` `network-analysis` `pcap` `intrusion-detection` `ftp` `cybersecurity` `soc` `tcpdump`

