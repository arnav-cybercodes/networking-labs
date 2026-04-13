# Error Control 🚀

Error control ensures that data transmitted over a network is **accurate and reliable**.
"In Cybersecurity, error control is the foundation of the Integrity pillar of the CIA Triad. Without CRC, we couldn't distinguish between a random bit-flip and a malicious packet injection."

It is divided into two main processes:

## 1. Error Detection
Identifying whether an error has occurred during transmission.

## 2. Error Correction
Locating and fixing the error.

---

# Types of Errors

## 🔹 Single Bit Error
- Only **one bit** is changed (0 → 1 or 1 → 0)
- Caused by **low noise**
- Easy to detect

👉 Action:
- If detected → Retransmission
- If not → Accept data

---

## 🔹 Burst Error
- **Multiple bits** are changed
- More common in real-world communication

👉 For correction:
- Need:
  - Number of error bits
  - Location of error bits

If:
- Data bits = n  
- Error bits = k  

👉 Possible error locations: nCk

---

# Error Detection Concept

To detect errors, we add **redundant bits (extra bits)**.

✔ Known to both sender and receiver  
✔ Used to verify integrity of data  

If received data matches expected pattern → ✅ No error  
Else → ❌ Error detected  

---

# Error Detection Techniques

## 1. Simple Parity Check

Adds **1 parity bit**.

### Even Parity
Total number of 1s (including parity bit) = **even**

### Odd Parity
Total number of 1s = **odd**

### Properties:
- Detects all **single-bit errors**
- Cannot detect **even number of bit errors**

---

## 2. Two-Dimensional Parity (2D Parity)

- Data arranged in **rows and columns**
- Parity added for both:
  - Rows
  - Columns

### Advantages:
- Detects **single-bit errors**
- Can also **correct single-bit error**

### Limitations:
- Detects some multi-bit errors (not all)
- 4-bit errors → sometimes undetected

---

## 3. Checksum

- Data divided into **equal-sized segments**
- All segments added together
- Complement of sum is sent as checksum

### Receiver:
- Adds all received segments + checksum
- If result = valid → No error

---
# CRC (Cyclic Redundancy Check) 🚀

CRC is an **error detection technique** used to check whether data is transmitted correctly.

It uses **modulo-2 division (XOR division)** to detect errors.

---

# 🔹 Basic Idea

- Sender adds **redundant bits (CRC)** to data  
- Receiver checks if data is intact using same process  

👉 If error occurs → data becomes invalid  

---

# 🔧 Key Terms

- **Data Word (D)** → Original data  
- **Generator (G)** → Divisor (predefined pattern)  
- **Remainder (R)** → CRC bits  
- **Codeword (C)** → Data + CRC  

---

# ⚙️ CRC Process

## 🔸 Sender Side

### Step 1: Append Zeros
- Let generator degree = **r**
- Append **r zeros** to data  

Example: Data=100100 r=3 then ➡️ 100100000

---

### Step 2: Modulo-2 Division
- Divide (Data + zeros) by Generator  
- Use **XOR operation** (no carry/borrow)

👉 Result:
- Quotient → ignore  
- Remainder → CRC  

---

### Step 3: Form Codeword
Codeword = CRC + Data
👉 This is transmitted

---

## 📡 Receiver Side

### Step 1:
- Receive codeword  

### Step 2:
- Divide by same generator  

### Step 3: Check Remainder

- If remainder = **0** → ✅ No Error (Accepted)  
- If remainder ≠ **0** → ❌ Error (Retransmission required)  

---
#Core Logic:
Valid Codeword ➗ Generator Remainder = 0

If any bit changes:

Remainder ≠ 0 Error detected

# 🔄 Flow Summary

### Sender:

Data → Append zeros → Divide → CRC → Send (Data + CRC)

### Receiver:

Received → Divide → Check remainder → Accept / Reject

---
[error-control](https://github.com/user-attachments/assets/f44f3277-2bb5-4928-bba7-bfa59b23e082)


# 🔢 Polynomial Representation

- Data → D(x)  
- Generator → G(x)  
- Codeword → C(x)  
- Remainder → R(x)  

### Formula:
C(x) = D(x) × x^r + R(x)

Where:
- r = degree of generator  

---

# 🔥 Important Points

✔ Uses **modulo-2 division (XOR)**  
✔ No carry or borrow  
✔ Very effective for **burst error detection**  
✔ Used in real-world systems (Ethernet, networks)

---

# 🚀 Simple Understanding

- Sender creates a **check pattern (CRC)**  
- Receiver verifies it  
- If pattern breaks → error  

---

# ✅ Final Conclusion

CRC is a **powerful and reliable error detection technique** that ensures data integrity during transmission.

# Error Correction

## 🔹 Hamming Code

- Used for **error correction**
- Can:
  - Detect up to **2-bit errors**
  - Correct **1-bit error**

---

# Hamming Distance

Defined as:
👉 Minimum number of bit changes required to convert one codeword to another

If:Hamming Distance = d

Then:
- Detect up to → (d - 1) bit errors

---

# Summary 🧠

| Technique | Detect | Correct |
|----------|--------|--------|
| Parity | Single bit | ❌ |
| 2D Parity | Single + some multi-bit | ✅ (1-bit) |
| Checksum | Good | ❌ |
| CRC | Very strong | ❌ |
| Hamming Code | Yes | ✅ (1-bit) |

---

# Key Takeaways 🚀

- Errors are unavoidable in transmission
- Redundant bits help detect errors
- CRC is widely used in real systems
- Hamming code helps in correction
