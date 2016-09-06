# Basic LAN Administration
___
**IP address:**  Your virtual address.

**Local address:** `127.0.0.1`

**MAC address:** Your physical address, embedded into your NIC.

[Link to robust explanation](http://imgur.com/gallery/Y9Sa0)

*Note instructions are for UNIX based systems*

Most LAN are Class C Private networks. Not enough IPv4 address are left to give each device a Public IP Adress so NAT is used to assign private IP's in the LAN.

`ifconfig`

___
### What is my computer exposing?
Your computer communicates outside the LAN by opening ports, which are set by daemons, services, programs or you manually. They also must be allowed in your router, all well known ports are typically set to this(0-999).

`netstat -taln`

Check if a port at a given url is up or down? (This would test for a local server running on port 3000).

`nmap -p 3000 localhost`
___
### What the hell is ping and traceroute??
Ping is a common troubleshooting command that uses the ICMP protocol. It can also be used in DDOS attacks...

`ping 127.0.0.1`

`ping www.google.com`

Find IP address by FQDN.

`arp www.google.com`

Traceroute also uses ICMP and is used to trace the route your packets take to its destination.

`traceroute www.google.com`

`ip route`
___
### Who else is on the LAN?
NMAP is a great open source tool that allows you to essentialy map your network. Run the below command and replace the IP address with your LANS network address, typically one below your routers IP.


[Download and install NMAP here.](https://www.nmap.org)



`sudo nmap -sP 172.16.0.0/24`
