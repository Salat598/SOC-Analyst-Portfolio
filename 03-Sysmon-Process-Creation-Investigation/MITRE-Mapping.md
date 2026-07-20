# MITRE ATT&CK Mapping

## Tactic

Execution

## Technique

T1204 – User Execution

## Description

User Execution occurs when an application or file is launched through direct user interaction.

During this project, Notepad, Calculator, Command Prompt and PowerShell were intentionally executed by the logged-in user, generating Sysmon Event ID 1 records.

## Data Sources

- Sysmon Process Creation
- Windows Event Logs

## Detection

Monitor Sysmon Event ID 1 for:

- Unusual parent-child relationships
- Suspicious command-line arguments
- Execution from non-standard directories
- Encoded PowerShell commands

## Mitigations

- Application Control
- User Awareness Training
- Endpoint Detection and Response (EDR)
- PowerShell Logging
