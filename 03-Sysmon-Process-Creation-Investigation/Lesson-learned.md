# Lessons Learned

This project introduced endpoint monitoring using Sysmon Event ID 1 (Process Creation).

Key concepts learned include:

- Understanding how Sysmon records process creation events.
- Interpreting process metadata such as Image, CommandLine, User, IntegrityLevel and Hashes.
- Analyzing parent-child process relationships to determine how applications were launched.
- Recognizing the importance of executable paths and cryptographic hashes when validating process legitimacy.
- Mapping observed behavior to the MITRE ATT&CK framework.

This project strengthened my understanding of endpoint visibility and the role of Sysmon in detecting suspicious process execution within a Windows environment.
