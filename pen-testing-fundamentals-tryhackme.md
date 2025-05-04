# 🧰 TryHackMe - Pentesting Fundamentals Writeup

> **Platform:** TryHackMe  
> **Room:** Pentesting Fundamentals  
> **Difficulty:** Beginner  
> **Objective:** Understand the essential concepts and phases of penetration testing with hands-on examples.

---

## 🧠 Topics Covered

- Pentesting Lifecycle
- Types of Tests: Black-box, White-box, Grey-box
- Passive vs. Active Reconnaissance
- Enumeration & Scanning Basics
- Intro to Exploitation
- Common tools used in each phase

---

## 🔍 Reconnaissance

### 📌 Passive Reconnaissance

- No direct interaction with the target
- Tools & Techniques:
  - Google Dorking
  - WHOIS
  - Netcraft
  - Shodan


whois target.com

Active Reconnaissance
Direct interaction to discover open ports and services


nmap -sC -sV -oN scan.txt [Target-IP]
Nmap helps identify services and potential vulnerabilities



 Enumeration
Deeper look into services discovered during scanning

Examples:

SMB enumeration

FTP anonymous login

HTTP directory brute-force

enum4linux -a [Target-IP]

 Exploitation Basics
 
Introduced to Metasploit for exploiting known vulnerabilities

Hands-on practice in launching basic attacks safely in lab
msfconsole
use exploit/multi/...

Conclusion
✅ Room Completed
✅ Understood full pentesting cycle
✅ Gained experience with core tools and methodology

Author
Umar Farooq
Cybersecurity Student | TryHackMe Explorer
GitHub: TheRealUmarFarooq
