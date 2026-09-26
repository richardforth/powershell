#  Registry

## Using Powershell to access a registry hive
Get-Item -Path "HKLM:\SOFTWARE\Microsoft\NET Framework SETUP\NDP\*"
> Most importantly, notice the colon after HKLM, without thi, it searches the local directory tree asand you'll get an error