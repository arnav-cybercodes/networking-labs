# IP Addressing ⛳
- IPv4(Internet Protocol Version 4) is a system used for identifying devices on a network.
- It is of 32 bits represented as 192.168.1.1 where each divided part is an octet i.e.  cosisting of 8 binary bits.
- Each octet ranges from **0-255**
- ![IPv4 Example](https://github.com/user-attachments/assets/45f9ceaf-dc07-4218-a3c4-3834e43d1d8b)
  Here, middle box contains IP Addresses in Octet format while right boc contains addresses in Binary format.

## 🌍 Types of IP Address

- **Private IP Address**
  👉 Used inside local networks
  👉 Not accessible from internet
  👉 Example ranges:
  - 192.168.x.x
  - 10.x.x.x
  - 172.16.x.x – 172.31.x.x

- **Public IP Address**
  👉 Assigned by ISP
  👉 Used to communicate over internet
  
# 🧠Breakdown of IPv4:
- It consists of two parts:NID(Network ID) and HID(Host ID).
- NID identifies the specific network.
- HID identifies a specific device on that network.  
- Now these IP Addresses are divided into Classes namely A,B,C,D,E
- where Class A use first 8 bits(octet) as NID and 24 bits for Host IDs.  
- Class B uses 16 bits as NID and rest 16 bits for Host IDs.
- Class C contains 24 bits of Network ID and rest as HID, and similarly so on.
- Example:192.168.1 → Network ID  
.1 → Host ID

- **Loopback Address**
  👉 127.0.0.1
  👉 Used to test your own system (localhost)

  ## 🚪 Default Gateway

- It is the router that connects your network to other networks
- Example: 192.168.1.1
- Used when sending data outside your network
  
## 🌐 Network Identification

A network communication system is identified using three main components:

- **Network** → Identified using **IP Address (Logical Address)**
- **Host** → Identified using **MAC Address (Physical Address)**
- **Process** → Identified using **Port Number**

---
💡 Note: MAC Address works at Data Link Layer while IP Address works at Network Layer (OSI Model)

## 🔌 Common Port Numbers

| Protocol | Port Number |
|----------|------------|
| SMTP (Simple Mail Transfer Protocol) | 25 |
| DNS (Domain Name System) | 53 |
| HTTP | 80 |
| HTTPS | 443 |
| FTP | 20, 21 |
| POP3 | 110 |
| IMAP | 143 |

---

## 🔁 Types of Communication

| Type | Meaning | Example |
|------|--------|--------|
| **Unicast (1:1)** | One sender → One receiver | Sending message to a friend |
| **Broadcast (1:All)** | One sender → All devices in network | ARP request |
| **Multicast (1:Many)** | One sender → Selected group | Live streaming |

### 📡 Types of Broadcast

- **Limited Broadcast Address (LBA)** → `255.255.255.255`  
  👉 All bits of IP address are **1**  
  👉 Reaches all devices in the local network only  

- **Directed Broadcast Address (DBA)** → Network-specific broadcast  
  👉 Formed by making **all Host ID bits = 1**  
  👉 Example: `192.168.1.255`  

💡 **Tip:**
- Limited Broadcast = Full IP is all 1s (`255.255.255.255`)  
- Directed Broadcast = Only **Host part is all 1s**, Network part remains same  

---

## 🎭 Network Mask (Subnet Mask)

- Used to separate **Network ID (NID)** and **Host ID (HID)**
- Represented like: `255.255.255.0`

👉 Helps in:
- Identifying network portion  
- Identifying host portion
  
 ## 🔀 Subnetting (Intro)

- Process of dividing a network into smaller networks
- Helps in better management and security
