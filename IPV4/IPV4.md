1. Network connectivity between end hosts on diffeent networks (ie. outiside of the LAN)
2. Provides logical addressing (IP addresses)
3. Provides path selection between source and destination
4. Routers operate at Layer 3

In 192.168.1.0/24 192.168.1 the network itself and only the last 0 indicates the end host which is pc itself.
And /24 indicates which part of address represents network and which part represent the end host which is pc.

IP means internet protocol is a primary layer 3 protocol is used today. And v4 is the version used in most networks.Source Ip Address and Destination IP Address both are 32 bits (4 bytes) in length.It strecteches from 0 to 31.

192.168.1.254 where 

192 = 8 bits
168 = 8 bits
1 = 8 bits
254 = 8 bits

Binary are difficult to understand thats why ip addresses are written in dotted decimal.

the 8 bit group is called octet.
192 = 11000000 (octet)

Binary bits can extends too 255.

An IPV4 address is really a series of 32 bits

in 192.168.1.254/24 the first 24 bits is the network portion of the address and the remaining 8 represents the end hosts.

First 24 bits are the first 3 octates.(192.168.1) and 254(the last 8 bit) is host.

IPV4 addresses are split up into 5 different claases.The class of the IPV4 address determined by 5 first octet of the address.

# IPV4 address classes
1. class A (0-127): If the first octet begins with 0 that means the numeric range of the first octet is from 0 to 127.Prefix length /8

2. Class B (128-191) : If the first octet begins with 10 that means the numeric range of the first octet is from 128 to 191. Prefix length /16

3. Class C (192-223) : If the first octet begins with 110 that means the numeric range of the first octet is from 192 to 223. Prefix length /24

4. Class D (224-239) : If the first octet begins with 1110 that means the numeric range of the first octet is from 224 to 239.

5. Class E (240-255) : If the first octet begins with 1111 that means the numeric range of the first octet is from 240 to 255.

The classof address will be focuses on A,B and C. Addresse is class D is reserved for multicast addresses. Multicast is another kind of addresses separated from unicast and broadcast addresses.class E addresses used for experimental usage.

# The end of the class A range is usually considered to be 126. Not 127. Because 127 is reserved for loopback addresses.

# Loopback Addresses
1. Address range 127.0.0.0 - 127.255.255.255
2. Used to test the "network stack" (think OSI,TCP/IP model) on the local device.

1. Class A : /8 => 255.0.0.0 (11111111 00000000 00000000 00000000)
2. Class B : /16 (255.255.0.0 11111111 11111111 00000000 00000000)
3. Class C : /24 (255.255.255.0 11111111 11111111 11111111 00000000)

# On juniper devices we use classes using /

# /8, /16, /24 are CIDR notations that represent subnet masks.A subnet mask (like 255.255.255.0) is the full form.CIDR (Classless Inter-Domain Routing) is the modern way to represent IP address ranges and subnetting using this / notation.

in 192.168.1.0/24 as the host portion is 0 the last portion is all 0s. This address is network address and network address cant be assigned to the host.





