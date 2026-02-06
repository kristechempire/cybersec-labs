# CyberSec Labs

My beginner journey in cybersecurity – safe lab projects, scans, and notes.

## Project 2: Nmap Service Enumeration on Metasploitable 2

Date: February 2025 (or actual date)  
Goal: Set up isolated lab, discover host, scan open ports & service versions on vulnerable target.

### Lab Setup
- Kali Linux (attacker) + Metasploitable 2 (target) in VirtualBox  
- Network: Host-Only Adapter (private, no internet leak)  
- Target IP: 192.168.56.102 (your Metasploitable)

### Commands Used
1. Host discovery (ping scan whole subnet):
   nmap -v -sn 192.168.56.0/24

 → Found 2 live hosts (Kali + Metasploitable)

2. Detailed service/version scan:
   nmap -v -sV 192.168.56.102

     → Detected 19 open services, including many vulnerable ones (vsftpd 2.3.4 backdoor, old Apache, Samba, etc.)

### Key Findings
- vsftpd 2.3.4 (port 21): Famous backdoor exploit  
- OpenSSH 4.7p1 (port 22): Old version  
- Apache 2.2.8 (port 80): Web server vulnerabilities  
- Samba 3.X (ports 139/445): Potential for EternalBlue-style exploits  
- UnrealIRCd (port 6667): Backdoor  
- Many others (telnet, NFS, VNC, etc.) intentionally insecure for learning

### Screenshot of Nmap -sV Output
![Nmap Service Scan on Metasploitable 2](nmap%20metasploitable.jpg)

### What I Learned
- Nmap host discovery first finds live targets.  
- -sV reveals software versions → check for known CVEs/exploits.  
- Metasploitable 2 is perfect for safe practice.  
- First step in ethical hacking: reconnaissance/enumeration.

More projects coming soon!
