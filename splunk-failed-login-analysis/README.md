# Splunk Failed Login Analysis

## Project Overview

This project demonstrates how Splunk can be used to analyze authentication logs and identify failed login attempts using Splunk Search Processing Language (SPL).

## Objective

The objectives of this lab are to:

* Import log data into Splunk.
* Search for failed login events.
* Count failed login attempts by IP address.
* Identify potentially suspicious login activity.

## Tools Used

* Splunk Enterprise
* Windows 11
* Sample log file (`failed_login.log`)

## Dataset

The dataset contains successful and failed login events from multiple IP addresses.

## SPL Query

```spl
FAILED login
| stats count as Failed_Attempts by IP
```

## Results

*Results will be added after running the SPL query.*

## Screenshots

*Screenshots of the imported log and search results will be added here.*

## Analysis

*Analysis of the search results will be added here.*

## Conclusion

*The conclusion will be added after completing the analysis.*
