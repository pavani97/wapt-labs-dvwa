# 🔐 Web Application Penetration Testing (WAPT) – DVWA Labs

This repository contains my **hands-on Web Application Penetration Testing (WAPT)** practice performed on **Damn Vulnerable Web Application (DVWA)**.  
The project focuses on identifying, exploiting, and documenting **OWASP Top 10 vulnerabilities** using manual testing techniques and industry-standard tools.

This work is part of my **WAPT certification preparation** and practical cybersecurity portfolio.

---

## 🎯 Scope of Testing

- **Target Application:** Damn Vulnerable Web Application (DVWA)
- **Testing Type:** Manual Web Application Penetration Testing
- **Methodology:**
  - OWASP Top 10
  - OWASP Web Security Testing Guide
- **Environment:**
  - Kali Linux
  - Local lab setup

---

## 🛠️ Tools & Technologies Used

- Burp Suite
- OWASP ZAP
- Kali Linux
- Browser Developer Tools
- Manual payload crafting

---

## 🐞 Vulnerabilities Covered

### 1️⃣ SQL Injection
- Identified injectable input parameters
- Executed SQL payloads to manipulate backend queries
- Demonstrated impact on data confidentiality and integrity

📄 File: `SQL Injection.md`

---

### 2️⃣ Cross-Site Scripting (XSS)
- Tested reflected and stored XSS vulnerabilities
- Injected malicious JavaScript payloads
- Analyzed impact such as session hijacking and user impersonation

📄 File: `XSS.md`

---

### 3️⃣ Insecure Direct Object Reference (IDOR)
- Manipulated object references and URL parameters
- Accessed unauthorized resources
- Highlighted broken access control issues

📄 File: `IDOR.md`

---

### 4️⃣ Cross-Site Request Forgery (CSRF)
- Crafted malicious requests to perform unauthorized actions
- Tested absence of CSRF tokens and validation mechanisms
- Assessed impact on authenticated users

📄 File: `CSRF.md`

---

## 📸 Evidence & Proof of Concept

Each vulnerability includes:
- Step-by-step attack execution
- Proof of Concept (PoC)
- Screenshots of exploitation

All screenshots are stored in the `screenshots/` directory.

---

## 🛡️ Remediation & Recommendations

- Root cause analysis for each vulnerability
- Secure coding recommendations
- OWASP-aligned remediation steps

📄 Consolidated remediation guidance: `remediation.md`

---

## 📌 Disclaimer

This project is created **strictly for educational and learning purposes**.  
All testing was performed in a **controlled lab environment** on intentionally vulnerable applications.  
No real-world systems were harmed.

---

## 🚀 Key Takeaways

This project demonstrates my ability to:
- Perform structured web application security testing
- Identify and exploit common web vulnerabilities
- Document findings in a professional penetration testing format
- Communicate security risks and remediation clearly

---

