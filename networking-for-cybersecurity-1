# Networking Basics – OSI Model

## Goal
To learn what the OSI model is and how it works.

## What I Learned
The **OSI Model** is a way to understand how computers send data to each other.  
It has **seven layers**, and each layer has a specific task. Each layer communicates with the layers above and below it.

Here are the seven layers, explained from top (7) to bottom (1):

### 7. Application Layer
- **Function:** This is the layer where programs interact with the network.  
- **Example:** Opening a website in a browser using **HTTP** or **HTTPS**.

### 6. Presentation Layer
- **Function:** Prepares data so that it can be understood by the computer. It can **encrypt, compress, or format** the data.  
- **Example:** When using HTTPS, this layer encrypts your data so it is secure during transmission.

### 5. Session Layer
- **Function:** Establishes and maintains the connection between two computers.  
- **Example:** When you log in to a website and stay logged in, the session layer manages that connection.

### 4. Transport Layer
- **Function:** Breaks the data into small segments and ensures they arrive correctly and in order.  
- **Protocols:** TCP (reliable) or UDP (faster, less reliable).  
- **Example:** Your HTTP request is divided into packets, sent to the server, and reassembled on the other side.

### 3. Network Layer
- **Function:** Determines the best path for data to travel from the source to the destination.  
- **Example:** Uses IP addresses to deliver packets to the correct server.

### 2. Data Link Layer
- **Function:** Sends data between devices on the same local network using **MAC addresses**.  
- **Example:** Sends the data to the correct computer or router within your home network.

### 1. Physical Layer
- **Function:** Transmits the actual signals over physical media.  
- **Example:** Data travels via **cables, Wi-Fi, or optical fiber**.

## Example: Opening a Website
Here’s how data flows through the OSI layers when opening a website like **google.com**:

| Layer | What Happens |
|-------|--------------|
| 7 – Application | You type google.com in your browser. |
| 6 – Presentation | Data is encrypted (HTTPS). |
| 5 – Session | A secure connection is established (TLS session). |
| 4 – Transport | Data is broken into packets (TCP). |
| 3 – Network | Each packet gets an IP address. |
| 2 – Data Link | Packets are sent to your router using MAC addresses. |
| 1 – Physical | Packets travel over Wi-Fi or cables to the router. |

---

💡 **Tip:**  
You can remember the OSI layers with the mnemonic:  
**“All People Seem To Need Data Processing”** → Application, Presentation, Session, Transport, Network, Data Link, Physical.
