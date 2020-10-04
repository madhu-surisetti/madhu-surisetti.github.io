---
layout: page
title: GATE - CN
permalink: /gate/computer-networks/
publish: t
type: list
start: sep 9, 2020
last: sep 9, 2020
---

## Computer Networks

### Introduction to Computer Network & IP address
- Things:
-- Networks(network-id) => Hosts(domain-name, host-id) => Processes(port-number)
- Data moves around the networks
- DNS => Phonebook for the Internet
- 2^10 -> Kilo
- 2^20 -> Mega
- 2^30 -> Giga
- 2^40 -> Tera
- If you have n bits, you have 2^n numbers
- If you choose k bits (k<n), you divide 2^n numbers into 2^k parts(with 2^(n-k) elements in each division)
- This is how you divide networks & hosts
- Choose the first k bits to get 2^k networks and leave the (n-k) bits for each host
- You have n = 32 bits for IP address
- If you buy an IP address for an organization, you buy a network-id(i.e., the first k bits)
- This way dividing IP addresses is called: classfull
![alt text](https://raw.githubusercontent.com/madhu-surisetti/madhu-surisetti.github.io/master/images/gate/classfull.png "Classfull division of IP addresses")
- You can tell which class the IP belongs to by looking at the first byte.
- classA - 2^31 addresses(network-id-range 1 - 126)
- classB - 2^30 addresses(network-id-range 128 - 191)
- classC - 2^29 addresses(network-id-range 192 - 223)
- classD - 2^28 addresses(there are no network ids here - only IP addresses)
- classE - 2^28 addresses(there are no network ids here - only IP addresses)
- If you have an n bit binary number with all 1's, then it's value is (2^n)-1
- When you buy a network-id, you cannot use the first and last host-ids
- You use the 1st address to represent the network.
- The last address is used as broadcast address.

### Types of Casting
- Casting: Sending data from one host to another
- 2Types of casting: unicast and broadcast
- unicast -> one host to another
- broadcast -> one host to many
- Limited broadcast address -> 255.255.255.255(from one host to all the hosts in the same network)
- Directed broadcast address -> network-id.255.255.255(from one host all the hosts in another network with network-id)

### Subnets, Subnet masking, Routing
- You select some bits to divide the network into subnets.
- For example, in the network 220.1.2.0 the last 8 bits belong to host-id. So, select the first bit of the first byte to divide the network into 2 subnets. The first subnet will be from 220.1.2.0 to 220.1.2.127(these 2 can't be used - because the first and last addresses are always reserved for broadcast addresses) and the second one's from 220.1.2.128 to 220.1.2.255(here 220.1.2.128 becomes the network-id of the subnet)
- If you are the network 220.1.2.128 and there are 2 subnet like above, then 220.1.2.255 is the direct-broadcast-address for the 2nd subnet. But if a packet is coming from outside the network, 220.1.2.255 is the direct-broadcast-address for the whole network.
- Routers use subnet-mask to find the interface of the subnet that the packet needs to be forwarded to.
- Creating a subnet-mask: subnet-mask is 4 bytes. All bits belonging to the network-id and subnet-id are filled with 1 and the rest with 0.
- If you AND the subnet-mask with the IP address, you get the subnet-id that the packet belongs to.
- The router uses routing-table to decide the interface to forward to. Routing table is basically a hash-table to subnet-ids and interfaces.
- Only one subnet-mask for one network.
- Sometimes an IP address matches with more than 1 interface in the routing table. If that happens, choose the interface with more 1's in the address.

### variable length subnet masking(VLSM)
- You can tell the number of host-ids available from the subnet-mask
- Subnet-mask is a string of 1's followed by 0's (usually).

### Subnet masking question

### Classless Interdomain routing(CIDR)
- Classfull division is not flexible with size.
- CIDR is created to solve this problem.
- The downside is we can't tell the network-id or host-id
- So we usually append the IP address with number of bits of network-id in the IP => 192.168.43.86/n -> has n bits of network-id-range
- Rules for forming CIDR blocks
-- All the IP addresses must be contiguous
-- Block should be a power of 2
-- First IP in the block should be divisible by the block-size.
- Any IP appended with the number of network-id bits can represent the entire block.
- The first IP in the block is reserved for the block-id.

### Subnetting in CIDR, VLSM in CIDR
- If you want to subnet, choose bits from host-id and divide.
- For representation, append the subnet bits to the IP.
- 