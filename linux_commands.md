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

# Generating an SSH key now just works
> previously we needed PuTTYGen
ssh-keygen -t ed25519

# Equivalent to ssh-copy-id myspecialserver
```powershell
Get-Content $HOME\.ssh\id_ed25519.pub | ssh redacted@myspecialserver.co.uk "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```

> A game changer - I thought I needed PuTTY or MobaXTerm turns out, I can do that right from the console now
```powershell
ssh myspecialserver
```

# scp also works
```powershell
scp redacted@myspecialserver.co.uk:~/.bash_history bash_history_redacted.txt
```

# An equivalent to `sleep 120 && ssh myspecialhost`
```powershell
sleep 120; ssh myspecialhost
```
> note its not exactly alike, the semicolon just says run the next command despite the exit code of the previous command

# Backgrounding, subshells, and jobs
```powershell
Start-Job {
    Start-Sleep -Seconds 10
}

Get-Job
Id Name PSJobTypeName State     HasMoreData Location
-- ---- ------------- -----     ----------- --------
1  Job1 BackgroundJob Running   True        localhost

Stop-Job 1; Remove-Job 1

