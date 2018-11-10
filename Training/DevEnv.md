# MiniKube installation on Hyper-v
To start with hyper-v
1. install Hyper-v
1. Create a virtual switch
1.

## Create an external switch
***Run Powershell as administrator***
1. List the network adapters `Get-NetAdapter`
1. Create a virtual switch with `new-VMSwitch -name ExternalSwitch -NetAdapterName "<NameofAdapterfrom 2>" -AllowManagementOS $true


## Install Chocolatey
***Run Powershell as Administrator***
`Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`

***Run cmd as Administrator***
@"%systemroot%\System32\WindowsPowerShell\v1.0\Powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Commanc "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))"`

***Check for Chocolatey upgrades***
`choco upgrade chocolatey`

## Install Minikube

-  [ ] Virtual Switch Install
-  [ ] Chocolatey Install
-  [ ] MiniKube Install
-  [ ]
