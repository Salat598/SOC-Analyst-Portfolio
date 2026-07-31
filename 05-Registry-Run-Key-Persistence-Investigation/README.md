# Project 4 - Registry Run Key Persistence Investigation

## Overview

This project demonstrates how attackers can establish persistence on a Windows endpoint by modifying Registry Run Keys.

A harmless persistence mechanism was created using PowerShell to launch Notepad automatically during user logon. The registry modification was detected using Microsoft Sysmon Event ID 13 and investigated following a SOC analyst workflow.


## Objectives

- Understand Windows Registry persistence
- Investigate Sysmon Event ID 13
- Analyze Registry Run Keys
- Map activity to MITRE ATT&CK
- Validate persistence
- Perform remediation
- Verify successful cleanup

## Lab Environment

Attacker Machine

- Kali Linux
- VirtualBox

Victim Machine

- Windows 10
- Microsoft Sysmon
- Windows Event Viewer
- PowerShell


## Persistence Technique

Registry Run Key

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

Value Created

NotepadLab

Executable

C:\Windows\System32\notepad.exe

## Detection

Data Source
Microsoft Sysmon
Event ID
13 – Registry Value Set
## Investigation Summary

PowerShell created a new Registry Run Key called NotepadLab.
The registry value configured Notepad.exe to execute automatically whenever the SOC1 user logged into Windows.
The activity matched the MITRE ATT&CK technique:
T1547.001 – Registry Run Keys / Startup Folder
The persistence mechanism was validated by signing out and back into Windows, confirming that Notepad launched automatically.
The Run Key was then removed and remediation was verified.
## Skills Demonstrated
- Registry Analysis
- Windows Forensics
- Persistence Detection
- Microsoft Sysmon
- Event Log Analysis
- PowerShell Investigation
- MITRE ATT&CK Mapping
- Incident Response
- Remediation Validation
## MITRE ATT&CK
Technique
T1547.001 – Registry Run Keys / Startup Folder
Tactic
Persistence
## Screenshots

- Registry creation command
- Sysmon Event ID 13
- Registry verification
- Notepad automatic execution


## Learning Outcome

This project demonstrates how persistence can be established, detected, investigated, validated and removed using Windows Registry analysis and Sysmon telemetry.
