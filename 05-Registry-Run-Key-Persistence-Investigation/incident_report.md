# Incident Report

## Incident Summary

A Registry Run Key was created using PowerShell on FINANCE-PC-07.

The modification configured Notepad.exe to execute automatically during user logon.

Although this activity was intentionally performed for training, the same technique is commonly used by threat actors to maintain persistence.

---

## Alert Information

Host

FINANCE-PC-07

User

SOC1

Severity

Medium

Event Source

Microsoft Sysmon

Event ID

13

## Evidence

Process

```text
powershell.exe
```

Registry

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Run\NotepadLab

Executable

```text
C:\Windows\System32\notepad.exe

## Root Cause

The persistence mechanism was intentionally created using PowerShell for training purposes.


## Impact

No malicious impact.

The executable launched successfully during user logon.

## Containment

Registry value removed.

## Eradication

Persistence mechanism deleted using PowerShell.

## Validation

User logged in again.

Notepad no longer launched automatically.

Persistence successfully removed.
