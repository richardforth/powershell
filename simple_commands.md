# Windows Powershell: Simple Commands
> Examples attributed to SAMS Teach yourself Windows Powershell in 24 hours, 2014

## Check windows event log, show last five entries
Get-EventLog -LogName Application -Newest 5

## Check windows event log, show last five entries, format as a list
Get-EventLog -LogName Application -Newest 5 | Format-List

## Check windows event log, show last five entries, format as a list, save to an output file
Get-EventLog -LogName Application -Newest 5 | Format-List | Out-File C:\events.txt

