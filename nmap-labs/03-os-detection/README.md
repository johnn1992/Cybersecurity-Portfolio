# Lab 3 – OS Detection

## Objective

Learn how to identify the operating system of a target host using Nmap.

## Command Used

```bash
sudo nmap -O scanme.nmap.org
```

## Explanation

The `-O` option enables operating system detection. Nmap analyzes the target's network responses and attempts to identify the operating system it is running.

> **Note:** OS detection usually requires administrator/root privileges, which is why `sudo` is used on Linux.

## Key Findings

- Attempted operating system detection on the target.
- Observed Nmap's OS fingerprinting process.
- Learned that OS detection works best when enough open and closed ports are available.

## Screenshot

![OS Detection Screenshot](Screenshot%202026-07-06%20090822.png?raw=true)
