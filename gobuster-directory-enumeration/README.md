# 🔍 Gobuster Directory Enumeration

This section documents the directory brute-force enumeration conducted against the OWASP Juice Shop application hosted at **http://192.168.38.128:3000**. The goal of this lab is to identify hidden routes, API endpoints, and application components that may reveal attack vectors for further penetration testing.

---

## 🧪 Command Executed

Because OWASP Juice Shop returns **200 OK for all URLs**, Gobuster requires length/status filtering.  
The final working command:

```bash
gobuster dir \
-u http://192.168.38.128:3000 \
-w /usr/share/wordlists/dirb/common.txt \
--exclude-length 75002 \
-o gobuster_results.txt
