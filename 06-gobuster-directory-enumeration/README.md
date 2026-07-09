# Gobuster Directory Enumeration

## Objective

The objective of this lab was to perform web directory enumeration against a Metasploitable 2 web server using Gobuster. The goal was to discover hidden directories and files that may expose additional information or attack surfaces.

## Tool Used

- Gobuster v3.8.2
- Kali Linux
- Metasploitable 2 (Target)

## Target Information

- Target IP: 192.168.254.128
- Service: HTTP
- Port: 80/tcp

## Command Used

```bash
gobuster dir -u http://192.168.254.128 -w /usr/share/seclists/Discovery/Web-Content/common.txt
## Evidence

### Gobuster Scan Screenshot

![Gobuster Scan Screenshot](Screenshot%202026-07-09%20122235.png)

### Gobuster Results

The full scan output is available in [gobuster-results.txt](gobuster-results.txt).
