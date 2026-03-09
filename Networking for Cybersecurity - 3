# Networking for Cybersecurity - 3

## Goal
The goal of this project is to learn the basics of:

- Nmap scanning of localhost
- DNS basics
- HTTP basics
- Basic networking tools in Linux
- Simple Python networking scripts

---

# Commands I Used

```bash
nmap localhost
nmap -sV -A localhost
ip a
ifconfig
ss -tuln
netstat -tuln
curl http://example.com
curl -I http://example.com
nslookup google.com
dig google.com
What I Learned

Nmap (Network Mapper) is a tool used for network discovery and security auditing. It can scan hosts and detect open ports and running services.

DNS (Domain Name System) translates domain names (for example example.com) into IP addresses (for example 93.184.216.34).

HTTP (Hypertext Transfer Protocol) is a communication protocol used between web browsers and web servers.

Linux Commands
Check IP address
ip a

Displays:
IP address
Network interface
MAC address
Scan localhost
nmap localhost
Scans the local machine for open ports.
Detailed scan
nmap -sV -A localhost
Options:
-sV → detects service versions
-A → enables OS detection and additional scripts
Network information
ifconfig
Shows:
IP address
Network interface
MAC address
Check open ports
ss -tuln
Displays listening TCP and UDP ports.
Alternative command:
netstat -tuln
Shows:
TCP ports
UDP ports
Listening services
HTTP request
curl http://example.com
Fetches the content of a webpage.
curl -I http://example.com
Shows only the HTTP headers.
DNS lookup
nslookup google.com
Performs a DNS query.
dig google.com
Shows:
IP address
DNS server
DNS records

Python Code
Check if a Port is Open
import socket

host = "127.0.0.1"
port = 80

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
result = s.connect_ex((host, port))

if result == 0:
    print("Port is open")
else:
    print("Port is closed")

s.close()
Simple Port Scanner
import socket

target = "127.0.0.1"

print("Scanning", target)

for port in range(1, 1025):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.settimeout(0.5)

    result = s.connect_ex((target, port))

    if result == 0:
        print(f"Port {port} is open")

    s.close()
DNS Lookup with Python
import socket

domain = "google.com"

ip = socket.gethostbyname(domain)

print("IP address:", ip)
HTTP Request with Python
import requests

response = requests.get("https://example.com")

print(response.status_code)
print(response.text[:200])

Install the requests library if needed:
