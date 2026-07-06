# Lab 2 – Service Version Scan

## Objective

Learn how to identify the versions of services running on open ports using Nmap.

## Command Used

```bash
nmap -sV scanme.nmap.org
```

## Explanation

The `-sV` option tells Nmap to probe open ports and determine the version of the services running on them. This provides more detailed information than a basic scan.

## Key Findings

- Identified open ports on the target.
- Detected service names and version information.
- Learned how service version detection improves reconnaissance.

## Screenshot

![Service Version Scan Screenshot](Screenshot%202026-07-03%20110853.png?raw=true)
