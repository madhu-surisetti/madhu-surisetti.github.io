---
layout: page
title: Quotes
permalink: /gate/computer-networks/
publish: t
type: list
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
- If you have n bits, you 2^n numbers
- If you choose k bits (k<n), you divide 2^n numbers into 2^k parts(with 2^(n-k) elements in each division)
- This is how you divide networks & hosts
- Choose the first k bits to get k networks and leave the (n-k) bits for each host
- You have n = 32 bits for IP address
- If you buy an IP address, you buy a network-id(i.e., the first k bits)
- There is another way meta way of dividing IP addresses: classfull
![alt text](https://raw.githubusercontent.com/madhu-surisetti/madhu-surisetti.github.io/master/images/gate/classfull.png "Classfull division of IP addresses")
- classA - 2^31 addresses
- classB - 2^30 addresses
- classC - 2^29 addresses
- classD - 2^28 addresses
- classE - 2^28 addresses
