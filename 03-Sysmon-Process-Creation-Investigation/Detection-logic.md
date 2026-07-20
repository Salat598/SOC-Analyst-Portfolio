# Detection Logic

## Objective

Detect suspicious process creation activity.

## Data Source

Sysmon Event ID 1


## Detection Opportunities

Alert when:

- powershell.exe launches from Microsoft Word.
- cmd.exe launches from Excel.
- rundll32.exe executes from a temporary directory.
- explorer.exe launches unknown executables.
- PowerShell is started with encoded commands.
- 
## Example Investigation Questions

- Which process created the child process?
- Which user launched it?
- What command-line arguments were used?
- Does the executable path match the expected Windows location?
- Is the file hash known or suspicious?
