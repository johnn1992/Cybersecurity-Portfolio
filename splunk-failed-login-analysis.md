# Splunk Failed Login Analysis

## Project Overview

This project demonstrates how Splunk can be used to analyze failed login attempts from log data using Splunk Search Processing Language (SPL).

## Objective

- Import a log file into Splunk.
- Search for failed login events.
- Count failed login attempts by IP address.
- Identify suspicious login activity.

## Tools Used

- Splunk Enterprise
- Windows 11
- Sample log file (`failed_login.log`)

## Dataset

The dataset contains both successful and failed login events from multiple IP addresses.

## SPL Query

```spl
FAILED login
| stats count as Failed_Attempts by IP
```

## Results

*To be updated.*

## Screenshots

*To be added.*

## Analysis

*To be added.*

## Conclusion

*To be added.*
