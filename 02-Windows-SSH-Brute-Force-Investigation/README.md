# Project 02 – Windows SSH Brute Force Investigation

## Project Overview

This project demonstrates how to investigate multiple failed SSH authentication attempts followed by a successful login using Windows Security Event Logs.

The investigation was conducted in a controlled SOC home lab consisting of:

- Windows 10 Home
- Kali Linux
- OpenSSH Server
- Sysmon
- Windows Event Viewer
- Oracle VirtualBox

The objective was to simulate suspicious authentication activity and investigate it using native Windows logs.


## Scenario

A Windows endpoint received multiple failed SSH authentication attempts targeting the local user account **jdoe**.

After several failed attempts, a successful authentication occurred.

This behavior is commonly associated with password guessing or brute-force attacks and should be investigated by a SOC analyst.


## Objectives

- Generate Windows authentication events
- Investigate failed logins
- Investigate successful logins
- Build an event timeline
- Assess the severity
- Recommend containment actions


## Environment

| Component | Value |
|-----------|-------|
| Windows Host | FINANCE-PC-07 |
| Operating System | Windows 10 Home |
| Attacker Machine | Kali Linux |
| Windows IP | 192.168.56.20 |
| Kali IP | 192.168.56.10 |
| Service | OpenSSH |


## Tools Used

- Oracle VirtualBox
- Windows Event Viewer
- Windows Security Logs
- Sysmon
- OpenSSH Server
- Kali Linux
- SSH


## Investigation Summary

The investigation identified multiple failed SSH authentication attempts against the **jdoe** account.

Windows generated Event ID **4625** for failed logins and Event ID **4624** for the successful authentication.

Analysis of the event details confirmed that authentication was handled by the OpenSSH service (`sshd.exe`).

The activity is consistent with password guessing or brute-force behavior within a controlled lab environment.


## Evidence Collected

- Windows Security Logs
- Event ID 4625
- Event ID 4624
- OpenSSH Authentication Events
- Screenshots
- Event Log Export (.evtx)


## Skills Demonstrated

- Windows Log Analysis
- Event Viewer Investigation
- Authentication Analysis
- Incident Response
- Security Event Correlation
- Documentation
