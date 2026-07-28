# Project 3 – PowerShell Reconnaissance Investigation

## Objective
Investigate a suspicious PowerShell execution using Microsoft Sysmon.

The objective was to determine:

- Who executed PowerShell
- What commands were executed
- Whether the activity was malicious
- Map the observed behavior to the MITRE ATT&CK Framework

## Lab Environment

Host Machine
- Windows 11

Virtual Machines
- Windows 10
    - Hostname: FINANCE-PC-07
    - Sysmon Installed
    - OpenSSH Enabled

- Kali Linux
    - Used as Analyst Workstation

## Tools

- Microsoft Sysmon
- Event Viewer
- Windows PowerShell
- MITRE ATT&CK

## Skills Demonstrated

- Process Creation Analysis
- Parent/Child Process Investigation
- MITRE ATT&CK Mapping
- Windows Event Analysis
- Timeline Creation
- Incident Reporting
