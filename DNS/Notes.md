# DNS (Domain Name System)

# The Purpose of DNS

1. DNS is used to resolve human readable names (google.com) to IP address
2. Machines such as pcs dont use names, they use addresses (ie. IPV4/IPV6)
3. Names are much easier for us to use and remember than IP addresses. 
4. When you type 'youtube.com' into a web browser, your device will ask a DNS Server for the IP address of youtube.com. 
5. The DNS server(s) your device uses can be manually configured or learned via DHCP.

If your device doesnt know the correct IP address it will automatically ask the server. To learn the ip address of youtube.com, pc1 sends a dns query message to its configured DNS server 8.8.8.8 . Then the DNS server replies, telling PC1 that the IP address is 172.217.25.110 . R1 router isnt acting as a DNS server or client. It is simply forwarding packets. So no DNS configuration is required on R1. They just need to perform their job of routing network traffic. 

DNS "A" record = used to map names of IPV4 addresses.
DNS "AAAA" (Quadrupal) record = used to map names of IPV6 addresses.

DNS uses both TCP and UDP.

Standard DNS queries/responses typically uses UDP. TCP is used for DNS messages greater than 512 bytes. In either case, port 53 is used. 

# DNS CACHE

Devices will save the DNS server's responses to a local DNS cache. This means they dont have to query the server every single time they want to access a particular destination. 

to see DNS cache -> ipconfig /displaydns

CNAME Record => Canonical Name. It basically maps a name with another name. 

ipconfig /flushdns

# Host File

Most devices have a 'hosts' file which simply a list of hosts and ip addresses. In windows it's in the  C:\Windows\System32\drivers\etc folder and the name simply 'hosts'. This isnt a DNS its a simple alternative to DNS.

# The Corrected Flow

1. PC 1 (Before PC 1 can send the ping, it has to know the IP address of youtube.com)

2. (DNS Query: "What is the IP of youtube.com?")

3. Router (The Router checks its own local cache. It has no entry for youtube.com, so it acts as a Forwarder)

4. (Forwarded DNS Query) 

5. Google DNS Server (Google’s server finds the entry in its database: youtube.com = 142.250.190.46)

6. (DNS Response with the IP address)

7. Router (The Router receives the answer, saves it for a few minutes, and passes it back to PC 1)

8. (IP Address delivered to PC 1)

9. PC 1 (Finally, PC 1 is able to send the Ping to the IP address, and the YouTube server sends the Reply)


# Commands

1. ipconfig /all

2. nslookup name 

3. ipconfig /displaydns

4. ipconfig /flushdns

5. ping ip-address -n number