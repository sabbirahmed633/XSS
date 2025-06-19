Exploiting XSS Vulnerabilities on a Live Web Server
A hands-on penetration testing project that explores the exploitation of DOM-based, Reflected, and Stored XSS (Cross-Site Scripting) vulnerabilities on a live web server. This lab-based demonstration is part of the Internet and Web Application Security curriculum and showcases how attackers can leverage XSS flaws to inject and execute malicious scripts.

🔬 Conducted by: Sabbir Ahmed 

🚀 Objective
To simulate real-world exploitation of various types of XSS vulnerabilities and understand:

How user inputs are mishandled in client-side and server-side code

The potential impact of successful XSS attacks

Techniques to deliver, disguise, and escalate XSS payloads

🔍 XSS Attack Types Covered
1. DOM-Based XSS
Vector: JavaScript reads the payload from window.location and injects it into the DOM.

Tools Used: Network Monitor, Developer Tools

Evidence: Screenshots of GET requests, query string in DOM, and JavaScript alerts.

2. Reflected XSS
Vector: User input reflected immediately in the server response (e.g., search boxes).

Payload Example:

html
Copy
Edit
<script>alert('XSS')</script>
Outcome: Script executes in the context of the current page when the malicious URL is visited.

3. Stored XSS
Vector: Malicious script is permanently stored on the target server (e.g., in a comment field).

Persistence: The payload executes every time the stored input is viewed by users.

Impact: Greater risk due to reach and repeatability.

🧪 Applied Learning Tasks
Crafting Payload Links: Created malicious URLs to trigger alerts via DOM and query string manipulation.

Network Monitoring: Captured live HTTP requests and DOM reflections.

Disguising Attacks: Developed disguised XSS payloads using obfuscation and misleading link labels.

Session Hijacking Simulation: Demonstrated potential for password theft via XSS.

🧠 Key Takeaways
XSS can be delivered via multiple channels (URL, form input, persistent storage).

DOM-based vulnerabilities are often overlooked in client-side JavaScript.

Even simple payloads like alert() can reveal deep flaws in input handling.

Proper input validation, output encoding, and content security policies are essential to mitigate XSS.

📁 Project Structure
bash
Copy
Edit
📂 xss-lab/
├── screenshots/               # Visual proof of each attack step
├── payloads/                  # XSS scripts used in each part
├── writeup/                   # Detailed lab notes and analysis
└── README.md                  # Project overview (this file)
🛡️ Countermeasures and Best Practices
Use Contextual Output Encoding (e.g., HTML, JavaScript, URL)

Sanitize Input on Both Client and Server Side

Employ CSP (Content Security Policy)

Avoid Dynamic JavaScript Execution with eval() or innerHTML

Validate URLs and Strip Untrusted Parameters

📚 References
OWASP XSS Guide
Mozilla Developer Docs – XSS
