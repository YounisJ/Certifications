# CAP (Certified AppSec Practitioner)
## Here is outline to for prepation of CAP Exam


<details>
  <summary><b>1. Input Validation Mechanisms:</b></summary>
  Input validation is something that is used to limit the user input for attaining just the required functionality through input testing. Since some of the vulnerabilities like XSS, SQL Injection, SSTI, etc. are possible due to lack of implementation within input validation


a. **Syntactical Validation** (Format Check):
   - What it checks: The structure or format of the data.
   Example in plain terms:
   - If someone enters a date as 2024-15-50, syntactical validation will check if it follows the correct format YYYY-MM-DD (but not whether it's a real date).
b. **Semantic Validation** (Meaning Check):
   - What it checks: The logic or meaning of the data.
     Example in plain terms:
   - If someone enters a date as 2024-02-30, semantic validation will catch that February never has 30 days.

### Key Difference:
| Validation Type | What it Checks          | Example                          |
|----------------|-------------------------|----------------------------------|
| Syntactical    | Format and structure     | "abc@example.com" (email format) |
| Semantic       | Logical correctness      | "birthdate not in the future"    |



- **Blacklisting**:
    - Scanning and Rejecting input that is know to be bad (Given data doesn't contains the bad content)
    - Example: ‘|%| — |;|/\|\\\||\[|@|xp And <SCRIPT>
- **Whitelisting**:
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

<details>
  <summary><b>5. XML External Entity attack</b></summary>
  XML External Entity (XXE) attack is a type of attack that exploits a vulnerability in an XML parser that is used to process XML documents. This vulnerability can be used by attackers to gain access to sensitive data within an XML file, or even to gain access to a network system.
  

**Types:**

- XML Injection: The document contains malicious code which can be used to steal data from the XML document or to gain access to the network system.

- XML Bombing: The document contains malicious code which can be used to cause a denial of service (DoS) attack or to gain access to the network system.

- XXE Injection: The document contains malicious code which can be used to gain access to the network system or to execute arbitrary code on the system.

**Preventions:**
- External source validated and filtered
- Use Latest version of xml parser
- Use input validation
</details>

<details>
  <summary><b>6. Cross-Site Request Forgery</b></summary>
Cross-Site Request Forgery (CSRF) is a type of attack which is carried out when an attacker tricks a user into sending a malicious request to a target website. 

The malicious request can be a GET or POST request, and the attacker can use it to access and modify sensitive user data, or to execute unwanted commands on a vulnerable website

- Example of a CSRF attack is an attacker manipulating a user into sending a GET request to a vulnerable website. The GET request could contain a malicious command, such as “delete all users”, which the attacker can then use to delete all users from the website without the user’s knowledge.

**Preventions:**
- Use anti-CSRF token
- Restrict access
- Use Captcha
- Use Https accross all pages
- Use 2fa
</details>


<details>
  <summary><b>7. Encoding, Encryption, and Hashing</b></summary>
Encoding, encryption, and hashing are three distinct processes used to protect digital information.

**Encoding** is a way of representing data in a different format, typically for the purpose of obfuscation or to compress the data. It does not provide security, but can be used to help make it more difficult for unauthorized persons to access the data.

- URL Encoding
- Base64 Encoding
- ASCII Encoding
- UTF-8 Encoding
- Hexadecimal Encoding

**Encryption** is a process of transforming data using an algorithm and a key in order to make the data unreadable without the key. It is the most commonly used method to protect data in transit and at rest.

- Symmetric Encryption: Symmetric encryption is a type of encryption where the same key is used for both encryption and decryption
- Asymmetric Encryption: Asymmetric encryption is a type of encryption where two different keys are used, one for encryption and one for decryption

**Hashing** is the process of generating a fixed-length output from a string of data using a deterministic algorithm. It is used to verify the integrity of data and to securely store passwords.


- **MD5**: Generates a 128-bit hash value.
- **SHA-1**: Generates a 160-bit hash value.
- **SHA-2**: Generates a 224-bit, 256-bit, 384-bit, or 512-bit hash value.
- **SHA-3**: Generates a 224-bit, 256-bit, 384-bit, or 512-bit hash value.
- **BCrypt**: Generates a variable-length hash value based on a salt and user-supplied password.
  
</details>

<details>
  <summary><b>8. Understanding of OWASP Top 10 Vulnerabilities</b></summary>
Every year Open Web application security project publishes its top 10 list of web vulnaribilities that includes top 10 vulnaribbilities and there impact and how to avoid them

**here are the 2021 OWASP Top 10**:
1. Broken access control: 
2. Cryptographic failure
3. Injection
4. Insecure design
5. Security misconfiguration
6. Vulnerable and outdated components
7. Identification and authentication failures
8. Software and data integrity failures
9. Security logging and monitering failures
10. Server-side request forgery 

**Broken access control**
Broken Access Control happens when access permissions are misconfigured thereby allowing attackers to access, modify or delete data, files and accounts that they should not have access to in the first place.

**CRYPTOGRAPHIC FAILURES**

Cryptographic failures occur when sensitive data is insufficiently protected and therefore leaked or exposed to unauthorized audiences. Such failures are most common if data is transmitted or stored in clear text or using known-to-be-weak cryptographic algorithms such as MD5 or SHA-1.

**INJECTION**

An attacker can execute unintended commands or gain access to sensitive data by injecting malicious data as part of a command or query. This usually happens when a website fails to filter, validate or sanitize users’ inputs or implement parameterization.

**INSECURE DESIGN**

This newest OWASP Top 10 revision talks about risks related to design and architectural flaws, with recommendations for implementing threat modelling, secure design patterns, and reference architectures – from the very beginning of the design process.

**SECURITY MISCONFIGURATION**

This category covers a brand range of potential vulnerabilities including insecure default configurations, open ports, incomplete configurations, and misconfigured HTTP headers, using insecure default usernames and passwords, etc.

**VULNERABLE AND OUTDATED COMPONENTS**

This refers to known issues where vulnerabilities exist because developers either do not know the versions of components used including those of nested dependencies, or are not aware that the software used is already unsupported or out of date.

e.g. Log4j2 Vulnerability

**IDENTIFICATION AND AUTHENTICATION FAILURES**

Previously known as “Broken Authentication”, this category covers weaknesses in authentication and session management in web applications. The resulting vulnerabilities allow attackers to gain unauthorized access to accounts and/or data.

**SOFTWARE AND DATA INTEGRITY FAILURES**

For software, data integrity failures are becoming increasingly relevant as sensitive information is increasingly stored in databases, where it is at risk of tampering security.

**SECURITY LOGGING AND MONITORING FAILURES**

Previously categorized as “Insufficient Logging and Monitoring”, Security Logging and Monitoring Failures moved one place up from #10 this year. Logging and monitoring are essential components in ensuring that any suspicious activity can be detected close to real-time, or diagnosed after the fact.

**SERVER-SIDE REQUEST FORGERY (SSRF)**

Server-side request forgery (also termed as SSRF) is a web security flaw that allows an attacker to force a server-side application to send HTTP requests to any domain the attacker chooses

</details>

<details>
  <summary><b>9. Security Best Practices and Hardening Mechanisms.</b></summary>
    - Same Origin Policy: 
    - Security Headers: 

</details>
10. TLS security
    - TLS Certificate Misconfiguration
    - Symmetric and Asymmetric Ciphers
11. Server-Side Request Forgery
12. Authorization and Session Management related flaws
    - Insecure Direct Object Reference (IDOR)
    - Privilege Escalation
    - Parameter Manipulation attacks
    - Securing Cookies
13. Insecure File Uploads
14. Code Injection Vulnerabilities
15. Business Logic Flaws
16. Directory Traversal Vulnerabilities
17. Security Misconfigurations.
18. Information Disclosure.
19. Vulnerable and Outdated Components.
20. Common Supply Chain Attacks and Prevention Methods.
