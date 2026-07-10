## Command Used

```bash
gobuster dir -u http://192.168.254.128 -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

## Findings

Gobuster discovered the following resources:

- `/phpMyAdmin/` - PHP database administration interface
- `/phpinfo.php` - PHP information disclosure page
- `/dav/` - WebDAV directory
- `/test/` - Test directory
- `/twiki/` - Wiki application
- `/index.php` - Main web page

## Security Observations

Directory enumeration helps identify hidden resources on web servers. Exposed directories, administrative panels, and information disclosure pages can increase the attack surface of a web application.

## Evidence

### Gobuster Scan Screenshot

![Gobuster Scan Screenshot](gobuster-scan.png)

### Gobuster Results File

[gobuster-results.txt](gobuster-results.txt)
