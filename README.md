# Azure VPN with FW

This creates a resource group, a hub vnet with a vpn gateway and Azure firewall, a spoke vnet peered to the hub vnet, and an on-prem vnet with vpn gateway. Also creates Windows VM's in all those subnets with your public ip added to an NSG allowing RDP access. UDR's are in place routing all traffic to the firewall.
You'll be prompted for the resource group name, location where you want the resources created, your public ip and username and password to use for the VM's.
