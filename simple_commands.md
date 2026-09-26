# Windows Powershell: Simple Commands
> Examples attributed to SAMS Teach yourself Windows Powershell in 24 hours, 2014

## Check windows event log, show last five entries
Get-EventLog -LogName Application -Newest 5

## Check windows event log, show last five entries, format as a list
Get-EventLog -LogName Application -Newest 5 | Format-List

## Check windows event log, show last five entries, format as a list, save to an output file
Get-EventLog -LogName Application -Newest 5 | Format-List | Out-File C:\events.txt

## Pull up command history
> Note F7 no longer works as the book describes
Get-History

## History functions
```powershell
PS C:\WINDOWS\system32> Get-PSReadLineKeyHandler | Where-Object Function -like '*History*'


History functions
=================

Key       Function              Description
---       --------              -----------
Alt+F7    ClearHistory          Remove all items from the command line history (not PowerShell history)
Ctrl+s    ForwardSearchHistory  Search history forward interactively
F8        HistorySearchBackward Search for the previous item in the history that starts with the current input - like PreviousHistory if the input is
                                empty
Shift+F8  HistorySearchForward  Search for the next item in the history that starts with the current input - like NextHistory if the input is empty
DownArrow NextHistory           Replace the input with the next item in the history
UpArrow   PreviousHistory       Replace the input with the previous item in the history
Ctrl+r    ReverseSearchHistory  Search history backwards interactively
```

## Invoke a previous command
> This is kind-of the closest thing to linux's !28 command (ie run History command 28)
```powershell
PS C:\WINDOWS\system32> Invoke-History 28
Write-Host "Hello World!"
Hello World!
```

## History invocation with shorthand version
> Invoke-History has a shorthand version: ihy
```powershell
PS C:\WINDOWS\system32> ihy 28
Write-Host "Hello World!"
Hello World!
```