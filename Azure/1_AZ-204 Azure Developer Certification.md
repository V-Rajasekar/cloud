## AZ-204 Azure Developer Certification

### Prerequests
1. Register for Azure Account
2. Download VisualStudio code
3. Bookmark Azure-Samples

### Installing PowerShell

https://github.com/powershell/powershell (WIndows x64)

#### Installing AZ module 

`Install-Module -Name AZ -AllowClobber` 

#### List AZ module available 

`Get-Module -Name Az -Listavailable`


--- Connect to azure account

 `Connect-AZAccount`

--- List available VM

`Get-AzVm` 


## Creating a Virtual machine
A Virtual mchine is a service that cloud providers offer that as Iaas. It is a portion of a machine that is running in an Azure data center , that you can control like remote, installing software and you pay only that use it. 

### Azure portal 

### Azure Resounce management template ARM Template

- Create resources using JSON template and by passing the parameters. Allows to automate resource creation and implement desired state configuration. 
- Allows to control environment looks and prevent developers or ops from changing it accidentally.

### Using PowerShell

```powershell 

Login to Azure account 

  Connect-AZAccount

Creating AZ ResourceGroup

  New-AzResourceGroup -Name "powershellgrp" -Location EastUS

Creating a New VM

    New-AzVm -ResourceGroupName  powershellgrp  -Location EastUS -Name "myPowershellvm" -VirtualNetworkName "mypowershellNet" -SubnetName "default" -SecurityGroupName "poweshellNSG" -PublicIpAddressName "powershellpublicip" -OpenPorts 80, 3389

-- List Available VM

Get-AzVm

```
 

### Using AZ Cli command

--- Az cli

```powershell

List Resource groups
`az group list`

-- Create AZ Resource group

az group create --name cligroup --location eastus

-- Creating AZ VM with default VirtualNetworkGroup, Subnet, IPAddress, Port opens

az vm create --resource-group cligroup --name aznewvm --image win2016datacenter --admin-username rajasekar

```


