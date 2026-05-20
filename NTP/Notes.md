All devices have an internal clock (routers, switches, your PC etc)
Syslog the protocol used to keep device logs. 

# NTP

Manually configuring the time on device is not scalable.
The manually configured clocks will drift, resulting in inaccurate time. 
NTP (Network Time Protocol) allows automatic syncing of time over a network.
NTP client requests from NTP servers.
A device can be NTP server and NTP client at a same time. 

Some NTP servers are better than others. The distance of an NTP server from the original reference clock is called stratum. 

NTP uses UDP port 123 to communicate. 

# Reference Clock

A Reference clock is usually a very accurate time device like an atomic clock or gps clock.
Reference clocks are stratum 0 within the NTP hierarchy. 
NTP servers  directly connected to reference clock stratum 1.