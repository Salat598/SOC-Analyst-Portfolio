# MITRE ATT&CK Mapping

## Technique

T1110 – Brute Force

Description

Adversaries may attempt to gain access by repeatedly guessing passwords.

## Data Sources

- Windows Security Logs
- Authentication Logs
- OpenSSH Logs
- Sysmon

## Detection

Monitor for repeated authentication failures followed by a successful login.

## Mitigation

- Strong password policy
- Multi-factor authentication
- Account lockout
- Login monitoring
