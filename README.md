[Table](Table.md)
# CommandCenter
# IT Admin Commands and Troubleshooting Documentation

Welcome to the IT Admin Documentation repository. This contains a comprehensive list of common IT administrative commands for troubleshooting, system configuration, and management tasks.

## Table of Contents
- [Exchange Online and Teams](#exchange-online-and-teams)
- [Microsoft Deployment Toolkit (MDT)](#microsoft-deployment-toolkit-mdt)
- [Networking and DNS](#networking-and-dns)
- [System Administration](#system-administration)
- [Disk and Storage](#disk-and-storage)
- [Group Policy and Active Directory](#group-policy-and-active-directory)
- [Security and Encryption](#security-and-encryption)
- [Miscellaneous Commands](#miscellaneous-commands)

## Exchange Online and Teams
- **Connect-ExchangeOnline**: `Install-Module ExchangeOnlineManagement`
- **Connect-MicrosoftTeams**: Connect to Microsoft Teams
- **Set-UnifiedGroup groupname -HiddenFromExchangeClientsEnabled:$false**: Unhide a Unified Group from Exchange Clients

## Microsoft Deployment Toolkit (MDT)
- **MDT**: [Microsoft Deployment Toolkit (MDT) Download](https://www.microsoft.com/en-us/download/details.aspx?id=54259)

## Networking and DNS
- **register-dnsclient**: Configures DNS client for dynamic updates
- **ipconfig /registerdns**: Refreshes DNS records
- **route print > C:\route_output.txt**: Save route print to a file
- **pathping 192.168.104.42**: Ping path to an IP address
- **nslookup somehost.sr.com 10.128.80.219**: Test DNS from a specific server

## System Administration
- **wmic product where "name like 'Forti%%'" call uninstall /nointeractive**: Uninstalls Forti software (reboots PC)
- **dism /Online /Cleanup-Image /RestoreHealth**: Clean up Windows image
- **gpresult /user DOMAIN\username /h c:\Temp\rep.html**: Get Group Policy results for a user
- **start-adsyncsynccycle -policytype delta**: Run a delta sync for AD synchronization
- **nltest /dsgetdc:yourdomain.com**: Test connectivity to the domain controller

## Disk and Storage
- **Chkdsk /f c**: Check disk for errors
- **robocopy "C:\Users\username\Downloads" "C:\Users\username\OneDrive - Strathcona Resources Ltd\Downloads" /MIR**: Sync files between directories
- **New-PSDrive -Name G -PSProvider FileSystem -Root "\\domain.local\Filepath\Data" -Persist**: Map network drive G:

## Group Policy and Active Directory
- **Get-Recipient | Select DisplayName, RecipientType, EmailAddresses | Export-Csv EmailAddresses.csv**: Export email aliases from Exchange
- **Get-ADGroupMember "Admin" | select name | Export-CSV "C:\Users\sdi\Desktop\1222.csv" -NoTypeInformation**: Export members of the "Admin" group
- **$inactiveComputers = Get-ADComputer -Filter {LastLogonTimestamp -lt $time -and Enabled -eq $true} -Property Name, LastLogonTimestamp**: Get computers that haven't logged in for 90 days

## Security and Encryption
- **manage-bde -status**: Get BitLocker status
- **manage-bde -protectors -delete C: -Type TPMAndPIN**: Remove BitLocker TPM and PIN protector
- **manage-bde -protectors -add C: -TPM**: Add BitLocker TPM protector
- **Net localgroup Administrators /add "AzureAD\<users office 365 email address>"**: Add Azure AD user to local administrators

## Miscellaneous Commands
- **gpresult /h c:\temp\1.html**: Output GP result to HTML
- **msinfo32**: System Information (CMD)
- **systeminfo | findstr /B /C:"Domain"**: Find the domain in system info
- **Robo copy**: Copy directories using RoboCopy
- **whoami**: Display current user
- **slmgr /xpr**: Display Windows activation status
- **powercfg -energy**: Monitor energy efficiency for 60 seconds
- **wmic bios get serialnumber**: Get the system's BIOS serial number
- **netsh winsock reset**: Reset network connections (requires reboot)
- **mklink /H Link Target**: Create a hard link
- **SUBST**: Map a folder to a drive letter
- **slmgr /xpr**: Check Windows activation status

---

## Contributing
If you would like to suggest new commands, fixes, or improvements to the documentation, please submit a **Pull Request**.

## License
This documentation is licensed under the [MIT License](LICENSE).

---

> **Note**: This README file provides a navigation menu for IT admin commands and troubleshooting, categorized by their usage. All commands should be used with care and as per your organization's policies.
