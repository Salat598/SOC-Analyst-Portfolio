# Project 01: Brute Force Login Investigation

## Overview

**Project Type:** SOC Analyst Lab Simulation  

**Disclaimer:** This investigation is based on a simulated Security Operations Center (SOC) scenario created for learning purposes. It does not represent a real-world security incident.

# Incident Summary

On **08:30 AM**, the Security Information and Event Management (SIEM) platform generated a **Medium Severity** alert after detecting multiple failed login attempts against a user account. The alert showed **18 consecutive failed login attempts** followed immediately by a successful login within a five-minute period.

Although the successful login could have been performed by the legitimate user, the pattern of repeated authentication failures followed by success is consistent with a possible brute-force attack and required further investigation.

# Alert Details

| Field | Value |
|--------|-------|
| Alert Name | Multiple Failed Login Attempts |
| Severity | Medium |
| Username | jdoe |
| Host | FINANCE-PC-07 |
| Source IP | 192.168.10.45 |
| Failed Logins | 18 |
| Successful Login | Yes |
| Time Window | 08:02 – 08:07 |

# Timeline

| Time | Event |
|------|-------|
| 08:02:11 | Failed Login Attempt |
| 08:02:19 | Failed Login Attempt |
| 08:02:26 | Failed Login Attempt |
| ... | Additional Failed Login Attempts |
| 08:06:55 | 18th Failed Login Attempt |
| 08:07:04 | Successful Login |

# Initial Assessment

The investigation identified repeated authentication failures against a single user account from the same IP address. A successful login immediately after numerous failures is suspicious and may indicate that valid credentials were eventually obtained.
At this stage, the activity is **consistent with a brute-force attack**, but additional investigation would be required to determine whether the successful login was performed by the legitimate user or an unauthorized attacker.
# Possible Attack Type
## Brute Force Attack
A brute-force attack involves attempting many different passwords against a single user account until authentication succeeds.
### Why this assessment?

- Multiple failed logins against one account.
- Login attempts occurred within a short period.
- Successful authentication occurred after repeated failures.
- No evidence was available indicating password reset activity.
# Evidence to Collect

## Windows Security Logs

Relevant Windows Security Event IDs include:

| Event ID | Description |
|-----------|-------------|
| 4625 | Failed Logon |
| 4624 | Successful Logon |
| 4634 | User Logoff |
| 4672 | Special Privileges Assigned to New Logon |

These events help determine:

- Who attempted to log in
- Source IP address
- Logon type
- Authentication status
- Administrative privileges

## Firewall Logs

Firewall logs should be reviewed to determine:

- Whether the source IP has communicated with other systems.
- Whether unusual network activity occurred.
- Whether additional suspicious connections were established after login.
## Active Directory Logs

Review Active Directory logs for:

- Account lockouts
- Password changes
- Privilege modifications
- Authentication history
## Endpoint Security Logs

Review endpoint detection and response (EDR) logs for:

- PowerShell execution
- New process creation
- Malware detections
- Suspicious file activity
- Lateral movement

## VPN Logs (if applicable)

If the organization uses VPN access, review:

- VPN authentication records
- Device information
- Geographical location
- Multi-factor authentication (MFA) status

# Investigation Steps

The following actions would be performed during the investigation:

1. Verify whether the user initiated the successful login.
2. Review Windows Event Logs for authentication events.
3. Analyze firewall logs for suspicious network activity.
4. Review endpoint telemetry for malicious behavior.
5. Determine whether other accounts experienced similar login attempts.
6. Check whether the source IP has previously generated security alerts.
7. Review activity performed after the successful login.
# Indicators of Compromise (IOCs)

| Type | Value |
|------|-------|
| Username | jdoe |
| Source IP | 192.168.10.45 |
| Host | FINANCE-PC-07 |
| Failed Login Attempts | 18 |
| Successful Login | 08:07:04 |

# Impact Assessment

At the time of the investigation:

- No evidence of malware execution was available.
- No evidence of privilege escalation was observed.
- No evidence of data exfiltration was available.

However, because authentication was eventually successful, there remains a possibility of unauthorized access that requires additional investigation.

# Severity Assessment

**Medium**

### Justification

The alert represents suspicious authentication activity involving multiple failed logins followed by a successful login.

Although successful authentication increases the potential risk of account compromise, there is currently no evidence of malicious activity after login. Additional investigation is required before escalating the severity.


# MITRE ATT&CK Mapping

| Tactic | Technique | Technique ID |
|---------|-----------|--------------|
| Credential Access | Brute Force | T1110 |
| Initial Access / Defense Evasion | Valid Accounts | T1078 |

### Explanation

**T1110 – Brute Force**

The repeated failed authentication attempts are consistent with password guessing.

**T1078 – Valid Accounts**

If the successful login was performed by an attacker using valid credentials, the attacker would be abusing a legitimate account to gain access.

# Containment Recommendations

If malicious activity is confirmed, the following actions are recommended:

- Reset the affected user's password.
- Require Multi-Factor Authentication (MFA).
- Temporarily disable the account if compromise is suspected.
- Block the malicious source IP if confirmed to be external.
- Monitor the account for additional suspicious activity.
- Review authentication logs across the environment for similar attacks.
- Notify the affected user and verify recent account activity.

# Lessons Learned

This investigation demonstrates the importance of monitoring authentication events and correlating failed and successful logins.

A successful login immediately following multiple failed attempts should always be investigated because it may indicate credential compromise. Analysts should avoid making assumptions and instead base conclusions on evidence collected from authentication logs, endpoint telemetry, firewall logs, and user verification.

# Final Conclusion

The SIEM detected a Medium-severity authentication alert involving 18 failed login attempts followed by a successful login against the user account **jdoe** from source IP address **192.168.10.45**.

The activity is consistent with a possible brute-force attack; however, the available evidence is insufficient to confirm malicious intent. Further investigation, including user verification and review of Windows Event Logs, firewall logs and endpoint telemetry, is necessary to determine whether the successful login was legitimate or unauthorized.

Until additional evidence is obtained, the incident should remain under investigation while the affected account is closely monitored for suspicious activity.
