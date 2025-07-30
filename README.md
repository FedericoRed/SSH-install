# server SSH-install

*abilitare la porta dal firewall*
1)
<img width="189" height="98" alt="fire1" src="https://github.com/user-attachments/assets/b14d1821-7ad8-4601-9cf0-775a1ca51c3c" />

2) 
<img width="846" height="225" alt="fire2" src="https://github.com/user-attachments/assets/812e6a8d-b0f3-4ae4-a7f4-9459df93b5a9" />

3)
<img width="677" height="309" alt="fire3" src="https://github.com/user-attachments/assets/519193b3-de0b-4292-897f-adc0fa3174ac" />


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
