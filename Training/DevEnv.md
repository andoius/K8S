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

`Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString(‘https://chocolatey.org/install.ps1'))`



***Run cmd as Administrator***

`@”%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe” -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command “iex ((New-Object System.Net.WebClient).DownloadString(‘https://chocolatey.org/install.ps1'))" && SET “PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin”`

***Check for Chocolatey upgrades***

`choco upgrade chocolatey`

***Install the Kubernetes client***

`choco install kubernetes-cli`


## Install Minikube
***Run Powershell as Administrator***

`choco install minikube`

**Test that MiniKube has installed**

`minikube version`

**Check that the latest version of minikube is installed**

`minikube get-k8s-versions`

**upgrade the version of minikube installed**

`minikube update-check`

## Start minikube
previously we created a virtual switch, the name of that switch will be used here to bind the minikube to that switch

to check the available commands for minikube run
`minikube start -help`

|Setting|Desctiption|Default|
|--|--|--|
|vm-driver| Hyper-V : Specifies Hypervisor driver to be used||
|cpus|Specifies number of CPU “cores” allocation|2|
|memory|Specifies the amount of RAM allocated|2048|
|hyperv-virtual-switch |Specify virtual network switch to be used “VM-External-Switch was created in previous steps”||
|kubernetes-version| string: Specify version of Kubernetes to be installed (ex. v1.2.3)||

-  [x] Virtual Switch Install
-  [x] Chocolatey Install
-  [x] MiniKube Install
-  [ ] Start minikube
