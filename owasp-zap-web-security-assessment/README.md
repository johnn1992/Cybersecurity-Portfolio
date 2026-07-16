# OWASP ZAP Web Application Security Assessment

## Project Overview

This project demonstrates a web application security assessment performed using **OWASP Zed Attack Proxy (ZAP)**. The objective was to identify common web application vulnerabilities by performing automated scanning against a deliberately vulnerable web application.

The assessment included crawling the application, passive scanning, active scanning, and reviewing the identified security findings.

---

## Objectives

- Learn how to use OWASP ZAP
- Perform automated web application security testing
- Identify common web vulnerabilities
- Analyze discovered security issues
- Generate a professional security assessment report

---

## Tools Used

- OWASP ZAP 2.17.0
- Windows 11
- Google Chrome
- Demo TestFire Web Application

---

## Target Application

**Target:** https://demo.testfire.net

This application is intentionally provided for web security testing and training purposes.

---

## Assessment Methodology

The following steps were performed:

1. Launched OWASP ZAP.
2. Configured an automated scan.
3. Crawled the target application using the Spider.
4. Performed Passive Scanning.
5. Executed Active Scanning.
6. Reviewed discovered vulnerabilities.
7. Generated a security assessment report.

---

## Key Findings

The automated scan identified several security issues, including:

### High Risk

- Reflected Cross-Site Scripting (XSS)
- SQL Injection
- Time-Based SQL Injection

### Medium Risk

- Absence of Anti-CSRF Tokens

### Low Risk

- Content Security Policy (CSP) Header Not Set
- Missing Anti-Clickjacking Header
- Secure Pages Include Mixed Content
- Missing Subresource Integrity Attribute
- Cookie without SameSite Attribute

---

## Sample Vulnerability Analysis

### Reflected Cross-Site Scripting (XSS)

**Risk:** High

**Description**

OWASP ZAP detected reflected Cross-Site Scripting by injecting a JavaScript payload into user input and observing that it was returned in the application's response without proper sanitization.

Example payload:

```html
<script>alert(1)</script>
```

**Potential Impact**

- Session hijacking
- Credential theft
- Phishing attacks
- Malicious JavaScript execution

**Recommended Mitigation**

- Validate all user input
- Encode output before rendering
- Implement a strong Content Security Policy (CSP)
- Sanitize untrusted data

---

### SQL Injection

**Risk:** High

**Description**

The scanner detected SQL Injection by submitting specially crafted SQL statements that altered the application's database query behavior.

Example payload:

```sql
' OR '1'='1' --
```

**Potential Impact**

- Unauthorized database access
- Authentication bypass
- Data theft
- Data modification
- Complete database compromise

**Recommended Mitigation**

- Use parameterized queries (prepared statements)
- Validate user input
- Apply least-privilege database permissions
- Avoid dynamic SQL queries

---

## Skills Demonstrated

- Web Application Security Testing
- Vulnerability Assessment
- OWASP ZAP
- Spidering
- Passive Scanning
- Active Scanning
- Cross-Site Scripting Analysis
- SQL Injection Analysis
- Security Report Generation

---

## Screenshots

### Completed Scan Results

![Completed Scan](screenshots/zap_scan_complete.png)

---

### Reflected Cross-Site Scripting (XSS)

![Reflected XSS](screenshots/xss_reflected_alert.png)

---

### SQL Injection Detection

![SQL Injection](screenshots/sql_injection_alert.png)

---

### Generated HTML Report

![Generated Report](screenshots/report_generated.png)



---

## Report

The complete OWASP ZAP HTML report is available in the **reports** directory.

```
reports/OWASP_ZAP_Report.html
```

---

## Lessons Learned

This project provided practical experience using OWASP ZAP to assess web application security. It demonstrated how automated tools can identify common vulnerabilities such as Cross-Site Scripting (XSS), SQL Injection, missing security headers, and CSRF protections. It also reinforced the importance of understanding scan results and documenting findings in a professional format.

---

## Disclaimer

The target application used in this project is intentionally vulnerable and intended solely for security training and educational purposes. No unauthorized systems were scanned during this assessment.
