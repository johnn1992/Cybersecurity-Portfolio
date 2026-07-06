# Lab 4 – Aggressive Scan

## Objective

Learn how to perform an aggressive Nmap scan to gather detailed information about a target.

## Command Used

```bash
sudo nmap -A 10.10.123.25
```

## Explanation

The `-A` option enables multiple advanced scanning features, including:

- Operating System Detection (`-O`)
- Service Version Detection (`-sV`)
- Default NSE Scripts (`-sC`)
- Traceroute

This scan provides a comprehensive overview of the target system and is commonly used during the reconnaissance phase of a penetration test.

## Key Findings

- Detected open ports.
- Identified running services and their versions.
- Attempted operating system detection.
- Executed default NSE scripts.
- Performed traceroute to the target.

## Screenshot

The screenshot will be added after it is uploaded to this folder.
