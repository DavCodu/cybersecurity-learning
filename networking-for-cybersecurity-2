# Networking for Cybersecurity -2

## Goal

The goal of this project is to understand some of the basic networking protocols used in cybersecurity:

* IP (Internet Protocol)
* UDP (User Datagram Protocol)
* TCP (Transmission Control Protocol)

Understanding these protocols is important for networking, penetration testing, and cybersecurity analysis.

---

# What I Learned

## IP – Internet Protocol

IP is a protocol used for communication between computers in a network.
Its main purpose is to deliver data packets from one computer to another.

### Key Characteristics

* Devices are identified using IP addresses (IPv4 and IPv6)
* Responsible for addressing and routing packets across networks
* Delivers packets but does not guarantee packet order or reliability
* Used by almost all internet communication protocols

### Example

An IP address works like a postal address that tells the internet where data should be delivered.

# UDP – User Datagram Protocol

UDP is a transport protocol that works on top of IP and allows computers to communicate quickly.

### Key Characteristics

* **Fast and simple**
* **Connectionless protocol**
* **Does not guarantee delivery**
* **Does not guarantee packet order**
* Used when **speed is more important than reliability**

### Common Uses

* Online games
* Video streaming
* VoIP (Voice over Internet Protocol)

VoIP is a technology that allows voice communication over the internet instead of traditional phone networks.

### Example

In an online game, losing a few packets is better than having network delay (latency).

# Example Python Code – UDP Client and Server

## UDP Client

import socket

target_host = "127.0.0.1"
target_port = 9999

client = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

while True:
    message = input("[CLIENT]: ")
    client.sendto(message.encode(), (target_host, target_port))

    data, server = client.recvfrom(1024)
    print("[SERVER]:", data.decode())


## UDP Server

import socket

bind_ip = "127.0.0.1"
bind_port = 9999

server = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server.bind((bind_ip, bind_port))

print(f"[*] UDP Server listening on {bind_ip}:{bind_port}")

while True:
    data, addr = server.recvfrom(1024)
    print(f"[*] Received from {addr}: {data.decode()}")

    server.sendto(b"ACK from UDP server", addr)


# TCP – Transmission Control Protocol

TCP is a transport protocol that works with IP but adds reliability and connection management.

### Key Characteristics

* **Connection-oriented protocol**
* **Guarantees packet delivery**
* **Ensures packets arrive in the correct order**
* Uses a **TCP three-way handshake** to establish a connection

The handshake process allows the client and server to confirm that both sides are ready to communicate.

### Common Uses

* Websites (HTTP / HTTPS)
* Email (SMTP, IMAP)
* File transfers (FTP)

TCP is used when reliability is more important than speed.

# Example Python Code – TCP Client and Server

## TCP Client

import socket

target_host = "127.0.0.1"
target_port = 9999

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect((target_host, target_port))

while True:
    message = input("[CLIENT]: ")
    client.send(message.encode())

    response = client.recv(4096)
    print("[SERVER]:", response.decode())

## TCP Server

import socket
import threading

bind_ip = "127.0.0.1"
bind_port = 9999

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind((bind_ip, bind_port))
server.listen(5)

print(f"[*] Listening on {bind_ip}:{bind_port}")

def handle_client(client_socket):
    while True:
        data = client_socket.recv(1024)

        if not data:
            break

        print("[CLIENT]:", data.decode())

        response = input("[SERVER]: ")
        client_socket.send(response.encode())

    client_socket.close()

while True:
    client, addr = server.accept()

    print(f"[*] Accepted connection from {addr[0]}:{addr[1]}")

    client_handler = threading.Thread(
        target=handle_client,
        args=(client,)
    )

    client_handler.start()


# Skills Practiced

* Networking fundamentals
* Understanding transport protocols
* Python socket programming
* Client-server communication
* Basic networking concepts used in cybersecurity
