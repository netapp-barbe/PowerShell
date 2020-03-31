# To install NetApp SolidFire PowerShell on Windows:

![solidfire-powershell-logo](../../Install/product.png)   ![windows-logo](windows10-logo-small.png)

This page has instructions for installing the SolidFire PowerShell Core tools module on a Windows client. 

**Note**: Only PowerShell Core is supported in PowerShell Tools v1.6. 

## PowerShell Core

##### Prerequisites

| Component            | Version          |
|----------------------|------------------|
| .NET Core SDK        | 3.1 or later     |
| PowerShell Core      | 6.2 or later     |
| Element software     | 11               |

### Installation Instructions
1. Download and install the .NET Core SDK, Version 3.1. You can get that here: 

   [.NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1/).

   You must use the SDK, not just the runtime.

2. Download and install the PowerShell Core msi installer: 

   Latest version : [Powershell Core 7.0](https://github.com/PowerShell/PowerShell/)

3. Once inside the PowerShell Core shell, install SolidFire PowerShell Tools using the following command:

        PS> Install-Module -Name SolidFire.Core

   The command automatically downloads the tool from the [PowerShell Gallery](powershellgallery.com).

4. Import the SolidFire module with the following command:

        PS> Import-Module SolidFire.Core

5. To see a list of available commands, use:

        PS> Get-Command -Module SolidFire.Core

##### Supported Microsoft Operating Systems

The module supports and has been tested on the following versions of these Microsoft operating systems:

| Version                |
|------------------------|
| Windows Server 2016    |
| Windows Server 2018    |
| Windows 10             |

PowerShell Core 6.2 supports many more platforms, however extensive module testing has not been done.

You can find that list here at [PowerShell Core 6.2](https://devblogs.microsoft.com/powershell/general-availability-of-powershell-core-6-2/).
