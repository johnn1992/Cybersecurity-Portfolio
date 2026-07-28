# Splunk Failed Login Analysis

## Project Overview

This project demonstrates the use of Splunk Enterprise as a Security Information and Event Management (SIEM) platform to analyze Windows security logs and investigate authentication activity.

The project focuses on detecting failed login attempts, monitoring successful logons, analyzing privileged access events, identifying user activity patterns, and creating visual security dashboards.

This project improves on my previous Splunk lab by using automated log ingestion instead of manually importing log files.

---

## Objectives

* Configure Splunk Enterprise for security log analysis
* Analyze Windows Security Event Logs using SPL queries
* Investigate authentication activity
* Detect failed login attempts
* Monitor privileged account usage
* Identify user activity patterns
* Create security visualizations and dashboards

---

## Tools & Technologies

* Splunk Enterprise
* SPL (Search Processing Language)
* Windows Security Event Logs
* Windows Event Viewer
* Splunk Dashboards

---

## Lab Environment

**Operating System**

* Windows 11

**SIEM Platform**

* Splunk Enterprise

**Log Source**

* Windows Security Event Logs

---

# Security Investigations

## 1. Failed Logon Attempts

**Objective:**
Identify unsuccessful authentication attempts and analyze possible brute-force activity.

### SPL Query

```spl
index=* EventCode=4625
| stats count by Account_Name, Source_Network_Address
| sort -count
```

### Investigation Results

![Failed Logon Attempts](./screenshots/01-failed-logon-attempts.png)

### Visualization

![Failed Logon Chart](./screenshots/01-failed-logon-chart.png)

---

## 2. Successful Logons

**Objective:**
Analyze successful authentication events and identify normal account access activity.

### SPL Query

```spl
index=* EventCode=4624
| stats count by Account_Name, Logon_Type
| sort -count
```

### Investigation Results

![Successful Logons](./screenshots/02-successful-logons.png)

### Visualization

![Successful Logons Chart](./screenshots/02-successful-logons-chart.png)

---

## 3. Privilege Logon Events

**Objective:**
Identify privileged account logon events that require monitoring.

### SPL Query

```spl
index=* EventCode=4672
| stats count by Account_Name
| sort -count
```

### Investigation Results

![Privilege Logon Events](./screenshots/03-privilege-logon-events.png)

### Visualization

![Privilege Logon Events Chart](./screenshots/03-privilege-logon-events-chart.png)

---

## 4. Event Type Analysis

**Objective:**
Analyze the distribution of Windows security events.

### SPL Query

```spl
index=*
| stats count by EventCode
| sort -count
```

### Investigation Results

![Event Type Analysis](./screenshots/04-event-type-analysis.png)

### Visualization

![Event Type Analysis Chart](./screenshots/04-event-type-analysis-chart.png)

---

## 5. Top User Activity Analysis

**Objective:**
Identify accounts generating the highest number of security events.

### SPL Query

```spl
index=*
| stats count by Account_Name
| sort -count
```

### Investigation Results

![Top User Activity Analysis](./screenshots/05-top-user-activity-analysis.png)

### Visualization

![Top User Activity Chart](./screenshots/05-top-user-activity-chart.png)

---

## 6. Security Event Activity Timeline

**Objective:**
Analyze security events over time to identify activity patterns.

### SPL Query

```spl
index=*
| timechart count by EventCode
```

### Investigation Results

![Security Event Activity Timeline](./screenshots/06-security-event-activity-timeline.png)

### Visualization

![Security Event Timeline Chart](./screenshots/06-security-event-timeline-chart.png)

---

# Splunk Dashboard

A Splunk dashboard was created to provide a centralized view of security events.

The dashboard includes:

* Failed authentication attempts
* Successful logons
* Privileged logon events
* Event type distribution
* User activity analysis
* Security event timeline

---

# Key Findings

* Detected failed authentication attempts using Windows Event ID 4625
* Reviewed successful logon activity using Event ID 4624
* Investigated privileged access events using Event ID 4672
* Identified user activity trends through SPL analysis
* Created visualizations for SOC monitoring and reporting

---

# Skills Demonstrated

* Splunk Enterprise
* SPL Query Development
* SIEM Monitoring
* Windows Event Log Analysis
* Authentication Investigation
* Security Dashboard Creation
* SOC Analyst Workflow

---

# MITRE ATT&CK Mapping

| Technique         | ID    | Description                                       |
| ----------------- | ----- | ------------------------------------------------- |
| Valid Accounts    | T1078 | Monitoring legitimate account usage               |
| Brute Force       | T1110 | Detecting repeated failed authentication attempts |
| Account Discovery | T1087 | Reviewing account activity                        |

---

# Conclusion

This project demonstrates practical SIEM investigation skills by using Splunk Enterprise to collect, analyze, and visualize Windows security events.

The workflow represents common SOC analyst activities including authentication monitoring, event investigation, threat detection, and security reporting.
