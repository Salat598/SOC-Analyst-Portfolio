# Remediation

## Registry Removal

```powershell
Remove-ItemProperty `
-Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" `
-Name "NotepadLab"
```


## Verification

```powershell
Get-ItemProperty "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run"
```

Result

The NotepadLab Registry value was no longer present.


## Validation

User logged back into Windows.

No automatic execution occurred.

Persistence successfully removed.
