Things we'll cover
IPV4 address classes (review,clarification)
Finding the 
1. Maximum nummber of hosts
2. Network address
3. Broadcast address
4. First usable addresses
5. Last usable addresses of a particular network
6. Configuring IP addresses on Cisco devices

# In IPV4 classes in A first number starts with 1 and ends with 126 (0-127) becuase like 127 0 is also reserved.

# Class C

In class C the host portion is 2 to the power 8. The host portion is 8 bits.

Host portion = 8 bits = 2 to the power 8 = 256

If the host portion is all 0s = network address(Network ID) and it cant be assigned to a host. (00000000)

If the host portion is all 1s = broadcast address and it also cant be assigned to a host. (11111111)

Maximum hosts per network = 2 to the power 8 -2 = 254. 

# Class B

In class B the host portion is 2 to the power 16. The host portion is 16 bits.

Host portion = 16 bits = 2 to the power 16 = 65,536.

Host portion all 0s = network address (network ID)
Host portion all 1s = broadcast address

Maximum hosts per network = 2 to the power 16 -2 = 65,534. 

# Class A

In class C the host portion is 2 to the power 24. The host portion is 24 bits.

Host portion = 24 bits = 2 to the power 24 = 16,777,216

Host portion all 0s = network address (network ID)
Host portion all 1s = broadcast address

Maximum hosts per network = 2 to the power 24 -2 = 16,777,214

Maximum hosts per network = 2 to the power n -2 (n = number of host bits)

# Class C

# First usable address

192.168.1.1/24

# Last usable address

192.16.1.254/24


# Class B

# First usable address

172.16.0.1/16

# Last usable address

172.16.255.254/16


# Class A

# First usable address

10.0.0.1/8

# Last usable address

10.255.255.254/8


# Quiz 1
Pc 1 has an ip address of [43.109.23.12/8]

Network address : 43.0.0.0
Maximum number of hosts in the network : 16,777,214
Network broadcast address : 43.255.255.255
First usable address of the network : 43.0.0.1
Last usable address of the network:43.255.255.254


