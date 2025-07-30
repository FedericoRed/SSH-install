# server SSH-install

*powershell*
```
powershell: Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```

*controlla se esiste*
```
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH.Server*'
```
*avviare il servizio*
```
Start-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'

```
