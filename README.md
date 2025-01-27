# penetration-testing-labs
I've created a GitHub-friendly README for your Penetration Testing Labs project. It includes setup details, penetration testing steps, vulnerability assessment, mitigation recommendations, and tools used.
# Penetration Testing Labs

## 📌 Project Overview
Conducted **simulated penetration tests** using **Kali Linux, Metasploit, and OWASP ZAP** to identify and mitigate **15 security vulnerabilities** across various systems. This process enhanced the overall **system security posture** by uncovering potential threats and implementing mitigation measures.

## 🚀 Objectives
- Perform **penetration testing** to uncover security weaknesses.
- Exploit vulnerabilities using **Metasploit Framework**.
- Identify **web application vulnerabilities** with **OWASP ZAP**.
- Provide **mitigation recommendations** to improve security.

---

## 🛠️ Setup & Configuration

### 1️⃣ Environment Setup
- Installed **Kali Linux** on a VM or bare-metal system.
- Configured **Metasploitable2** & **DVWA (Damn Vulnerable Web App)** for testing.
- Installed **OWASP ZAP** for web application vulnerability analysis.

### 2️⃣ Target System Details
| System | Target Type | Vulnerabilities Tested |
|--------|------------|----------------------|
| Metasploitable2 | Linux VM | SSH, SMB, FTP, Apache, MySQL |
| DVWA | Web App | SQL Injection, XSS, CSRF, LFI/RFI |
| Windows 10 | Workstation | Privilege Escalation, SMB, RDP |

---

## 🔍 Penetration Testing Process

### 🔹 1. Network Scanning with Nmap
Identified open ports and services:
```sh
nmap -sV -p- -A 192.168.1.10
```

### 🔹 2. Exploiting Vulnerabilities with Metasploit
Example: Exploiting an outdated SMBv1 service
```sh
msfconsole
use exploit/windows/smb/ms17_010_eternalblue
set RHOST 192.168.1.10
exploit
```

### 🔹 3. Web Application Security Testing with OWASP ZAP
- **Automated Scan** for vulnerabilities:
  ```sh
  zap-cli quick-scan -u http://192.168.1.20/dvwa/
  ```
- **Detected Issues:**
  - SQL Injection
  - Cross-Site Scripting (XSS)
  - Insecure Authentication

### 🔹 4. Post-Exploitation & Mitigation
- Obtained **reverse shell access**.
- Escalated privileges on **Windows 10**.
- Implemented security fixes to mitigate findings.

---

## 📊 Findings & Risk Assessment
| Vulnerability | Impact | Mitigation Steps |
|--------------|--------|------------------|
| SMBv1 Exploit (EternalBlue) | Critical | Disable SMBv1, apply patches |
| SQL Injection (DVWA) | High | Use prepared statements, input validation |
| XSS (Cross-Site Scripting) | Medium | Implement CSP headers, sanitize inputs |
| Weak SSH Configuration | Medium | Enforce key-based authentication |

---

## 🔧 Recommendations & Security Hardening
✅ **Apply system updates and security patches.**
✅ **Disable unnecessary services and ports.**
✅ **Harden SSH, SMB, and FTP configurations.**
✅ **Regularly conduct security audits and penetration testing.**

---

## 🔗 Technologies Used
- **Kali Linux**
- **Metasploit Framework**
- **OWASP ZAP**
- **Nmap & Nikto**
- **Burp Suite**

---

## 📢 Contribution & Feedback
Feel free to **fork this repository**, contribute via **pull requests**, or suggest improvements via **GitHub Issues**! 🚀

---

### 🔗 References
- [Metasploit Documentation](https://docs.metasploit.com/)
- [OWASP ZAP User Guide](https://www.zaproxy.org/docs/)
- [Penetration Testing Methodologies](https://www.offensive-security.com/metasploit-unleashed/)
