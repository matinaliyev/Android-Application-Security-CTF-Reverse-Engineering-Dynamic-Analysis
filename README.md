# Android Application Security CTF – Reverse Engineering & Dynamic Analysis

A comprehensive **Android security challenge series** focused on **APK reverse engineering, cryptographic analysis, and runtime instrumentation**.

This project documents the systematic analysis and exploitation of **8 Android CTF challenges**, using both **static and dynamic techniques** to uncover hardcoded secrets, broken cryptography, insecure storage, and native code vulnerabilities.

---

## Objectives

- Reverse engineer Android APKs to uncover hidden logic and secrets
- Analyze **smali**, **JNI**, and **native libraries**
- Break insecure cryptographic implementations
- Perform **dynamic analysis** using Frida
- Demonstrate real-world Android security weaknesses and attack paths

---

## Challenge Overview

| Challenge | Focus Area | Key Techniques |
|--------|-----------|---------------|
| 1. Serial Key Missing | Hardcoded crypto | Smali analysis, SQLite inspection, AES decryption |
| 2. Knights & Assets | Steganography | Asset inspection, steghide, binwalk, Hashcat |
| 3. Decompile It Twice | JNI & Native Code | Frida, Ghidra, native library reversing |
| 4. What Is the Combination | Runtime secrets | Smali analysis, Frida hooks, AES |
| 5. Salted & Hashed | Crypto misuse | AES-CBC analysis, weak hashing |
| 6. Can You Open It? | Device security | Emulator rooting, filesystem analysis |
| 7. Where Is the Key? | Asymmetric crypto | RSA key reconstruction |
| 8. Catch Them All | Cipher analysis | Frida, Vigenère decryption |

---

## Tools & Techniques

### Static Analysis
- **apktool** (APK decompilation)
- Smali code inspection
- AndroidManifest & resource analysis
- SQLite database extraction
- Native library reversing (Ghidra)

### Dynamic Analysis
- **Frida** (Java & JNI hooking)
- Runtime function interception
- Decrypted string and URL extraction
- Emulator instrumentation

### Cryptography & Exploitation
- AES-CBC decryption
- RSA-2048 key reconstruction
- Hash cracking (Hashcat + rockyou)
- Steganography (steghide, binwalk)
- Classical ciphers (Vigenère)

---

## Representative Findings

### 🔴 Insecure Cryptographic Practices
- Hardcoded AES keys and IVs in smali code
- Reusable salts and static encryption material
- Plaintext credentials stored locally

### 🔴 Broken Secret Management
- Secrets embedded in assets and resources
- Sensitive values retrievable via runtime hooks
- Keys stored inside native libraries

### 🔴 JNI & Native Code Weaknesses
- Sensitive logic hidden in `.so` files
- Flags reconstructed via native disassembly
- Security through obscurity failures

### 🔴 Device-Level Weaknesses
- Emulator rooting allowed full bypass of lock screen
- Sensitive data exposed in system storage

---
APK
↓
Static Analysis (apktool / smali)
↓
Identify crypto / JNI usage
↓
Dynamic Hooking (Frida)
↓
Extract runtime secrets
↓
Decrypt / reconstruct flag


---

## Security Lessons Learned

- Hardcoded secrets are never safe
- Client-side cryptography is fundamentally untrusted
- JNI and native code do not guarantee secrecy
- Debugging interfaces dramatically increase attack surface
- Runtime instrumentation defeats most obfuscation techniques

---

## Ethical Disclaimer

- All challenges were completed in **isolated, controlled environments**
- No real-world applications or users were targeted
- This project is strictly for **educational and defensive security research**

---

## Author

**Matin Aliyev**

- Performed full static and dynamic analysis of all challenges
- Implemented Frida scripts and cryptographic attacks
- Reversed Android and native binaries
- Focused on real-world mobile security implications

---

## ⭐ Why This Project Matters

This project demonstrates **hands-on Android security expertise**, including:

- Mobile reverse engineering
- Runtime instrumentation
- Cryptography analysis
- Secure coding awareness
- Offensive techniques used for defensive insight

These skills directly translate to **Mobile AppSec, Red Team, and Security Engineering roles**.
## 🧠 Example Attack Flow

