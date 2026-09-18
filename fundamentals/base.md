# Network devices

## Host

Hosts are devices that send or recieve traffic: computers, phones, printers, servers, cloud servers, etc. Also any Internet of Things devices(IoT) in our house: TV, Refrigerator, etc.
they all follow the same rule: sending or recieving traffic over a network

hosts typically fall in one of two categories: clients & servers

### Clients

Clients initiate requests

### Servers

Servers are computers with software installed which responds to specific requests

**Clients & servers are relative to a specific communication**

## IP Address

An IP Address is the identity of each host

IP Addresses are 32 bits eg. 136.22.17.98 --> 10001000.00010110.00010001.01100010

IP Addresses are hierarchically assigned eg. ACME. inc. - 10.x.x.x --> New York - 10.20.x.x --> Sales - 10.20.55.x --> 10.20.55.129 -> Host at **ACME**, in **New York**, in **Sales**

## Network

Network is what trasports traffic between hosts

anytime two hosts are connected we have a network

Network is a logical grouping of hosts which require similar connectivity

Networks can contain other networks, also known as sub-networks or subnets eg. sales is a subnet of New York & ACME

Networks are connected to eachouther via **Internet**

## Repeaters

Repeaters regenerate signals & allow comunications across greater distances

## Hub

Hubs act as a multi-host repeaters they facilitate scaling comunication with additional hosts

the problem with hub is that everyone in the network recieves everyone else's data

## Bridges

Bridges can only connect two Hubs together & they learn which hosts are on which side

## Switches

Switch is a combination of hub & bridges therefore they have multiple ports & they learn which hosts are on whitch port

**Switching** is the communication of data within networks

## Routers

Routers facilitate communication between networks

**Routing** is the communication of data between networks
