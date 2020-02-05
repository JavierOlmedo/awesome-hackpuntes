---
description: A checklist of OWASP Testing guide v4
---

# OWASP: Testing guide checklist

{% file src="../.gitbook/assets/owasp-checklist-en.xlsx" caption="OWASP Checklist EN" %}

♻️ **Update to february 4, 2020**

### \[INFO\] INFORMATION GATHERING

* [ ] INFO-001 Conduct Search Engine Discovery and Reconnaissance Information Leakage
* [ ] INFO-002 Fingerprint Web Server
* [ ] INFO-003 Review Webserver Metafiles Information Leakage
* [ ] INFO-004 Enumerate Applications on Webserver
* [ ] INFO-005 Review Webpage Comments and Metadata Information Leakage
* [ ] INFO-006 Identify application entry points
* [ ] INFO-007 Map execution paths through application
* [ ] INFO-008 Fingerprint Web Application Framework
* [ ] INFO-009 Fingerprint Web Application
* [ ] INFO-010 Map Application Architecture

### \[CONFIG\] CONFIGURATION AND DEPLOY MANAGEMENT

* [ ] CONFIG-001 Network/Infrastructure Configuration
* [ ] CONFIG-002 Application Platform Configuration
* [ ] CONFIG-003 File Extensions Handling for Sensitive Information
* [ ] CONFIG-004 Backup and Unreferenced Files for Sensitive Information
* [ ] CONFIG-005 Enumerate Infrastructure and Application Admin Interfaces
* [ ] CONFIG-006 HTTP Methods
* [ ] CONFIG-007 HTTP Strict Transport Security
* [ ] CONFIG-008 RIA cross domain policy
* [ ] CONFIG-009 File Permission
* [ ] CONFIG-010 Subdomain Takeover

### \[IDENT\] IDENTITY MANAGEMENT

* [ ] IDENT-001 Role Definitions
* [ ] IDENT-002 User Registration Process
* [ ] IDENT-003 Account Provisioning Process
* [ ] IDENT-004 Account Enumeration and Guessable User Account
* [ ] IDENT-005 Weak or unenforced username policy

### \[AUTHN\] AUTHENTICATION

* [ ] AUTHN-001 Credentials Transported over an Encrypted Channel
* [ ] AUTHN-002 Default credentials
* [ ] AUTHN-003 Weak lock out mechanism
* [ ] AUTHN-004 Bypassing authentication schema
* [ ] AUTHN-005 Remember password functionality
* [ ] AUTHN-006 Browser cache weakness
* [ ] AUTHN-007 Weak password policy
* [ ] AUTHN-008 Weak security question/answer
* [ ] AUTHN-009 Weak password change or reset functionalities
* [ ] AUTHN-010 Weaker authentication in alternative channel

### \[AUTHZ\] AUTHORIZATION

* [ ] AUTHZ-001 Directory traversal/file include
* [ ] AUTHZ-002 Bypassing authorization schema
* [ ] AUTHZ-003 Privilege Escalation
* [ ] AUTHZ-004 Insecure Direct Object References

### \[SESS\] SESSION MANAGEMENT

* [ ] SESS-001 Bypassing Session Management Schema
* [ ] SESS-002 Cookies attributes
* [ ] SESS-003 Session Fixation
* [ ] SESS-004 Exposed Session Variables
* [ ] SESS-005 Cross Site Request Forgery
* [ ] SESS-006 Logout functionality
* [ ] SESS-007 Session Timeout
* [ ] SESS-008 Session puzzling

### \[INPVAL\] DATA VALIDATION

* [ ] INPVAL-001 Reflected Cross Site Scripting
* [ ] INPVAL-002 Stored Cross Site Scripting
* [ ] INPVAL-003 HTTP Verb Tampering
* [ ] INPVAL-004 HTTP Parameter pollution
* [ ] INPVAL-005 SQL Injection
* [ ] INPVAL-006 LDAP Injection
* [ ] INPVAL-007 ORM Injection
* [ ] INPVAL-008 XML Injection
* [ ] INPVAL-009 SSI Injection
* [ ] INPVAL-010 XPath Injection
* [ ] INPVAL-011 IMAP/SMTP Injection
* [ ] INPVAL-012 Code Injection
* [ ] INPVAL-013 Command Injection
* [ ] INPVAL-014 Buffer overflow
* [ ] INPVAL-015 Incubated vulnerabilities
* [ ] INPVAL-016 HTTP Splitting/Smuggling
* [ ] INPVAL-017 HTTP Incoming Requests
* [ ] INPVAL-018 Host Header Injection
* [ ] INPVAL-019 Server Side Template Injection

### \[ERR\] ERROR HANDLING

* [ ] ERR-001 Analysis of Error Codes
* [ ] ERR-002 Analysis of Stack Traces

### \[CRYPST\] CRYPTOGRAPHY

* [ ] CRYPST-001 Weak SSL/TSL Ciphers, Insufficient Transport Layer Protection
* [ ] CRYPST-002 Padding Oracle
* [ ] CRYPST-003 Sensitive information sent via unencrypted channels
* [ ] CRYPST-004 Weak Encryption

### \[BUSLOGIC\] BUSINESS LOGIC

* [ ] BUSLOGIC-001 Business Logic Data Validation
* [ ] BUSLOGIC-002 Ability to Forge Requests
* [ ] BUSLOGIC-003 Integrity Checks
* [ ] BUSLOGIC-004 Process Timing
* [ ] BUSLOGIC-005 Number of Times a Function Can be Used Limits
* [ ] BUSLOGIC-006 Circumvention of Work Flows
* [ ] BUSLOGIC-007 Defenses Against Application Mis-use
* [ ] BUSLOGIC-008 Upload of Unexpected File Types
* [ ] BUSLOGIC-009 Upload of Malicious Files

### \[CLIENT\] CLIENT SIDE

* [ ] CLIENT-001 DOM based Cross Site Scripting
* [ ] CLIENT-002 JavaScript Execution
* [ ] CLIENT-003 HTML Injection
* [ ] CLIENT-004 Client Side URL Redirect
* [ ] CLIENT-005 CSS Injection
* [ ] CLIENT-006 Client Side Resource Manipulation
* [ ] CLIENT-007 Cross Origin Resource Sharing
* [ ] CLIENT-008 Cross Site Flashing
* [ ] CLIENT-009 Clickjacking
* [ ] CLIENT-010 WebSockets
* [ ] CLIENT-011 Web Messaging
* [ ] CLIENT-012 Local Storage
* [ ] CLIENT-013 Cross Site Script Inclusion

