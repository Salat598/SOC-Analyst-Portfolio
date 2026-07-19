# Incident Report

## Incident ID

SOC-2026-001


## Incident Title

Multiple Failed SSH Authentication Attempts Followed by Successful Login


## Date

19 July 2026


## Analyst

Salat Abdullahi Issak

## Severity

Medium

## Summary

A sequence of failed SSH authentication attempts was observed against the local Windows account **jdoe**.

Following multiple failed attempts, a successful authentication occurred.

The activity was generated during a controlled security lab exercise to simulate brute-force behavior.


## Systems Affected

Host

FINANCE-PC-07

Operating System

Windows 10 Home

Service

OpenSSH Server


## Timeline

14:34

Multiple failed login attempts detected.

Windows Event ID

4625

14:34

Successful SSH authentication.

Windows Event ID

4624


## Evidence

### Failed Authentication

Event ID

4625

Target User

jdoe

Process

C:\Windows\System32\OpenSSH\sshd.exe

Status

0xc000006d

Sub Status

0xc000006a

Authentication Package

Negotiate

Logon Type

8

### Successful Authentication

Event ID

4624

Target User

jdoe

Process

C:\Windows\System32\OpenSSH\sshd.exe

Authentication Package

MICROSOFT_AUTHENTICATION_PACKAGE_V1_0

Logon Type

3


## Analysis

Repeated authentication failures followed by a successful login may indicate password guessing or brute-force activity.

Although this activity was intentionally generated in a laboratory environment, similar patterns in production should be investigated immediately.

No evidence of privilege escalation or lateral movement was observed.

## Containment Recommendations

- Verify the legitimacy of the successful login.
- Reset user credentials if compromise is suspected.
- Enable account lockout policies.
- Monitor for repeated authentication failures.
- Correlate Windows Security logs with Sysmon and firewall logs.


## Status

Closed (Lab Simulation)
