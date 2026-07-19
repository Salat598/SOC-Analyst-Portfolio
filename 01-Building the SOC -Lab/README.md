# Building My SOC Home Lab

## Objective

The objective of this project was to build a realistic Security Operations Center (SOC) home lab capable of generating and investigating real security events.

The lab allows safe simulation of attacks while collecting Windows logs for forensic analysis.

---

# Hardware

Host Machine

- Intel Core i5-8250U
- 8 GB RAM
- Windows 11

---

# Software Used

- Oracle VirtualBox
- Windows 10 Home
- Kali Linux
- Sysmon
- OpenSSH Server
- Windows Event Viewer

---

# Network Design

The lab uses two network adapters.

Adapter 1

Purpose:

Internet connectivity using NAT.

Adapter 2

Purpose:

Private communication between Kali Linux and Windows using an Internal Network.

Network Name

SOC-LAB

---

# IP Addressing

Windows

192.168.56.20

Kali

192.168.56.10

---

# Windows Configuration

The following tasks were completed.

- Installed Windows 10
- Installed VirtualBox Guest Additions
- Renamed computer to FINANCE-PC-07
- Installed Sysmon
- Installed OpenSSH Server
- Enabled Windows Firewall SSH rule
- Verified Windows Security Logs
- Verified Sysmon Operational Logs

---

# Kali Configuration

The following tasks were completed.

- Installed Kali Linux
- Configured static IP
- Verified SSH connectivity
- Connected to Windows successfully

---

# Connectivity Test

Windows successfully communicated with Kali.

Kali successfully communicated with Windows.

Ping Results

Windows → Kali

Successful

Kali → Windows

Successful

SSH Test

Successful

---

# Outcome

The SOC lab is fully operational and capable of generating Windows Security events for blue team investigations.
