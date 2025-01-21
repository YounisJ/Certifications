# CAP (Certified AppSec Practitioner)
## Here is outline to for prepation of CAP Exam


<details>
  <summary><b>1. Input Validation Mechanisms</b></summary>
  Input validation is something that is used to limit the user input for attaining just the required functionality through input testing. Since some of the vulnerabilities like XSS, SQL Injection, SSTI, etc. are possible due to lack of implementation within input validation


a. **Syntactical Validation** (Format Check)
   - What it checks: The structure or format of the data.
   Example in plain terms:
   - If someone enters a date as 2024-15-50, syntactical validation will check if it follows the correct format YYYY-MM-DD (but not whether it's a real date).
b. **Semantic Validation** (Meaning Check)
   - What it checks: The logic or meaning of the data.
     Example in plain terms:
   - If someone enters a date as 2024-02-30, semantic validation will catch that February never has 30 days.

### Key Difference:
| Validation Type | What it Checks          | Example                          |
|----------------|-------------------------|----------------------------------|
| Syntactical    | Format and structure     | "abc@example.com" (email format) |
| Semantic       | Logical correctness      | "birthdate not in the future"    |



- **Blacklisting**
    - Scanning and Rejecting input that is know to be bad (Given data doesn't contains the bad content)
    - Example: ‘|%| — |;|/\|\\\||\[|@|xp And <SCRIPT>
- **Whitelisting**
    - Scanning and accepting input that is know to be good ()
    - whitelist validation is the more powerful of the two input validation approaches
    - Example: Length, size, format and type etc

</details>

##

<details>
  <summary><b>2. Auth Related Vulnerabilities</b></summary>
  Authentication-related vulnerabilities are an important security concern for organizations today. A malicious actor can gain access to a system by exploiting a vulnerability in authentication systems, such as weak passwords or default credentials.

  Types:
  
  - Password attacks
  - Insecure authentication (Weak encryption)
  - Social engineering
  - Stolen credentials
  - Unauthorized access
  - Weak Default settings

  Mitigations:
  - Strong pass
  - Secure Auth Protocols
  - Educate users
  - multi factor auth

</details>

##

<details>
  <summary><b>3. XSS (Cross-Site Scripting)</b></summary>
  injecting malicious code into the web page using HTML or JavaScript. This code can then be used to gain access to user data, alter the appearance of the page, or even send malicious commands to the server. The malicious code is often hidden in a URL, hidden form field, or in the HTML source of the web page.

**Types:**
  - **Stored XSS** : In a stored XSS attack, the attacker injects malicious code into a website's database, where it is stored and executed whenever someone accesses a page that retrieves data from the database.
  - **Reflected XSS** : In a reflected XSS attack, the attacker crafts a URL that includes the malicious code, and tricks a victim into clicking on it. When the victim's browser requests the URL, the server returns a page containing the injected code, which is then executed by the victim's browser.

**Preventions:**
- Input Validation
- CSP (Content Security Policy): CSP is a security feature that allows a website to specify which sources of content are allowed to be loaded by the browser.
- Escaping user input
- Encoding user input
- Disable HTML in user input
</details>


<details>
<summary><b>4. SQL Injection</b></summary>
  SQL injection is a type of attack that takes advantage of the structure of SQL to inject malicious code into a web application. 
  **Catagories:**
  
- **Classic SQLI**: Classic SQL injection involves manipulating the syntax of an SQL query to gain access to sensitive data. This typically involves entering malicious code into an input field or URL.
- **Blind SQLI**: Blind SQL injection is a type of attack that is used when the attacker does not have direct access to the database. In this case, the attacker will use techniques such as Boolean-based and time-based SQL injection to gain access to the database.
- **Second-order SQLI**: Second-order SQL injection is a type of attack that occurs when an attacker is able to inject malicious code into a web application and it is then executed when the application is used by another user.

  **Preventions:**
  - Use parameterized queries
  - Use prepared statements
  - Input validation
  - Implement Whitelisting
  - Encrypt Sensitive data
  - Use least privilige escalation
  - Monitor system logs
  - Use WAF's
</details>

5. XML External Entity attack
6. Cross-Site Request Forgery
7. Encoding, Encryption, and Hashing
8. Authentication related Vulnerabilities
    - Brute force Attacks
    - Password Storage and Password Policy
9. Understanding of OWASP Top 10 Vulnerabilities
10. Security Best Practices and Hardening Mechanisms.
    - Same Origin Policy
    - Security Headers
11. TLS security
    - TLS Certificate Misconfiguration
    - Symmetric and Asymmetric Ciphers
12. Server-Side Request Forgery
13. Authorization and Session Management related flaws
    - Insecure Direct Object Reference (IDOR)
    - Privilege Escalation
    - Parameter Manipulation attacks
    - Securing Cookies
14. Insecure File Uploads
15. Code Injection Vulnerabilities
16. Business Logic Flaws
17. Directory Traversal Vulnerabilities
18. Security Misconfigurations.
19. Information Disclosure.
20. Vulnerable and Outdated Components.
21. Common Supply Chain Attacks and Prevention Methods.
