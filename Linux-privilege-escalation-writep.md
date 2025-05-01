# Linux Privilege Escalation - TryHackMe Writeup

## Overview  
The Linux Privilege Escalation room on TryHackMe teaches different techniques to escalate privileges from a normal user to root on a Linux system. The room focuses on discovering misconfigurations, weak permissions, and vulnerable services that can be exploited.

---

## Objectives / Tasks  
- Enumerate system information  
- Identify vulnerable services or misconfigurations  
- Escalate privileges to root  
- Capture and submit the flag

---

## Tools Used  
- LinPEAS (Privilege Escalation Script)  
- Nmap  
- Netcat  
- Sudo  
- SUID binaries

## Walkthrough

### Step 1: Enumerate System Information  
Start by gathering basic system information to understand the environment.  
bash
uname -a

This will provide details about the kernel version and system architecture.


---

Step 2: Check for Sudo Permissions

Check if the user has sudo permissions without a password prompt.

sudo -l

Result:
If there are commands that can be run without a password, such as sudo /bin/bash, you can execute them to escalate to root.


---
Step 3: Check SUID Binaries

Look for SUID binaries which are set to allow execution with the owner’s permissions.

find / -type f -perm -4000 2>/dev/null

Result:
If there are any binaries like nmap, ping, or others, they may be exploited for privilege escalation.


---

Step 4: Check for Writable Directories

Check for writable directories or files that may allow you to inject malicious scripts.

find / -writable -type d 2>/dev/null

Look for directories with world-writable permissions.


---
Step 5: Exploit a Vulnerability

If you find a vulnerable SUID binary or writable directory, you can exploit it to escalate privileges.

Example (SUID nmap binary):

nmap --interactive
!sh

This will start a shell with root privileges if nmap is vulnerable.


---

Step 6: Capture the Flag

Once you have root access, find the flag.

cat /root/root.txt


---
Flag

THM{example-flag-value}


---

Lessons Learned

Privilege escalation depends on identifying misconfigurations and vulnerabilities in the system.

SUID binaries are a common target for privilege escalation.

Always check sudo permissions and misconfigured services.

Be mindful of writable directories, as they can be exploited.



---

References

LinPEAS GitHub

Linux Privilege Escalation Techniques

TryHackMe Linux Privilege Escalation Room

