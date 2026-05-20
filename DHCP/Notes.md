# DHCP (Dynamic Host Configuration Protocol)

DHCP allows DHCP clients, usually end devices like PCs, Phones etc to automatically learn which ip address to use from a DHCP server, instead of us having to manually configure it.

1. DHCP is used to allow hosts to automatically/dynamically learn various aspects of their network configuration, such as ip address, subnet mask, default gateway, DNS server, etc, without manual/static configuration. 

2. It is an essential part of modern networks. when you connect a phone/laptop to wifi, do you ask the network admin which ip address, subnet mask, default gateway, etc, the phone/laptop should use?

3. Typically used for 'client devices' such as workstations (PCs), phones, etc.

4. Devices such as routers, servers, etc, are usually  manually configured. 

5. In small network (such as home networks) the router typically acts as the DHCP server for hosts in the LAN.

6. In larger network, the DHCP server is usually a Windows/Linux server. 

# The basic functions of DHCP

Preferred in IPV4 address. Preferred means This pc was previously assigned the IP address by the DHCP server. so it asked to receive the same address again this time. 

1. Lease Time : IPCONFIG /ALL displays what time the lease was obtained, and what time it will expire. 

2. Release IP address : ipconfig /release. So it can ask again for ip address.

3. DHCP server uses port 67 and DHCP client uses port 68

4. ipconfig /renew to get a new ip address. 

# Process that a DHCP client goes through to get an IP address from a DHCP server.

1. D (Discover) : ( Are there any DHCP servers in the network? I need an ip address. )  The first message is DHCP discover message. Its a broadcast message from client. 

2. O (Offer) : ( How about this ip address? ). It is sent from the DHCP server to the client, offering an address for the client to use, as well as other information like default gateway, DNS server, etc. 

3. R (Request) : ( I want to use the IP address you offered me. ). Next message is the DHCP request message. It is sent from the DHCP client to the server, telling the server that it wants to use the ip address it was offered. There may be multiple DHCP servers on the local network, and all of them will reply to the clients Discover message with an Offer. So the client has to tell which server it is accepting the offer from and request to use that ip address. Typically the client will accept the first offer it receives. 

4. A (Ack) : Now the final message in the process, the DHCP Ack, acknowledgement. This is sent from the server to the client, confirming that the client may use the requested ip address. Once this message is received the client finally configures the ip address on its network interface. 

# DHCP D-O-R-A

1. Discover -> Client to server -> Broadcast

2. Offer -> Server to client -> Broadcast or Unicast

3. Request -> Client to Server -> Broadcast

4. Ackowledge -> Server to Client -> Broadcast or Unicast

5. Release -> Client to Server -> Unicasta

# DHCP relay

1. Some network engineers might choose to configure each router to act as the DHCP server for its connected LANs.

2. However, large enterprises often choose to use a centralized DHCP server.

3. If th server is centralized, it won't receive the DHCP clients' broadcast DHCP messages. (broadcast messages dont leave the subnet)

4. To fix this, you can configure a router to act as a DHCP relay agent.

5. The router will forward the clients' broadcast DHCP messages to the remote DHCP server as unicast messages.

6. The router will forward the clients' broadcast DHCP messages to the remote DHCP server as unicast messages. 



