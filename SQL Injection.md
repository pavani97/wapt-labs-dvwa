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

   nmap -sn <target_ip>
   nmap -sV <target_ip> 

### Step 2: Exploiting the Vulnerability

#### Accessing the Web Application

The DVWA application was accessed through a web browser using the following URL:
![DVWA Login Page](screenshots/Screenshot (146).png)


   http://192.168.168.93.130/ (replace with your dvwa url)

Using default credentials that are publicly documented for DVWA:

- **Username:** `admin`
- **Password:** `password`

After successful authentication, the SQL Injection vulnerability page was accessed:
http://192.168.93.130/dvwa/vulnerabilities/sqli/

---

### Exploiting SQL Injection

Knowing that the application is vulnerable to SQL Injection, a malicious payload was entered into the input field.

#### 🔍 Payload Used
1' OR '1'='1

---
![DVWA Login Page](screenshots/Screenshot (145).png)
### 🧠 SQL Logic Explanation

#### Normal Query Behavior
When a legitimate input is provided, the backend SQL query executes as follows:

SELECT * FROM users WHERE id = '1';
This query returns a single user record matching the given ID.

Modified Query After Injection

The injected payload alters the logic of the query:
SELECT * FROM users WHERE id = '1' OR '1'='1';
Since the condition '1'='1' always evaluates to TRUE, the database returns all user records instead of a single entry.
### ✅ Impact

Authentication and input validation were bypassed

Multiple user records were exposed

The attacker gained visibility into backend user data

This demonstrates how improper input handling can lead to complete data disclosure.

### 🕵️‍♂️ Step 3: Data Enumeration

Once the injection was successful, it became possible to enumerate sensitive information, including:

Usernames

User IDs

### ⚠️ Important Note:
Such actions would be illegal and unethical in a real-world production environment. However, DVWA provides a safe and authorized testing platform designed specifically for understanding and practicing exploitation techniques responsibly.

### 🛡️ Security Recommendations

To mitigate SQL Injection vulnerabilities, the following countermeasures are strongly recommended:

Use parameterized queries or prepared statements

Enforce strict input validation and sanitization

Implement stored procedures with proper parameter binding

Deploy a Web Application Firewall (WAF)

Apply the principle of least privilege to database accounts

### 🧠 Reflection

This exercise highlights how even a basic SQL Injection attack can have severe consequences if applications are not properly secured. Despite being one of the oldest known web vulnerabilities, SQL Injection continues to pose a significant threat, especially in legacy or poorly maintained systems.

“Security begins with validation. Every input is a potential attack surface if left unchecked.”

Working with DVWA in an isolated lab environment strengthened my understanding of injection attacks and reinforced the importance of secure coding practices in real-world applications.

### 📌 Disclaimer

This demonstration was conducted solely for educational purposes within a legally authorized testing environment. Unauthorized testing on live systems is strictly prohibited.







