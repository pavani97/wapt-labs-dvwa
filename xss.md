# Understanding Cross-Site Scripting (XSS)

Cross-Site Scripting (XSS) is a security vulnerability where attackers inject malicious JavaScript into a web application. This script then executes within the browser of any user who visits the affected page, allowing the attacker to bypass access controls or steal session data.

---

## Three Main Types of XSS

### 1. Persistent (Stored) XSS
The malicious payload is permanently saved on the target server, such as in:
- A database
- A comment field
- A forum post  

The payload runs for **every user** who views the affected page.

### 2. Reflected XSS
The payload is *reflected* off the web application to the user’s browser.  
Key characteristics:
- Delivered via a URL parameter or form input
- Not stored on the server
- Requires user interaction (e.g., clicking a malicious link)

### 3. DOM-Based XSS
The vulnerability exists entirely in **client-side JavaScript**.  
The payload is executed by modifying the **Document Object Model (DOM)** in the victim’s browser, without interacting with the server.

---

## Practical Example: Reflected XSS in DVWA

**Target:**  
DVWA → `XSS (Reflected)`

---

## Execution Steps

1. Navigate to the **XSS (Reflected)** tab in DVWA.
2. In the input text box, enter the following payload:


## 1. Low

Enter your name into the input field and observe the application’s behavior.  
The input is directly reflected in both the URL and the page output beside “Hello”.

View it’s source by selecting “View Source” in the bottom-right corner.  
Observe that the application simply echoes back the user-supplied input without any sanitization or encoding.

Inject the following payload into the input field: <script>alert(1)</script> 




## Result

A JavaScript alert is successfully executed, confirming the application is vulnerable to reflected XSS at this level.

---

## 2. Medium

View the source code.  
Observe that this time our previous payload won’t work because the application includes a filter that removes `<script>` tags.

Since JavaScript is not case sensitive, we can bypass this filter by mixing uppercase and lowercase letters in the tag: <script>alert(1)</Script>




## Result

The alert executes successfully, demonstrating that the blacklist-based filter is insufficient.

---

## 3. High

View the source code.  
At this level, the application applies a regex-based replacement that strips variations of `<script>` tags, including obfuscated ones (e.g., `<ScRiPt>`, `<sCrXXXipt>`, `<s c r i p t>`).

Since the filter specifically targets `<script>` tags, we must craft a payload that does not rely on them.

Use an alternate injection vector, such as an image element with an error handler: <img src=x onerror=alert(1)>



The invalid image source (`x`) triggers an error, which in turn executes the `onerror` JavaScript handler.

## Result

The alert is executed successfully, confirming that the application remains vulnerable despite the regex filter.

