# 📡 Flow Control in Networking

## 🔹 What is Flow Control?

Flow control is a technique used to control the rate of data transmission between sender and receiver so that the receiver is not overwhelmed with too much data.

---

## ⏱️ Types of Delays

### 1. Transmission Delay

Transmission delay is the time required to send all bits of a message into the channel.

### 📌 Formula:
Transmission Delay (Td) = Length of Message / Bandwidth

- Bandwidth = number of bits per second (bps)

### 📌 Example:
If message = 1000 bits and bandwidth = 100 bps
Td = 1000 / 100 = 10 seconds

---

### 2. Propagation Delay

Propagation delay is the time taken by a signal to travel from sender to receiver.

### 📌 Formula:
Propagation Delay (Pd) = Distance / Speed

### 📌 Example:
Distance = 1000 km, Speed = 2 × 10⁸ m/s
Pd = 1000000 / (2 × 10⁸) = 0.005 sec

---

## 📊 Data vs Bandwidth Table

| Unit  | Data (Binary) | Bandwidth (Decimal) |
|------|--------------|---------------------|
| Kilo | 2¹⁰ = 1024   | 10³                 |
| Mega | 2²⁰ = 1024²  | 10⁶                 |
| Giga | 2³⁰ = 1024³  | 10⁹                 |

---

## 🌐 Networking Layers

### 🔹 Data Link Layer
- Address: MAC Address (48 bits)
- Communication: Node-to-node / Hop-to-hop

---

### 🔹 Network Layer
- Address: IP Address (32 bits)
- Communication: Source to Destination

---

### 🔹 Transport Layer
- Address: Port Number (16 bits)
- Communication: End-to-end / Process-to-process

---

## ⏳ Queuing Delay

Queuing delay occurs when packets wait in buffer queues before being processed.

👉 Happens when:
- Sending speed > Processing speed

---
![Layers](https://github.com/user-attachments/assets/c54c5140-a697-4506-897a-5031c708a3c9)


## ⚙️ Processing Delay

Processing delay is the time taken to process packets in:
- Network Layer
- Data Link Layer
- Physical Layer

---
![Message](https://github.com/user-attachments/assets/12d1c361-8add-4349-bd9d-e68f8b7bc8e5)

# 🔁 Flow Control Protocols

## 1. Stop and Wait ARQ

### 🔹 Problem in Stop & Wait:

1. **Lost Data Packet**
- Receiver waits forever
- Sender waits for ACK forever  
👉 Deadlock situation

2. **Lost Acknowledgement**
- Sender keeps waiting
- Data not retransmitted

3. **Delayed Acknowledgement**
- Sender gets confused with next packet

---

## 🔹 Solution: Stop & Wait ARQ (Automatic Repeat Request)

- Sender sets a **timer**
- If ACK not received → resend data
- Helps detect:
  - Lost data
  - Lost acknowledgement

---

## 🔹 Key Features:

- Sequence number (data)
- Sequence number (ACK)
- Timeout timer
- ACK is always for **next expected frame**

---
In stop and wait ARQ,

Sender window size is 1.
This allows the sender to keep only one frame unacknowledged.
So, sender sends one frame and then waits until the sent frame gets acknowledged.
After receiving the acknowledgement from the receiver, sender sends the next frame.
![stopwait](https://github.com/user-attachments/assets/18481877-447f-470b-9730-7f159567b33f)

 ![stop-wait](https://github.com/user-attachments/assets/5acbbcc3-15b1-483f-a842-f1efdea94ef9)

Here,

Sender uses Tt time for transmitting the packet over the link.
Then, sender waits for 2 x Tp time.
After 2 x Tp time, sender receives the acknowledgement for the sent frame from the receiver.
Then, sender sends the next frame.
This 2 x Tp waiting time is the actual cause of less efficiency.
 
