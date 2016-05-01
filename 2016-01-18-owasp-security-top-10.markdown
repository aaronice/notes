---
layout:     post
title:      "OWASP Security Top 10"
subtitle:   "A brief summary of OWASP Top 10"
date:       2016-01-18 12:00:00
author:     "aaronice"
keyword:    ["security","OWASP"]
header-img: ""
---

# OWASP TOP 10

OWASP is abbreviation for Open Web Application Security Project.

> The **OWASP Top Ten** represents a broad consensus about what the most critical web application security flaws are.

---

* TOC
{:toc}

---


## 1. SQL Injection

**Reason**

* Targets the back-end data stores via URL, forms, login boxes

**Defense**

* The best defense against SQL injection is use parameterized queries (prepared statements) for SQL queries within the code
* No detailed database error message returned directly
* Validate the input data before constructing SQL



## 2. Session hijacking

**Reason**

* Network packet captured, SessionID being used, hijacker treated as user

**Defense**

* Encryption of the site over HTTPS will help prevent session tokens from being stolen
* Sensitive sites consider not only authentication but also the entire sites: Use SSL, HTTPS
* Shorter idle timeouts
* Help those who forgot to logout
* Harder for hijackers to act



## 3. Cross-site Scripting (XSS)

**Reason**

* User supplied input is properly escaped, or not verify it to be safe via input validation

**Defense**

* Use proper re-encoding before redisplaying user input
* Properly escape all untrusted data based on the HTML context
* Positive or “whitelist” input validation
* Auto-sanitization libraries
* Content Security Policy (CSP)



## 4. Parameter Manipulation (insecure direct object reference)

**Reason**

* Parameter values contained inside a URL being modified get different functionality or data

**Defense**

* Server-side validation
* Central validation scheme
* Independent business logic
* Session variables
* Storing data in session variables, no parameters in the URL to be tampered with



## 5. Insecure Configuration

**Reason**

* Lack of standard hardening process for deployed infrastructure and software
* No central account management mechanism in place on each server
* No standardized and central process for patch management

**Defense**

* Repeatable Hardening process
* New server, repeatable hardening scripts
* Patch Management
* Regular Updates and Audits



## 6. Insecure Storage

**Reason**

* Sensitive data may be disclosed to unauthorized party

**Defense**

* Determine what’s sensitive
* Thread Modeling
* Use known strong algorithms
* Hashing
* Use >=168bits, e.g. SHA-256, instead of MD5, SH0, SH1



## 7. Forcible Browsing

**Reason**

* Access by “guessing” the URL

**Defense**

* Page Level Authorization
* Each page checks to see if the user is authorized to have access
* Programmed Authorization
* Code and programming to determine a user’s authorization, includes coding roles and access policies


## 8. Cross-site request forgery (XSRF)

**Reason**

* Victim must be authenticated
* Hacker must be able to make a XSRF URL, attack is blind

**Defense**

* Decrease session timeouts
* XSRF tokens, adding a secret, not automatically submitted, token to ALL sensitive requests
* Server generates a token on each page load and stores it, when submits the form, it check if the token matches
* Re-authentication
* Asking user to re-authenticate before a sensitive transaction is a good way to verify the user and their intended actions



## 9. Vulnerable Components

**Reason**

* Vulnerable components are common, virtually every app has these issues; development team not enforcing components/libraries up-to-date

**Defense**

* Automation checks periodically to check if libraries out-of-date


## 10. Unchecked Redirects

* URL redirects exploited by hacker

**Defense**

* Don’t use parameters (in URL), manage re-direction in code such as session data
* Server side validation, check redirect URLs, use a whitelist





## Reference

* [OWASP Top 10](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project)
* [OWASP_Top_Ten_Cheat_Sheet](https://www.owasp.org/index.php/OWASP_Top_Ten_Cheat_Sheet)
* [OWASP Node Goat Tutorial: Fixing OWASP Top 10](http://nodegoat.herokuapp.com/tutorial)
* [Node.js Security Checklist](https://blog.risingstack.com/node-js-security-checklist/)
