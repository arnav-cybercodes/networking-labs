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

---

## 🧮 Bit Weight Understanding
