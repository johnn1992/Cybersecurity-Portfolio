# Splunk Failed Login Analysis
| IP Address   | Failed Attempts |
| ------------ | --------------- |
| 185.22.45.10 | 2               |
| 203.0.113.50 | 1               |

## Objective
Analyze authentication logs using Splunk to identify failed login attempts and detect IP addresses with repeated failures.

## Tool Used
- Splunk

## Dataset
A sample authentication log file containing successful and failed login events was imported into Splunk for analysis.

## SPL Query Used

```spl
FAILED login | stats count as Failed_Attempts by IP
Screenshot
![Splunk Failed Login Results](screenshots/splunk_failed_login_results.png)
Conclusion

The Splunk analysis successfully identified IP addresses associated with failed login attempts. The IP address with the highest number of failures can be investigated further for possible brute-force login activity
