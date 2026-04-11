 # 🌐 Subnetting Notes 🚀

Building strong subnetting concepts step by step 💪

---

## 🍰 Real-Life Analogy (Classful vs Classless)

Imagine you have a **20 kg cake** 🍰

- It is already divided into **5 kg pieces (Classful addressing)**
- But you need **2 kg pieces**

👉 You cannot divide perfectly → **wastage happens**

### ✅ Solution: Classless Addressing (CIDR)

- Divide into exact required sizes  
- No wastage  

## 🔀 CIDR (Classless Inter-Domain Routing)

CIDR allows flexible allocation of IP addresses based on requirement.

👉 Instead of fixed classes (A, B, C), networks are assigned using **slash notation**

---

## 🔢 Slash Notation Example

Example:
192.168.1.0/26

- **/26** → first 26 bits are Network + Subnet  
- Remaining bits → Host  

### Details:

| Property | Value |
|----------|------|
| Subnet Mask | 255.255.255.192 |
| Block Size | 64 |
| No. of Addresses | 64 |
| Usable Hosts | 62 |

---

## 🧠 Another Example

IP: 10.0.0.0/16  

- /16 → 16 bits network  
- Remaining 16 bits → host  

👉 Total addresses:
2¹⁶ = 65,536  

---

## 🌍 CIDR Allocation (IANA & ISP)

- **IANA (Internet Assigned Numbers Authority)** manages global IP distribution  
- IANA allocates large blocks to **ISPs (Internet Service Providers)**  

👉 ISPs then distribute IPs to users based on requirement  

### Example:

- Company needs ~200 IPs  
- ISP assigns:  
  192.168.10.0/24 (256 addresses)

👉 No wastage compared to classful system  

---

## 💡 Key Insight

- CIDR = flexible allocation  
- Reduces IP wastage  
- Supports efficient network design  

---

## 🚀 Real Understanding

👉 Classful = fixed size (waste possible)  
👉 CIDR = custom size (efficient)
---

## 🧠 Subnetting Concept

- Subnetting = dividing a network into smaller networks
- Borrow bits from **Host ID (HID)** to create **Subnet ID (SID)**

## 🧮 Subnetting Formulas

### 🔹 Number of Subnets

Number of Subnets = 2ⁿ  

- n = number of bits borrowed from Host ID  

👉 Example:
If 3 bits are borrowed →  
Subnets = 2³ = 8  

---

### 🔹 Number of Hosts per Subnet

Number of Hosts = 2ʰ - 2  

- h = number of remaining host bits  

👉 (-2 because):
- 1 for Network Address  
- 1 for Broadcast Address  

👉 Example:
If 5 host bits →  
Hosts = 2⁵ - 2 = 30  

---

## 🥧 Subnet Division (Example: /26)

- Borrowed bits = 2  
- Subnets = 4  
- Block size = 64  

### Subnet Ranges

| Subnet | Binary | Range        |
|--------|--------|-------------|
| 1      | 00     | 0 – 63      |
| 2      | 01     | 64 – 127    |
| 3      | 10     | 128 – 191   |
| 4      | 11     | 192 – 255   |

## 🥧 Subnet Division (Visual)

![Subnet Division](https://github.com/user-attachments/assets/163c263d-8886-4a92-8c5d-000865285997)

Each slice represents one subnet of size 64 IP addresses.

## 📚 Important Address Concepts

| Term | Full Form | Meaning | Bit Pattern | Example |
|------|----------|--------|------------|---------|
| SM | Subnet Mask | Separates Network + Subnet from Host | NID + SID = 1, HID = 0 | 255.255.255.192 |
| NID | Network ID | Identifies the network | All host bits = 0 | 192.168.1.0 |
| HID | Host ID | Identifies a device in network | Host bits vary | 192.168.1.10 |
| DBA | Directed Broadcast Address | Last address of subnet | All host bits = 1 | 192.168.1.63 |

## ✅ Subnetting Validity Rules

To check whether subnetting is valid or not, follow these rules:

---

### 🔹 1. IP Addresses must be Contiguous

- All IPs in a subnet must be **continuous (no gaps)**
- They should form a proper block

👉 Example (Valid):
192.168.1.0 → 192.168.1.63  

👉 Example (Invalid):
192.168.1.0, 192.168.1.5, 192.168.1.20 ❌ (not continuous)

---

### 🔹 2. Block Size must be Power of 2

Block size = 2ⁿ  

👉 Valid block sizes:
- 2, 4, 8, 16, 32, 64, 128, 256  

👉 Example:
Subnet mask = 255.255.255.192  
→ Block size = 256 - 192 = 64 ✅  

---

### 🔹 3. First IP must be Divisible by Block Size

The starting IP of subnet must be a multiple of block size  

👉 Example:

Block size = 64  

Valid subnets:
- 192.168.1.0   ✅ (0 ÷ 64 = 0)
- 192.168.1.64  ✅ (64 ÷ 64 = 1)
- 192.168.1.128 ✅ (128 ÷ 64 = 2)
- 192.168.1.192 ✅ (192 ÷ 64 = 3)

Invalid subnet:
- 192.168.1.50 ❌ (not divisible by 64)

---

## 💡 Quick Check Trick

👉 Always check:
1. Block size (power of 2?)  
2. First IP divisible?  
3. Range continuous?  

If all correct → Subnet is VALID ✅  

---

## 🚀 Example Summary

Subnet: 192.168.1.64/26  

- Block size = 64  
- Range = 64 → 127  
- Continuous ✔  
- 64 divisible by 64 ✔  

👉 VALID subnet ✅

## 📊 Subnetting Examples (Solved)

---

### 🔹 Example 1

**Question:**  
Given IP: 192.168.1.0/26  
Find:
- Number of addresses  
- Range  
- Block ID  
- First Host  
- Last Host  
- DBA  

---

### ✅ Solution:

- Subnet Mask = 255.255.255.192  
- Block size = 256 - 192 = 64  

| Property | Value |
|----------|------|
| No. of Addresses | 64 |
| Block ID (Network ID) | 192.168.1.0 |
| Range | 192.168.1.0 – 192.168.1.63 |
| First Host | 192.168.1.1 |
| Last Host | 192.168.1.62 |
| DBA (Broadcast) | 192.168.1.63 |

---

### 🔹 Example 2

**Question:**  
Given IP: 192.168.1.128/26  
Find all required details  

---

### ✅ Solution:

- Subnet Mask = 255.255.255.192  
- Block size = 64  

| Property | Value |
|----------|------|
| No. of Addresses | 64 |
| Block ID (Network ID) | 192.168.1.128 |
| Range | 192.168.1.128 – 192.168.1.191 |
| First Host | 192.168.1.129 |
| Last Host | 192.168.1.190 |
| DBA (Broadcast) | 192.168.1.191 |

---

## 🌐 Supernetting

Supernetting is the **reverse of subnetting**

👉 Instead of dividing networks, we **combine multiple smaller networks into one larger network**

### 🔹 Purpose:
- Reduce routing table size  
- Improve efficiency  
- Used in CIDR  

👉 Example:
Combining:
- 192.168.0.0/24  
- 192.168.1.0/24  

→ Can form a larger block:
192.168.0.0/23  

---

## ⚖️ Subnetting vs Supernetting

| Feature | Subnetting | Supernetting |
|--------|-----------|-------------|
| Concept | Divide network | Combine networks |
| Purpose | Better management, security | Reduce routing complexity |
| Mask | Increases (/24 → /26) | Decreases (/24 → /23) |
| IP Usage | More networks, fewer hosts | Fewer networks, more hosts |
| Direction | One → Many | Many → One |

---
