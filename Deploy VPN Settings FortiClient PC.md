```powershell

# #Set PowerShell Execution Policy - depending on your Powershell settings, this may be required when testing the script

Set-ExecutionPolicy Bypass -Scope Process -Force`

# #Install SAML VPN Profile

if((Test-Path -LiteralPath "HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**") -ne $true) {  New-Item "HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**" -force -ea SilentlyContinue };
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**' -Name 'Description' -Value '**DESCRIPTION***' -Type String -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\' -Name 'Server' -Value '[Domain.com:9443](http://domain.com:9443/)' -Type String -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME' -Name 'ServerCert' -Value '1' -Type String -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**' -Name 'promptusername' -Value '0' -Type DWord -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**' -Name 'promptcertificate' -Value '0' -Type DWord -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**' -Name 'sso_enabled' -Value '1' -Type DWord -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**' -Name 'use_external_browser' -Value '0' -Type DWord -Force -ea SilentlyContinue;
Set-ItemProperty -LiteralPath 'HKLM:\SOFTWARE\Fortinet\FortiClient\Sslvpn\Tunnels\**VPN NAME**' -Name 'azure_auto_login' -Value '0' -Type DWord -Force -ea SilentlyContinue;


```


######  The Intune install.ps1 & forticlientvpn.msi attached (this was in the intunewin folder (Microsoft-Win32-Content-Prep-Tool-master)
###### Install Powershell Script
```powershell
$PackageName = "FortiClientVPN"
$Path_local = "$Env:Programfiles\_MEM"
$Path_local = "$Env:temp"
Start-Transcript -Path "$Path_local\$PackageName-install.log" -Force
(Start-Process "msiexec.exe" -ArgumentList "/i FortiClientVPN.msi /passive /quiet INSTALLLEVEL=3 DESKTOPSHORTCUT=0 /NORESTART" -NoNewWindow -Wait -PassThru).ExitCode
Start-Sleep 5
Stop-Transcript
