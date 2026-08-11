# Project 5 — IOC & Threat Intelligence Investigation

## Overview

This project demonstrates a practical Security Operations Center (SOC) investigation involving the analysis and validation of a suspicious executable and associated network infrastructure.

The investigation began with a suspicious executable identified through threat intelligence and progressed through file reputation analysis, IP reputation analysis, endpoint validation, Sysmon investigation, and evidence correlation.

The primary objective was to determine whether the suspicious artifact was actually present or active on the investigated Windows endpoint.

## Investigation Scenario

A suspicious Windows executable was identified through threat-intelligence analysis:

`x3rh269w.exe`

The file received multiple suspicious/malicious classifications from security vendors.

An associated IP address was also identified:

`185.234.72.18`

The investigation therefore focused on answering:

- Is the file malicious or suspicious?
- Does the file exist on the endpoint?
- Was the file executed?
- Did the file establish network connections?
- Is the associated IP malicious?
- Is there sufficient evidence of endpoint compromise?
- What severity should be assigned to the investigation?

## Lab Environment

| Component | Details |
|---|---|
| Operating System | Windows 10 |
| Hostname | FINANCE-PC-07 |
| Analyst Account | SOC1 |
| Monitoring | Sysmon |
| Log Analysis | Windows Event Viewer |
| Network Analysis | Wireshark |
| File Intelligence | VirusTotal |
| IP Reputation | AbuseIPDB |

---

## Tools Used

- Sysmon
- Windows Event Viewer
- Wireshark
- VirusTotal
- AbuseIPDB
- PowerShell
- MITRE ATT&CK

## Investigation Methodology

The investigation followed a structured SOC workflow:

1. Identify suspicious IOC
2. Investigate file reputation
3. Investigate associated infrastructure
4. Check IP reputation
5. Search endpoint telemetry
6. Investigate Sysmon Event ID 1
7. Investigate Sysmon Event ID 3
8. Search the filesystem
9. Correlate available evidence
10. Determine incident severity
11. Document the final assessment

## Key Findings

### Suspicious File

**Filename:** `x3rh269w.exe`

**Size:** 2.49 MB

**File Type:** Win32 EXE

**VirusTotal Detection:** 4/59

Several security vendors classified the file as suspicious or malicious.

### Associated IP

**IP Address:** 185.234.72.18

VirusTotal:
0/91 detections
AbuseIPDB:
0 reports

Abuse Confidence:
0%
The IP was associated with data-center/web-hosting infrastructure in Germany.

## Endpoint Investigation

The endpoint was investigated to determine whether the suspicious executable was actually present or executed.

### Sysmon Event ID 1

Event ID 1 was searched for the suspicious filename.

**Result:** No matching process creation event was identified.

### Sysmon Event ID 3

Event ID 3 was searched for network connections associated with the suspicious executable.

**Result:** No matching network connection event was identified.

### Filesysystem Search

The Windows endpoint was searched for:
x3rh269w.exe

**Result:** The file was not present on the endpoint.
## Final Assessment

### Severity: MEDIUM

### Classification

**Suspicious — Endpoint Compromise Not Confirmed**

The file demonstrated suspicious characteristics through external threat intelligence, including multiple vendor detections.

However, endpoint investigation did not confirm:

- File presence
- Process execution
- Network communication
- Persistence
- Command and control
- Endpoint compromise

Therefore, the evidence was insufficient to classify the endpoint as compromised.


## Key SOC Lesson

Threat intelligence alone does not prove that an endpoint has been compromised.

A suspicious IOC should be correlated with endpoint telemetry before declaring an incident confirmed.

The investigation followed the principle:

**Reputation → Context → Behavior → Correlation → Verdict**

## MITRE ATT&CK

No specific ATT&CK technique was confirmed for the suspicious file on the endpoint because execution and malicious behavior could not be established through endpoint telemetry.

This demonstrates the importance of distinguishing between:

**Threat Intelligence**

and

**Confirmed Endpoint Activity**

## Skills Demonstrated

- IOC investigation
- Threat intelligence analysis
- File reputation analysis
- IP reputation analysis
- VirusTotal
- AbuseIPDB
- Sysmon
- Windows Event Viewer
- Sysmon Event ID 1
- Sysmon Event ID 3
- PowerShell
- Endpoint validation
- Network investigation
- Evidence correlation
- Incident severity classification
- MITRE ATT&CK
- SOC investigation methodology

## Conclusion

The investigation identified a suspicious executable through threat-intelligence sources but did not find sufficient endpoint evidence to confirm execution or compromise of `FINANCE-PC-07`.

The investigation was therefore classified as:

**MEDIUM — Suspicious / Compromise Not Confirmed**

This project demonstrates an evidence-based SOC investigation approach where conclusions are based on confirmed telemetry rather than assumptions.
