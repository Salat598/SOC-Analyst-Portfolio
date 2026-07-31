# MITRE ATT&CK Mapping

## Tactic

Persistence

## Technique

T1547.001

Registry Run Keys / Startup Folder
## Evidence

Sysmon Event ID 13

Registry Value Set

PowerShell modified

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

creating

NotepadLab

## Analyst Assessment

The observed activity matches MITRE ATT&CK T1547.001 because the Registry Run Key allows automatic execution after user logon.
