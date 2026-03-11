#Networking Basics – Firewall Traffic Flow
##Goal

To understand how data flows through a firewall and how it is filtered.

##What I Learned

A firewall is a network security device that monitors and controls incoming and outgoing traffic based on rules.
It acts as a barrier between your internal network and the internet or other untrusted networks.

Traffic through a firewall can be allowed, blocked, or logged depending on the firewall rules.

Here’s how traffic flows through a firewall:

1. Incoming/Outgoing Traffic

Function: Data packets from your device or from the internet arrive at the firewall.

Example: You try to access a website, or someone tries to access your network.

2. Packet Inspection

Function: The firewall examines each packet against its rules.

Checks include: IP addresses, port numbers, protocols, and content (for advanced firewalls).

Example: Only HTTP/HTTPS traffic might be allowed, while suspicious ports are blocked.

3. Decision Making

Function: The firewall decides whether to allow, block, or log the traffic.

Example: A request to your web server on port 80 is allowed, but an unknown service request on port 1234 is blocked.

4. Forwarding or Blocking

Function: Traffic that is allowed is forwarded to the destination, while blocked traffic is discarded or logged.

Example: Allowed traffic reaches your computer or server; blocked traffic never enters your network.

5. Logging and Alerts

Function: Many firewalls keep a log of traffic events for monitoring or security audits.

Example: You can see if someone tried to access a blocked port or suspicious IP addresses.

Example: Accessing a Website

Here’s how a typical HTTP request flows through a firewall:

Step	What Happens
1 – Incoming Traffic	Your computer sends a request to example.com.
2 – Packet Inspection	Firewall checks the packet’s IP, port (80), and protocol (HTTP).
3 – Decision	Firewall rules allow HTTP traffic.
4 – Forwarding	Request is sent to the internet/server.
5 – Response	Server responds; firewall inspects response and forwards it back to your computer.
