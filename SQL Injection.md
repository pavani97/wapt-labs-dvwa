## 🎯 Objective

To simulate a realistic **SQL Injection attack** on a controlled test environment, identify user credentials from the backend database, and understand how improper input validation can compromise a web application’s integrity.

---

## 🧪 Target Environment

- **Platform:** Damn Vulnerable Web Application (DVWA)
- **Vulnerability Type:** SQL Injection (Classic)
- **Environment:** Local lab (intentionally vulnerable application)

---

## 🛠️ Tools Used

- Web Browser
- DVWA Web Interface
- Nmap

---

## 🔍 Method of Discovering the Vulnerability

### Step 1: Reconnaissance

Initial reconnaissance was performed to identify the target system and available services.

```bash
nmap -sn <target_ip>
nmap -sV <target_ip>

### Step 2: Exploiting the Vulnerability

#### Accessing the Web Application

The DVWA application was accessed through a web browser using the following URL:

```text
http://192.168.168.93.130/dvwa/


