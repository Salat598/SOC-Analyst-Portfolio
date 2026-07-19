# Detection Logic

## Detection Objective

Detect multiple failed SSH authentication attempts followed by a successful login.

## Indicators

- Event ID 4625
- Event ID 4624
- OpenSSH Process
- Same Target User
- Multiple failures within a short time

## Detection Rule

Alert when:

- Five or more Event ID 4625 events occur within five minutes

AND

A successful Event ID 4624 occurs for the same account shortly afterwards.

## Priority

Medium

Escalate to High if similar activity is observed across multiple accounts or systems.
