# Nikto Web Server Scan

## Objective

The objective of this lab was to use Nikto to scan a vulnerable web server running on Metasploitable 2 and identify common web server misconfigurations and security issues.

## Lab Environment

- Attacker Machine: Kali Linux
- Target Machine: Metasploitable 2
- Target IP: 192.168.254.128
- Tool Used: Nikto 2.5.0

## Command Used

```bash
nikto -h http://192.168.254.128
```

## Key Findings

The scan identified several security issues, including:

- Outdated Apache web server version.
- Missing X-Frame-Options security header.
- Missing X-Content-Type-Options security header.
- HTTP TRACE method enabled.
- Directory indexing enabled.
- phpinfo.php file accessible.
- phpMyAdmin directory exposed.
- Sensitive configuration files detected.

## Evidence

### Nikto Scan Screenshot

*Upload your screenshot here.*

### Scan Output

Upload the `nikto_scan.txt` file to this folder as evidence of the complete scan.

## Skills Demonstrated

- Web server vulnerability scanning
- Vulnerability identification
- Security assessment
- Nikto usage
- Documentation and reporting

## Disclaimer

This scan was performed in a controlled lab environment against Metasploitable 2 for educational purposes only.
