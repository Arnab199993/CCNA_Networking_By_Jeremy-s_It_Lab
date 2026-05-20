In dynamic NAT, the router dynamically maps inside local addresses to inside global addresses are needed.

An ACL is used to identify which traffic should be translated.

i. If the source ip is permitted by the ACL, the source IP will be translated. 
ii. If the source ip is denied by the ACL, the source IP will not be translated. The traffic will not be dropped.

A NAT pool is used to define the available inside global addresses.

Although they are dynamically assigned, the mappings are still one-to-one (One inside local IP address per inside global IP address).

If there aren't enough inside global IP addresses available (=all are currently being used), it is called 'NAT pool exhaustion'. 

----> If a packet from another inside host arrives and needs NAT but there are no available addresses, the router will drop the packet. 

----> The host will be unable to access outside networks until one of the inside global IP addresses becomes available. 

----> Dynamic NAT entries will time out automatically if not used, or you can clear them manually.

# NAT Pool Exhaustion

A packet with source ip 192.168.0.167 arrives at R1. It is translated to 100.0.0.1 and then forwarded. A packet with source ip 192.168.0.168 arrives at R1. It is translated to 100.0.0.2 and then forwarded. Now those ten inside global IP addresses 100.0.0.1 through 10 all are being used. If host 192.168.0.98 tries to send some traffic to the internet, as there are no addresses available, so the router will drop the packet. It is called NAT pool exhaustion.

# PAT (NAT Overload)

1. PAT (aka NAT overload) translates both the IP address and the port number (if necessary)

2. By using a unique port number for each communication flow, a single public IP address can be used by many different internal hosts. (port number are 16 bits = over 65000 available port numbers).

3. The router will keep track of which inside local address is using which inside global addresses and port.

4. Because many inside hosts can share a single public IP,PAT is very useful for preserving public IP addresses, and it is used in networks all over the world.

5. PAT is the most widely used because it allows so many inside hosts to share a single public ip address.


