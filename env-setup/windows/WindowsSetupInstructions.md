# Windows Setup

## Basic Environment Setup


### Enable WSL in Winodws

In bios enable virtualization (varies by architecture and mobo)

First launch elevated command prompt in powershell:
```powershell
Start-Process Powershell -Verb RunAs
```
Next Configure Windows Substem Linux 
```powershell
wsl --install
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
Install Linux Subsystem of Choice from Microsoft Store (default wsl setting is ubuntu can be set to anything by wsl --install -d (distribution name))

Next Install Latest wsl2 kernel from [here](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
Set wsl2 to default subsystem
```powershell
wsl --set-default-version 2
```

You can install [windows terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?rtc=1&activetab=pivot:overviewtab) if desired to manage multiple windows and environments.

After installing desired version of linux, run the exe.
```powershell 
ubuntu.exe
```
A new account will need to be created and it doesn't have to match any windows or microsoft account.


### Install Software

Next install [docker desktop](https://www.docker.com/products/docker-desktop)
Go to the gear icon, select kubernetes and verify that the version is v1.21.2 or greater.
Next Enable kubernetes and apply and restart (this will take some time.)