# Project 03 – Sysmon Process Creation Investigation

## Overview

This project demonstrates how Sysmon Event ID 1 (Process Creation) can be used to investigate processes executed on a Windows endpoint.

The investigation was performed in a SOC home lab built using VirtualBox, Windows 10, Kali Linux, and Sysmon.

The objective was to understand how Sysmon records process execution and how SOC analysts use this information to detect suspicious activity.

## Lab Environment

| Component | Details |
|-----------|---------|
| Host | Windows 11 |
| Virtualization | Oracle VirtualBox |
| Target VM | Windows 10 |
| Monitoring Tool | Sysmon |
| Attacker VM | Kali Linux |

## Objectives

- Understand Sysmon Event ID 1
- Investigate process creation
- Analyze parent-child relationships
- Examine command-line arguments
- Verify executable paths
- Review file hashes
- Map activity to MITRE ATT&CK

## Applications Executed

- Notepad
- Calculator
- Command Prompt
- PowerShell
## Evidence Collected

- Sysmon Event ID 1
- Process Name
- Parent Process
- Process GUID
- Command Line
- User
- SHA256 Hash
- Integrity Level
## Skills Demonstrated

- Endpoint Monitoring
- Windows Forensics
- Process Analysis
- Sysmon Investigation
- MITRE ATT&CK Mapping
- Incident Documentation
## Conclusion

Sysmon provides detailed endpoint telemetry that extends beyond Windows Security logs. By analyzing process creation events, SOC analysts can determine what applications were executed, how they were launched, and whether the behavior appears legitimate or suspicious.

This project established foundational skills in endpoint detection and investigation.
