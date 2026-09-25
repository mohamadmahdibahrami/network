# OSI(Open Systems Interconnection) Model:

OSI Model devides rules of networking into 7 layer & each layer serves a specific function

## Layer 1 - Physical:

The goal of physical layer is to transport computer data from a host to another eg. cables, wifi, repeaters, hubs

computer data exists in form of **Bits** (1's & 0's)

## Layer 2 - Data link - Hop to Hop:

Data link interacts with the physical layer eg. NIC (Network Enterface Cards), Wi-Fi Access Cards, Switches

The overall goal of layer 2 is to take 1's & 0's from a NIC to another NIC & to accomplish this goal is uses a specific addressing scheme known as **MAC Address**

**MAC Addresses** are 48 bits, represented as 12 hex digits eg. 94-65-9C-3B-8A-E5 on Windows, 94:65:9C:3B:8A:E5 on Linux, 9465.9C3B.8AE5 on Cisco

Every single NIC has a unique MAC Address

## Layer 3 - Network - End to End:

The overall goal of Layer 3 is to transfer data from an end to the other end and its Addressing Scheme is IP Address eg. Routers, Hosts, (Anything with an IP Address)

IP Addresses are 32 bits, represented as 4 octets, each 0-255

## The difference between Layer 2 & Layer 3:

if a host needs to send data to another host the layer 3 only adds the information of both **Ends** of this connection but the data needs to **Hop** on different routers to reach the other **End** therefore layer 2 adds the information of the first **Hop** to the packet then the second **Hop** etc... untill the data reaches the second **End**

Both Layer 3 & Layer 2 add both the source and the destination IP/MAC Address to the data transfered

## Layer 4 - Transport - Service to Service

The overall goal of Layer 4 is to make sure that the right app gets the right information & its Addressing Scheme is Ports

ports are eather TCP (0 - 65525) which favors !reliability or UDP (0 - 65525) which favors !efficiency eg. www.xyz.com -> TCP-22493 & the IP address looks like: 1.1.1.1:22493

the client selects a random port for each connection

reliability = قابل اطمینان بودن / efficiency = سودمند بودن
