# -WhatIf
> Taking the sting out of PS commands

## Example
```powershell
PS C:\WINDOWS\system32> Stop-Service Spooler -WhatIf
What if: Performing the operation "Stop-Service" on target "Print Spooler (Spooler)".
```
> Adding -WhatIf acts like a dryrun and shows you what would have happened without actually doing it