Understanding Cross-Site Scripting (XSS)
Cross-Site Scripting (XSS) is a security vulnerability where attackers inject malicious JavaScript into a web application. This script then executes within the browser of any user who visits the affected page, allowing the attacker to bypass access controls or steal session data.

Three Main Types of XSS
Persistent (Stored) XSS: The malicious payload is permanently saved on the target server (e.g., in a database, a comment field, or a forum post). It runs for every visitor who views the page.

Reflected XSS: The payload is "reflected" off a web application to the user's browser. It is typically delivered via a link (in a URL parameter) and is not stored on the server.

DOM-Based XSS: The vulnerability exists entirely in client-side code. The payload is executed by modifying the Document Object Model (DOM) environment in the victim's browser.

Practical Example: Reflected XSS in DVWA
Target: DVWA → XSS (Reflected)

Execution Steps
Navigate to the XSS (Reflected) tab.

In the input text box, type the following payload:

HTML

<script>alert("hai")</script>
Technical Breakdown
What it does: Injects a JavaScript alert() function into the application's HTML output.

The Vulnerability: If the application fails to sanitize the input (i.e., it doesn't strip or escape HTML tags), the browser treats the input as executable code.

The Result: A popup box with the text "hai" appears in your browser window.
