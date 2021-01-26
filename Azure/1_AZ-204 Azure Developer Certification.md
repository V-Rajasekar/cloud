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

The resources in this table are used by the VM and need to exist or be created when the VM is created.

|Resource |Required| Desc|
|----|----|----|
|Resource Group| yes|The VM must be contained in a resource group.|
|Storage Account|yes|The VM needs the storage account to store its virtual hard disks.|
|Virtual network|Yes| The VM must be a member of a virtual network.|
|Network interface|Yes|The VM needs the network interface to communicate in the network.|
|Public IP address|No|The VM can have a public IP address assigned to it to remotely access it.|
|Data disks|No|The VM can include data disks to expand storage capabilities.|



### Azure Resounce management template ARM Template
- Its a deployment and managment service (CRUD) operations in Azure resources
- Create resources using JSON template and by passing the parameters. Allows to automate resource creation and implement desired state configuration. 
- Allows to control environment looks and prevent developers or ops from changing it accidentally.