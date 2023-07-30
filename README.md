# Azure VPN with FW

This creates a resource group, a hub vnet with a vpn gateway and Azure firewall, a spoke vnet peered to the hub vnet, and an on-prem vnet with vpn gateway. This creates a log analytics workspace and diagnostic settings for the firewall logs. Also creates Windows VM's in all those subnets with your public ip added to an NSG allowing RDP access. UDR's are in place routing all traffic to the firewall except for your public ip to allow RDP access directly to the VM's. NSG's are placed on the default subnets of each vnet allowing RDP access from your public ip. This also creates a logic app that will delete the resource group in 24hrs.
You'll be prompted for the resource group name, location where you want the resources created, your public ip and username and password to use for the VM's.

The topology will look like this:

![vpnlabwithfw](https://user-images.githubusercontent.com/128983862/231862510-e0227b69-282e-4bce-bec2-1f7d721c5024.png)

You can run Terraform right from the Azure cloud shell by cloning this git repository with "git clone https://github.com/quiveringbacon/AzureVPNwithFW.git ./terraform".

Then, "cd terraform" then, "terraform init" and finally "terraform apply -auto-approve" to deploy.
