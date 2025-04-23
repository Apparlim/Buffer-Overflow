

---

# Buffer Overflow Lab

##  Overview

This project is a hands-on **Buffer Overflow Lab** aimed at understanding and exploiting buffer overflow vulnerabilities. The lab follows secure coding practices and explores various security mechanisms implemented in modern operating systems.

##  Table of Contents
- [Overview](#-overview)
- [Introduction](#-introduction)
- [Lab Setup](#-lab-setup)
  - [Required Tools](#required-tools)
  - [Steps](#steps)
- [Attack Implementation](#-attack-implementation)
  - [Step 1: Identifying the Vulnerability](#step-1-identifying-the-vulnerability)
  - [Step 2: Writing the Exploit](#step-2-writing-the-exploit)
  - [Step 3: Exploiting the Vulnerability](#step-3-exploiting-the-vulnerability)
- [Security Mechanisms](#-security-mechanisms)
  - [Address Space Randomization (ASLR)](#address-space-randomization-aslr)
  - [StackGuard (GCC Protection)](#stackguard-gcc-protection)
  - [Non-Executable Stack (NX Bit)](#non-executable-stack-nx-bit)
- [Conclusion](#-conclusion)
- [References](#-references)

---

##  Introduction

Buffer overflow is one of the most critical security vulnerabilities that allows attackers to overwrite adjacent memory locations. This lab demonstrates how buffer overflow occurs, how attackers can exploit it, and the defense mechanisms that prevent such attacks.

---

## Lab Setup

### Required Tools
- **Ubuntu Linux (VM recommended)**
- **GDB (GNU Debugger)**
- **GCC Compiler**
- **Python for Exploit Development**

### Steps
1. **Disable security mechanisms** such as Address Space Randomization and StackGuard.
2. **Compile vulnerable code** using GCC with appropriate flags.
3. **Use GDB** to analyze memory and stack layout.

---

##  Attack Implementation

### Step 1: Identifying the Vulnerability
- The vulnerable C program contains an unsafe `strcpy()` function that does not perform bounds checking.

### Step 2: Writing the Exploit
- A **malicious payload (shellcode)** is crafted to gain control of the execution.
- A **badfile** is created to inject the shellcode.

### Step 3: Exploiting the Vulnerability
- A buffer overflow attack is executed to manipulate the return address and execute arbitrary code.

---

##  Security Mechanisms

### Address Space Randomization (ASLR)
- Helps prevent buffer overflow attacks by **randomizing memory addresses**.
- **Command to enable ASLR:**  
  ```bash
  sysctl -w kernel.randomize_va_space=2
  ```

### StackGuard (GCC Protection)
- Protects against stack-based buffer overflow attacks by using **canary values**.
- **Command to compile without StackGuard:**  
  ```bash
  gcc -fno-stack-protector -z execstack -o vulnerable vulnerable.c
  ```

### Non-Executable Stack (NX Bit)
- Prevents the execution of injected shellcode by marking the stack as **non-executable**.
- **Command to enable non-executable stack:**  
  ```bash
  gcc -z noexecstack -o vulnerable vulnerable.c
  ```

---

##  Conclusion

### Key Takeaways
- Buffer overflow is a serious security vulnerability that can be **exploited to execute arbitrary code**.
- **Proper memory management** and **secure coding practices** are essential to mitigate such risks.
- Modern operating systems use **multiple security mechanisms** like ASLR, StackGuard, and NX Bit to protect against buffer overflows.

---

##  References

- Syracuse University Buffer Overflow Lab
- Wenliang Du’s Secure Coding Lab
- Linux Exploitation Techniques  
- GNU Debugger (GDB) Official Documentation
  

---
📸 Screenshots

![Screenshot 2025-02-11 175441](https://github.com/user-attachments/assets/ef6dff35-0c37-45d6-b8e6-741b0c479846)

![Screenshot 2025-02-08 141015](https://github.com/user-attachments/assets/9cd773ef-082f-4c86-a10f-0288c5640e0e)




