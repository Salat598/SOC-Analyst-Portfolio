# Incident Report

## Incident Summary

A Sysmon alert identified the execution of Windows PowerShell on host FINANCE-PC-07.
The investigation focused on determining whether the PowerShell activity represented malicious behavior or legitimate administrative activity.
## Host
FINANCE-PC-07
## User
SOC1
## Detection Source
Microsoft Sysmon
Event ID 1 – Process Creation
## Investigation
The initial process creation event showed that PowerShell was launched by explorer.exe, indicating interactive user execution.
The PowerShell session subsequently launched multiple Windows utilities used for system reconnaissance.
Observed child processes included:
- whoami.exe
- ipconfig.exe

The commands were executed using a Medium Integrity process and no evidence of privilege escalation was observed.
No encoded PowerShell commands were detected.
No suspicious command-line switches such as:

- -EncodedCommand
- -ExecutionPolicy Bypass
- -NoProfile

were present.

No persistence or malware execution was identified during the investigation.

## Conclusion
The observed activity is consistent with legitimate system reconnaissance performed by the logged-on user.
Although the commands are commonly used by threat actors after initial compromise, the investigation determined the activity was expected within the controlled laboratory environment.

## Severity
Low

## Recommendation
Continue monitoring PowerShell activity.
Investigate PowerShell executions containing:
- Encoded commands
- Hidden windows
- Download activity
- Privilege escalation
- Network connections
