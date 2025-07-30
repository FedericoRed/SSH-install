# server SSH-install

*powershell con diritti da amministratore*
```
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
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

*controlla se il servizio è in esecuzione*
```
Get_Service -Name sshd
```

*collegamento client-macchina destinazione*
```
powershell con amministratore sul TUO PC

ssh NOME_UTENTE_MACCHINA_REMOTA@INDIRIZZO_MACCHINA_REMOTA
```
