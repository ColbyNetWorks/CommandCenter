
| **Command Name**        | **Purpose/Other**                                                                                       |
|-------------------------|-------------------------------------------------------------------------------------------------------|
| `Connect-MicrosoftTeams` | Connect to Microsoft Teams |
| `Set-UnifiedGroup groupname -HiddenFromExchangeClientsEnabled:$false` | Unhide a Unified Group from Exchange Clients |
| `Microsoft Deployment Toolkit (MDT)` | Download MDT |
| `register-dnsclient` | Configures DNS client for dynamic updates |
| `ipconfig /registerdns` | Refreshes DNS records |
| `wmic product where "name like 'Forti%%'"` | Uninstalls Forti software (reboots PC) |
| `ssh -i "c:\users\username\sh\productionec2instances.pem" `<br>` username@10.10.10.10 -p 404` | SSH to a Linux box |
| `route print > C:\route_output.txt` | Save route print to a file |
| `DISM /Online /Cleanup-Image /RestoreHealth` | Clean up Windows image |
| `dism /Online /Add-Capability`<br>`/CapabilityName:Print.Fax.Scan~~~~0.0.1.0` | Add fax and scan capabilities to Windows |
| `gpresult /user DOMAIN\username /h c:\Temp\rep.html` | Get Group Policy result for a user |
| `pathping 192.168.104.42` | Ping path to an IP address |
| `Add-AppxPackage -Path C:\Users\Username\MSTeams-x64.msix` | Install Teams MSXI via PowerShell |
| `nslookup somehost.sr.com 10.128.80.219` | Test DNS from a specific server |
| `start-adsyncsynccycle -policytype delta` | Run a delta sync for AD synchronization |
| `Start-ADSyncSyncCycle -PolicyType Initial` | Run an initial sync for AD synchronization |
| `nltest /dsgetdc:yourdomain.com` | Test connectivity to the domain controller |
| `https://graph.microsoft.com/beta/deviceManagement`<br>`/deviceManagementScripts/abd2-f36cd2762326` | Use to download script from Intune |
| `manage-bde -status` | Get BitLocker status |
| `manage-bde -protectors -delete C: -Type TPMAndPIN` | Remove BitLocker TPM and PIN protector |
| `manage-bde -protectors -add C: -TPM` | Add BitLocker TPM protector |
| `Net localgroup Administrators /add "AzureAD<users office 365 email address>"` | Add Azure AD user to local administrators |
| `FG CLI: Config User Samk ///// show full` | Show SAML config (VPN SSO) |
| `Get-Recipient` | Select DisplayName, RecipientType, EmailAddresses |
| `dsregcmd.exe /debug /leave` | Leave Azure AD when local admin doesn’t work |
| `Win + R msinfo32` | Open system information utility |
| `Change user /install` | Install an application via command |
| `change user /execute` | Execute an application on RSH server |
| `Chkdsk /f c` | Check disk for errors |
| `route print` | Print routing table |
| `Net Use (see list)` | View or map network drives |
| `net use G: /delete` | Remove mapped drive G: |
| `net use G: "\domain.com\Data\" /persistent:yes` | Map network drive to DFS share |
| `Remove-PSDrive -Name G -ErrorAction SilentlyContinue` | Remove mapped drive G |
| `New-PSDrive -Name G -PSProvider FileSystem -Root "\domain.local\data" -Persist` | Map network drive G via PowerShell |
| `Install-Module PSWindowsUpdate` | Install the Windows Update module for PowerShell |
| `Get-WindowsUpdates` | Get a list of available Windows updates |
| `Install-WindowsUpdates` | Install available Windows updates |
| `robocopy "C:\Users\username\Downloads" "C:\Users\username\dest" /MIR` | Sync files between directories |
| `tasklist /svc` | Display running services |
| `whoami` | Display the current user |
| `Robo copy` | Copy directories using RoboCopy |
| `CTRL SHIFT L (list on excel) Filter` | Excel command to list/filter |
| `javaws jviewer.jnlp` | Launch Java Web Start file |
| `printui /s /t2` | Open printer properties menu |
| `inetcpl.cpl` | Open Internet settings utility |
| `Net share` | Display network shares |
| `New-Object System.Net.Sockets.TcpClient("10.16.23.78", 135)` | Check open ports (e.g., port 135) |
| `Rename-Computer NAME` | Rename a computer |
| `ipconfig /all` | Display all IP configuration |
| `ipconfig /flushdns` | Flush DNS cache |
| `ipconfig /renew` | Renew IP address |
| `Tracert (IP/Host)` | Trace route to a specific IP or host |
