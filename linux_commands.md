# Stuff I found out that works on Windows that I used to think only worked natively on Linux

# Ping works
> I will probably discover different switches are needed 
```powershell
ping myspecialhostname
```

# SSH works
> I found this using
```powershell
Get-WindowsCapability -Online | Where-Object Name -like '*OpenSSH*'
```

> A game changer - I thought I needed PuTTY or MobaXTerm turns out, I can do that right from the console now
```powershell
ssh myspecialhostname
```