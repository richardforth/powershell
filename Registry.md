#  Registry

## Using Powershell to access a registry hive
Get-Item -Path "HKLM:\SOFTWARE\Microsoft\NET Framework SETUP\NDP\*"
> Most importantly, notice the colon after HKLM, without this, it searches the local directory tree and you'll get an error