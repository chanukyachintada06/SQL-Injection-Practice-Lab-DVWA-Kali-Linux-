# 🛡️ SQL Injection Practice Lab (DVWA – Kali Linux)

This repository documents the complete setup and execution of a **local SQL Injection practice lab** using **Damn Vulnerable Web Application (DVWA)** on **Kali Linux**.  
This project is created **strictly for educational and ethical cybersecurity learning**.

---

## 📌 Project Objectives
- Understand how SQL Injection vulnerabilities occur
- Practice real-world SQLi attacks in a controlled environment
- Learn offensive (exploitation) and defensive (mitigation) techniques
- Gain hands-on experience aligned with **OWASP Top 10**

---

## 🧰 Lab Environment

| Component | Details |
|---------|--------|
| OS | Kali Linux |
| Web Server | Apache2 |
| Database | MariaDB (MySQL compatible) |
| Backend | PHP |
| Vulnerable App | DVWA |
| Tools | Burp Suite, sqlmap |

---

## ⚠️ Ethical Disclaimer
This project is intended **only for self-learning and educational purposes**.  
All testing was performed on a **locally hosted lab environment** owned by the author.

❌ Do NOT test these techniques on real or third-party websites without permission.

---

## 🔧 Step-by-Step Setup Guide

### 🔧 Step 1: Update System

sudo apt update

## 🔧 Step 2: Install Required Services and Packages
sudo apt install apache2 mariadb-server php php-mysqli git -y

## 🔧 Step 3: Start and Verify Services
**Start:**
sudo systemctl start apache2
sudo systemctl start mariadb

**Verify Services:**
Verify Apache by opening:
http://localhost


## 🔧 Step 4: Create Database and User for DVWA

sudo mariadb

**You can view sample sql query in the code file**

## 🔧 Step 5: Download DVWA Application
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git
sudo chown -R www-data:www-data DVWA
sudo chmod -R 755 DVWA

## 🔧 Step 6: Configure DVWA Database Settings
cd DVWA/config
sudo cp config.inc.php.dist config.inc.php
sudo nano config.inc.php

**Vulnerable PHP Login Page:**

$_DVWA['db_user'] = 'dvwa';
$_DVWA['db_password'] = 'dvwa';
$_DVWA['db_database'] = 'dvwa';

## 🔧 Step 7: Initialize DVWA
**Open in browser:**
http://localhost/DVWA/setup.php

**Login Credentials:**
Username: admin
Password: password


## 🧪 SQL Injection Testing

Set DVWA Security Level:
Low
' OR '1'='1
1 UNION SELECT database(), user()
1' AND SLEEP(5)-- -




## 🛠️ Tools Used
- Damn Vulnerable Web Application (DVWA)
- Burp Suite
- sqlmap
- Apache2
- MariaDB



## 🔐 Mitigation Techniques
- Use prepared statements
- Input validation and sanitization
- Principle of least privilege
- Disable detailed SQL error messages


## 📚 References
https://github.com/digininja/DVWA
https://github.com/sqlmapproject/sqlmap
https://owasp.org/www-community/attacks/SQL_Injection
https://owasp.org/www-project-top-ten/
https://portswigger.net/web-security/sql-injection

## 👤 Author
Chanukya Venkata Sai  
Cybersecurity & CSE Student

---

⭐ **If you found this repository helpful, please consider giving it a star on GitHub.**  
Your support helps others discover this project and motivates further improvements.

---


