# 🛡️ Nmap Scan – OWASP Juice Shop Penetration Testing Lab

This repository contains the complete Nmap reconnaissance performed against an intentionally vulnerable web application (**OWASP Juice Shop**) hosted on an Ubuntu virtual machine.  
The scanning was conducted from a Kali Linux attacker machine within an isolated host-only VMware Fusion network.

---

## 🧪 Lab Environment

### **Attacker Machine (Kali Linux)**
- IP Address: `192.168.38.129`
- Tools Used: Nmap, curl, ping

### **Victim Machine (Ubuntu)**
- IP Address: `192.168.38.128`
- Hosts OWASP Juice Shop (Docker)
- Service under test: http://192.168.38.128:3000
- ---

## 📌 Objective

Perform a structured Nmap reconnaissance to:

- Identify open ports  
- Enumerate running services  
- Detect service versions  
- Perform an all-port sweep  
- Conduct aggressive OS + script scanning  
- Check for vulnerabilities using Nmap Scripting Engine (NSE)

This phase establishes the attack surface for further exploitation steps such as Gobuster, SQLmap, Burp Suite testing, XSS, and authentication attacks.

---

## 📁 Files Included

### ✔ **Nmap Scan Outputs**
- `nmap_basic.txt`
- `nmap_versions.txt`
- `nmap_full.txt`
- `nmap_aggressive.txt`
- `nmap_vuln.txt`

### ✔ **Documentation**
- `Nmap_Scan_Document.docx`  

---

## 🔍 Scan Commands Used

### **1. Basic Port Scan**
`nmap -sS -Pn 192.168.38.128 -oN nmap_basic.txt`
### **2. Version Detection Scan**
`nmap -sV -sS -Pn 192.168.38.128 -oN nmap_versions.txt`
### **3. Full TCP Port Sweep**
`nmap -p- -sS -Pn 192.168.38.128 -oN nmap_full.txt`
### **4. Aggressive Scan (OS + Services + Scripts)**
`nmap -A -sS -Pn 192.168.38.128 -oN nmap_aggressive.txt`
### **5. Vulnerability Detection (NSE Script Scan)**
`nmap –script vuln -Pn 192.168.38.128 -oN nmap_vuln.txt` 

---

## 📝 Summary of Findings

Nmap enumeration of the target (192.168.38.128) revealed two open ports: 22/tcp (SSH) and 3000/tcp (HTTP – OWASP Juice Shop). SSH is running OpenSSH 9.6p1 on Ubuntu, and port 3000 serves the intentionally vulnerable Juice Shop application. Aggressive scans confirm the system is a Linux VM (VMware) with a kernel in the 4.x–5.x range. No critical system-level vulnerabilities were detected through automated NSE scripts, but Juice Shop exposes multiple application-level OWASP Top 10 vulnerabilities. The machine is reachable and properly configured for penetration testing activities.


## 🚀 Next Steps (Future Work)

This Nmap scan serves as the foundation for further penetration testing activities:

- Directory enumeration (Gobuster, ffuf)  
- Manual inspection using Burp Suite  
- SQL Injection (SQLmap + manual payloads)  
- Cross-Site Scripting (XSS) tests  
- Authentication brute force (Hydra)  
- JWT analysis  
- Final pentest report  

---

## 📚 Purpose

This repository demonstrates:
- Real-world reconnaissance methodology  
- Ability to document and interpret scan results  
- Experience setting up isolated cybersecurity labs  
- Offensive security skills for entry-level cybersecurity roles  

---

## 🏁 Author

**Sai Chetan Panathukula**  
Cybersecurity & Software Engineer  
VMware Fusion Lab • Kali Linux • OWASP Juice Shop  

---
