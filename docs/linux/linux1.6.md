# Install NetApp SolidFire PowerShell Tools on Linux

![solidfire-powershell-logo](../../Install/product.png) ![linux-logo](linux-logo-small.png)

The commands should be run in a terminal session on the machine where you want to install the tool. You don't have to be in a specific directory to execute any of these commands. You need sudo access. 

## Install PowerShell bits
###### CentOS
NOTE: The following steps ran on CentOS 7.3.

1. Install the rpm package:

    `#sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm`

    Then install using yum:

    `#sudo yum install dotnet-sdk-3.1`

2. Install PowerShell:

   `dotnet tool install --global PowerShell`

###### Ubuntu
NOTE: The following process worked on Ubuntu Server 18.04. It should be similar with 16.04. 

1. Get the .NET Core SDK Package since the ubuntu package manger doesn’t have any prior knowledge of it. 
   Download it using wget:

   `#wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb`
   

2. Install the downloaded package:

   `#sudo dpkg -i packages-microsoft-prod.deb`
   
   
3. When done, install the .NET Core SDK with the following commands:


   `sudo add-apt-repository universe`
   
   `#sudo apt-get update`
   
   `#sudo apt-get install apt-transport-https`
   
   `#sudo apt-get update`
   
   `#sudo apt-get install dotnet-sdk-3.1`
   
4. Install PowerShell:

   `dotnet tool install --global PowerShell`

## Install SolidFire bits

1. Inside the PowerShell shell, install SolidFire PowerShell Tools for dotnet core using the following command:

        PS> Install-Module -Name SolidFire.Core
        
   The command automatically downloads it from the [PowerShell Gallery](powershellgallery.com). 

2. Import the SolidFire module with the following command:

        PS> Import-Module SolidFire.Core

3. To see a list of available commands, use:

        PS> Get-Command -Module SolidFire.Core

**NOTE:** This module used to be called `SolidFire.Linux`. That name has been deprecated and it is now `SolidFire.Core`

## Paths

* `$PSHOME` is `/opt/microsoft/powershell/[version]/`
* User profiles are read from `~/.config/powershell/profile.ps1`
* Default profiles are read from `$PSHOME/profile.ps1`
* User modules are read from `~/.local/share/powershell/Modules`
* Shared modules are read from `/usr/local/share/powershell/Modules`
* Default modules are read from `$PSHOME/Modules`
* PSReadLine history is recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

The profiles respect PowerShell's per-host configuration,
so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.

On Linux and macOS, the [XDG Base Directory Specification][xdg-bds] is respected.

[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
