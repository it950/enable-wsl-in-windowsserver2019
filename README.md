## How to install wsl in windows server 2019
# Windows server 2019 do not support docker, the following steps only for logs
1. Check windows ***server 2019 version***: *1709 or later*, type command **winver** in command line.<br>
2. Enable the Windows Subsystem for Linux
``` PowerShell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```
3. [Downloading a distribution](https://docs.microsoft.com/en-us/windows/wsl/install-manual#downloading-distributions), eg: [Ubuntu20.04](https://aka.ms/wslubuntu2004)
4. Extract the downloaded file
``` Powershell
Rename-Item .\CanonicalGroupLimited.UbuntuonWindows_2004.2021.825.0.AppxBundle .\Ubuntu.zip
Expand-Archive .\Ubuntu.zip .\Ubuntu
```
5. Install Linux distribution from Ubuntu folder
``` Powershell
Add-AppxPackage .\Ubuntu_2004.2021.825.0_x64.appx
```
6. Launch linux from windows start menu
7. Set user name and password
8. If you receive some error, first check the windows version(1709 or later), then [confirm wsl is enable](https://docs.microsoft.com/en-us/windows/wsl/troubleshooting#confirm-wsl-is-enabled)
9. [Reference](https://docs.microsoft.com/en-us/windows/wsl/install-on-server)


