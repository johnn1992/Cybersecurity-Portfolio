# Splunk Failed Login Analysis

## Project Overview

This lab demonstrates how Splunk can be used to analyze log data and identify failed login attempts using the Search Processing Language (SPL).

## Objective

The objectives of this lab are to:

* Import a log file into Splunk.
* Search for failed login events.
* Count failed login attempts by IP address.
* Identify potentially suspicious IP addresses.

## Tools Used

* Splunk Enterprise
* Windows 11
* Sample log file (`failed_login.log`)

## Dataset

The dataset contains both successful and failed login events generated from multiple IP addresses.

## SPL Query

```spl
FAILED login
| stats count as Failed_Attempts by IP
```

## Results

*Results will be added after running the search in Splunk.*

## Screenshots

*Screenshots will be added after completing the analysis.*

## Analysis

*Analysis will be added after reviewing the search results.*

## Conclusion

*Conclusion will be added after completing the lab.*
