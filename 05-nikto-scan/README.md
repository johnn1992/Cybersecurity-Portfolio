# Nikto Web Server Vulnerability Scan

## Objective

The objective of this lab was to perform a web server vulnerability scan using Nikto against a Metasploitable 2 target. The goal was to identify common web server misconfigurations, outdated software, exposed files, and other potential security issues.

## Tools Used

- Nikto
- Kali Linux
- Metasploitable 2

## ## Target Information

- Target IP: 192.168.254.128
- Protocol: HTTP
- Port: 80/tcp

## Command Used

```bash
nikto -h http://192.168.254.128
```

## Key Findings

The Nikto scan identified several potential security issues on the target web server, including:

- Outdated Apache 2.2.8 web server.
- Missing security headers such as **X-Frame-Options** and **X-Content-Type-Options**.
- HTTP TRACE method enabled, which may expose the server to Cross-Site Tracing (XST) attacks.
- Publicly accessible **phpinfo()** page exposing server configuration details.
- Directory indexing enabled on multiple directories, including `/doc/`, `/test/`, and `/icons/`.
- Exposed **phpMyAdmin** interface that should be restricted to authorized users.
- Apache default files and documentation accessible.
- Potential information disclosure through PHP configuration and backup files.

## Security Observations

The scan revealed several common web server misconfigurations and information disclosure issues. While these findings do not automatically mean the server is compromised, they increase the attack surface and provide valuable information that could assist an attacker during reconnaissance. Regular patching, disabling unnecessary features, restricting administrative interfaces, and implementing secure HTTP headers can significantly improve the server's security posture.

## Evidence

### Initial Nikto Scan

![Initial Nikto Scan](Screenshot%202026-07-07%20153129.png)

### Nikto Findings

![Nikto Findings](Screenshot%202026-07-07%20153151.png)

### Scan Results File

[nikto_scan.txt](nikto_scan.txt)
