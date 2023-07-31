# Hybrid-Cloud-Network-in-Azure
Configured On-premises to Hub and Spoke connectivity using S2S tunneling from On-premises and hub and Transit Vnet peering from hub to spoke.


![diagram drawio](https://github.com/Ritwika06/Hybrid-Cloud-Network-in-Azure/assets/87636405/95f6f707-6776-4cf6-85be-1dd62af576fa)

In this project we will do the following - 
 - Create a hub and spoke connection
 - Establish Site-2-Site connectivity between the hub and on-prem
 - Configure on-prem and spoke connection

## Basic Concepts
### Virtual Network peering
Virtual network peering is a feature in Azure that allows you to seamlessly connect with two or more virtual networks. The traffic between virtual machines in peered virtual networks uses the Microsoft backbone infrastructure. Peering is bidirectional i.e we can send traffic from VM1 to VM2 and vice versa.

### Site-to-Site connection
A Site-to-Site VPN gateway connection is used to connect your on-premises network to an Azure virtual network over an IPsec/IKE (IKEv1 or IKEv2) VPN tunnel. Here IKEv2 is used as RRAS supports only this type of IKE. This type of connection requires a VPN device located on-premises that has an externally facing public IP address assigned to it.

### Virtual Network Gateway (VNG)
In Azure, a VNG acts as a VPN Gateway to send encrypted traffic between an Azure virtual network and on-premises locations over the public Internet.

### Local Network Gateway (LNG)
The local network gateway is a specific object that represents your on-premises location (the site) for routing purposes. It is assigned a user-defined name for easy reference and requires the IP address of your on-premises VPN device to establish a connection. This configuration enables seamless communication between your Azure virtual network and on-premises infrastructure.

### Hub and spoke topology
A hub and spoke topology is a way to isolate workloads while sharing common services. These services include identity and security. The hub is a virtual network (VNet) that acts as a central connection point to an on-premises network. The spokes are VNets that peer with the hub. Shared services are deployed in the hub, while individual workloads are deployed inside spoke networks.

### User-defined routes
User-defined routes refer to custom routing configurations set by network administrators in a computer network. These routes override the default routing decisions made by the network's underlying routing protocols. By defining specific pathways for data packets, administrators can optimize traffic flow, prioritize certain destinations, or ensure data passes through preferred devices.
