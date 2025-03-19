# TP2 : spawn moar vm moar cloud much cloud : une approche programmatique
## Part I : Programmatic approach
### I. Premiers pas
🌞 Créez une VM depuis le Azure CLI
~~~
C:\Users\jerem>az vm create -g Léo -n PCPortableTP2 --image Ubuntu2204 --admin-username marant --ssh-key-values ~/.ssh/id_rsa.pub
{
  "fqdns": "",
  "id": "/subscriptions/5c029a8e-2178-45ca-b23c-9cda6a79d3f1/resourceGroups/Léo/providers/Microsoft.Compute/virtualMachines/PCPortableTP2",
  "location": "centralindia",
  "macAddress": "7C-1E-52-3C-AF-0C",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.6",
  "publicIpAddress": "4.213.58.208",
  "resourceGroup": "Léo",
  "zones": ""
}
~~~
🌞 Assurez-vous que vous pouvez vous connecter à la VM en SSH sur son IP publique.
~~~
C:\Users\jerem>ssh marant@4.213.58.208
marant@PCPortableTP2:~$
~~~
- présence du service walinuxagent
~~~
marant@PCPortableTP2:~$ sudo systemctl status walinuxagent
● walinuxagent.service - Azure Linux Agent
     Loaded: loaded (/lib/systemd/system/walinuxagent.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2025-03-18 08:49:58 UTC; 7min ago
~~~
- présence du service cloud-init
~~~
marant@PCPortableTP2:~$ sudo systemctl status cloud-init
● cloud-init.service - Cloud-init: Network Stage
     Loaded: loaded (/lib/systemd/system/cloud-init.service; enabled; vendor preset: enabled)
     Active: active (exited) since Tue 2025-03-18 08:49:58 UTC; 8min ago
~~~
### II. Un ptit LAN
🌞 Créez deux VMs depuis le Azure CLI
- création `VNet` et création 2e `VM`
~~~
az network vnet create --resource-group Léo --name VNet --address-prefix 10.0.0.0/16 --subnet-name Subnet --subnet-prefix 10.0.0.0/24


marant@VMTP22:~$ ping 10.0.0.4
PING 10.0.0.4 (10.0.0.4) 56(84) bytes of data.
64 bytes from 10.0.0.4: icmp_seq=1 ttl=64 time=1.93 ms
64 bytes from 10.0.0.4: icmp_seq=2 ttl=64 time=0.999 ms
64 bytes from 10.0.0.4: icmp_seq=3 ttl=64 time=0.965 ms


marant@VMTP2:~$ ping 10.0.0.5
PING 10.0.0.5 (10.0.0.5) 56(84) bytes of data.
64 bytes from 10.0.0.5: icmp_seq=1 ttl=64 time=0.867 ms
64 bytes from 10.0.0.5: icmp_seq=2 ttl=64 time=0.948 ms
64 bytes from 10.0.0.5: icmp_seq=3 ttl=64 time=0.963 ms
~~~
## Part II : cloud-init
### 1. Intro
### 2. Gooooo
🌞 Tester `cloud-init`
~~~
az vm create -g Léo -n VMTP2 --image Ubuntu2204 --admin-username marant --ssh-key-values ~/.ssh/id_rsa.pub --custom-data ~\Cours\B2\CLOUD\cloud-init.txt
~~~
🌞 Vérifier que cloud-init a bien fonctionné
~~~
ssh user1@135.235.162.194
user1@VMTP22:~$
~~~
### 3. Write your own
🌞 Utilisez `cloud-init` pour préconfigurer la VM :
~~~
ssh marantuser@4.224.62.147
The authenticity of host '4.224.62.147 (4.224.62.147)' can't be established.
ED25519 key fingerprint is SHA256:xtn1DSf4uww79zbdoxpGlm1VoL+uvh3AhsdNUZGxwfc.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '4.224.62.147' (ED25519) to the list of known hosts.
Welcome to Ubuntu 22.04.5 LTS (GNU/Linux 6.8.0-1021-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information disabled due to load higher than 1.0

Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

marantuser@VMTP202:~$
~~~
## Part III : Terraform
### 2. Copy paste
🌞 Constater le déploiement
~~~
az vm list -o table
PS C:\Users\jerem\Desktop\Cours\B2\CLOUD\TerrraformTP> az vm list -o table
Name            ResourceGroup          Location      Zones
--------------  ---------------------  ------------  -------
tp2magueule-vm  TP2MAGUEULE-RESOURCES  westeurope
VMTP202         LÉO                    centralindia

PS C:\Users\jerem\Desktop\Cours\B2\CLOUD\TerrraformTP> az vm show --name tp2magueule-vm -g tp2magueule-resources -o table
Name            ResourceGroup          Location    Zones
--------------  ---------------------  ----------  -------
tp2magueule-vm  tp2magueule-resources  westeurope
PS C:\Users\jerem\Desktop\Cours\B2\CLOUD\TerrraformTP>
PS C:\Users\jerem\Desktop\Cours\B2\CLOUD\TerrraformTP>

PS C:\Users\jerem\Desktop\Cours\B2\CLOUD\TerrraformTP> az group list -o table
Name                   Location      Status
---------------------  ------------  ---------
Léo                    centralindia  Succeeded
NetworkWatcherRG       centralindia  Succeeded
tp2magueule-resources  westeurope    Succeeded
~~~
### 3. Do it yourself
🌞 Créer un plan Terraform avec les contraintes suivantes
~~~
provider "azurerm" {
  features {}
  subscription_id = "5c029a8e-2178-45ca-b23c-9cda6a79d3f1"
}

resource "azurerm_resource_group" "main" {
  name     = "${var.prefix}-resources"
  location = var.location
}

resource "azurerm_virtual_network" "main" {
  name                = "${var.prefix}-network"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.main.location
  resource_group_name = azurerm_resource_group.main.name
}

resource "azurerm_subnet" "internal" {
  name                 = "internal"
  resource_group_name  = azurerm_resource_group.main.name
  virtual_network_name = azurerm_virtual_network.main.name
  address_prefixes     = ["10.0.2.0/24"]
}

resource "azurerm_public_ip" "node1_pip" {
  name                = "${var.prefix}-node1-pip"
  resource_group_name = azurerm_resource_group.main.name
  location            = azurerm_resource_group.main.location
  allocation_method   = "Static"
}

resource "azurerm_network_interface" "node1_nic" {
  name                = "${var.prefix}-node1-nic"
  resource_group_name = azurerm_resource_group.main.name
  location            = azurerm_resource_group.main.location

  ip_configuration {
    name                          = "public"
    subnet_id                     = azurerm_subnet.internal.id
    private_ip_address_allocation = "Dynamic"
    public_ip_address_id          = azurerm_public_ip.node1_pip.id
  }
}

resource "azurerm_network_interface" "node2_nic" {
  name                = "${var.prefix}-node2-nic"
  resource_group_name = azurerm_resource_group.main.name
  location            = azurerm_resource_group.main.location

  ip_configuration {
    name                          = "private"
    subnet_id                     = azurerm_subnet.internal.id
    private_ip_address_allocation = "Dynamic"
  }
}

resource "azurerm_network_security_group" "ssh" {
  name                = "${var.prefix}-ssh-nsg"
  location            = azurerm_resource_group.main.location
  resource_group_name = azurerm_resource_group.main.name

  security_rule {
    name                       = "allow_ssh"
    priority                   = 100
    direction                  = "Inbound"
    access                     = "Allow"
    protocol                   = "Tcp"
    source_port_range          = "*"
    source_address_prefix      = "*"
    destination_port_range     = "22"
    destination_address_prefix = "*"
  }
}

resource "azurerm_network_interface_security_group_association" "node1_assoc" {
  network_interface_id      = azurerm_network_interface.node1_nic.id
  network_security_group_id = azurerm_network_security_group.ssh.id
}

resource "azurerm_linux_virtual_machine" "node1" {
  name                  = "${var.prefix}-node1"
  resource_group_name   = azurerm_resource_group.main.name
  location              = azurerm_resource_group.main.location
  size                  = "Standard_F2"
  admin_username        = "azureuser"
  network_interface_ids = [azurerm_network_interface.node1_nic.id]

  admin_ssh_key {
    username   = "azureuser"
    public_key = file("~/.ssh/id_rsa.pub")
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "0001-com-ubuntu-server-jammy"
    sku       = "22_04-lts"
    version   = "latest"
  }

  os_disk {
    storage_account_type = "Standard_LRS"
    caching              = "ReadWrite"
  }
}

resource "azurerm_linux_virtual_machine" "node2" {
  name                  = "${var.prefix}-node2"
  resource_group_name   = azurerm_resource_group.main.name
  location              = azurerm_resource_group.main.location
  size                  = "Standard_F2"
  admin_username        = "azureuser"
  network_interface_ids = [azurerm_network_interface.node2_nic.id]

  admin_ssh_key {
    username   = "azureuser"
    public_key = file("~/.ssh/id_rsa.pub")
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "0001-com-ubuntu-server-jammy"
    sku       = "22_04-lts"
    version   = "latest"
  }

  os_disk {
    storage_account_type = "Standard_LRS"
    caching              = "ReadWrite"
  }
}
~~~
~~~
ssh azureuser@40.113.155.178
The authenticity of host '40.113.155.178 (40.113.155.178)' can't be established.

azureuser@tp2maface-node1:~$
~~~
~~~
ssh -J azureuser@40.113.155.178 azureuser@10.0.2.5
The authenticity of host '10.0.2.5 (<no hostip for proxy command>)' can't be established.

azureuser@tp2maface-node2:~$
~~~
### 4. cloud-iniiiiiiiiiiiiit
![alt text](https://media1.tenor.com/m/3wJqEkHwcdwAAAAd/oui-mais.gif)
