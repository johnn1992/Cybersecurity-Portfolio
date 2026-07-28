# Splunk Failed Login Analysis

## Project Overview

This project demonstrates the use of Splunk Enterprise for Security Information and Event Management (SIEM) analysis by investigating Windows security events through automated log ingestion.

The objective was to analyze authentication activities, identify suspicious login behavior, monitor user activities, and visualize security events using Splunk dashboards.

Unlike my previous Splunk project where logs were manually imported, this project focuses on automated log ingestion and real-world SIEM workflow.

---

## Objectives

- Configure Splunk Enterprise for log monitoring
- Analyze Windows Security Event Logs using SPL queries
- Investigate failed and successful authentication attempts
- Identify privilege logon events
- Analyze user activity patterns
- Visualize security events using Splunk charts and dashboards
- Practice SOC analyst investigation techniques

---

## Tools & Technologies Used

- Splunk Enterprise
- SPL (Search Processing Language)
- Windows Security Event Logs
- Windows Event Viewer
- Splunk Dashboard Visualization

---

## Lab Environment

**Operating System:**
- Windows 11

**SIEM Platform:**
- Splunk Enterprise

**Log Source:**
- Windows Security Event Logs

---

# Investigations Performed

## 1. Failed Logon Attempts

**Objective:**
Identify unsuccessful authentication attempts and analyze potential brute-force activity.

### SPL Query

```spl
index=* EventCode=4625
| stats count by Account_Name, Source_Network_Address
| sort -count
```

### Results

![Failed Logon Attempts](screenshots/01-failed-logon-attempts.png)

### Visualization

![Failed Logon Chart](screenshots/01-failed-logon-chart.png)

---

# 2. Successful Logons

**Objective:**
Identify successful user authentication events and monitor account access.

### SPL Query

```spl
index=* EventCode=4624
| stats count by Account_Name, Logon_Type
| sort -count
```

### Results

![Successful Logons](screenshots/02-successful-logons.png)

### Visualization

![Successful Logons Chart](screenshots/02-successful-logons-chart.png)

---

# 3. Privilege Logon Events

**Objective:**
Detect privileged account logons that may require monitoring.

### SPL Query

```spl
index=* EventCode=4672
| stats count by Account_Name
| sort -count
```

### Results

![Privilege Logon Events](screenshots/03-privilege-logon-events.png)

### Visualization

![Privilege Logon Events Chart](screenshots/03-privilege-logon-events-chart.png)

---

# 4. Event Type Analysis

**Objective:**
Understand the distribution of Windows security events within the environment.

### SPL Query

```spl
index=*
| stats count by EventCode
| sort -count
```

### Results

![Event Type Analysis](screenshots/04-event-type-analysis.png)

### Visualization

![Event Type Analysis Chart](screenshots/04-event-type-analysis-chart.png)

---

# 5. Top User Activity Analysis

**Objective:**
Identify users generating the highest number of security events.

### SPL Query

```spl
index=*
| stats count by Account_Name
| sort -count
```

### Results

![Top User Activity Analysis](screenshots/05-top-user-activity-analysis.png)

### Visualization

![Top User Activity Chart](screenshots/05-top-user-activity-chart.png)

---

# 6. Security Event Activity Timeline

**Objective:**
Analyze security events over time to identify unusual activity patterns.

### SPL Query

```spl
index=*
| timechart count by EventCode
```

### Results

![Security Event Activity Timeline](screenshots/06-security-event-activity-timeline.png)

### Visualization

![Security Event Timeline Chart](screenshots/06-security-event-timeline-chart.png)

---

# Dashboard

A Splunk dashboard was created to provide a centralized view of authentication activity and security events.

The dashboard includes:

- Failed login attempts
- Successful login activity
- Privileged logon events
- Event type distribution
- User activity trends
- Security event timeline

---

# Key Findings

- Identified failed authentication attempts using Windows Event ID 4625
- Monitored successful authentication events using Event ID 4624
- Reviewed privileged logon activity using Event ID 4672
- Analyzed security event patterns across the environment
- Created visual dashboards for easier SOC monitoring

---

# Skills Demonstrated

- Splunk Enterprise Administration
- SPL Query Writing
- SIEM Monitoring
- Windows Event Log Analysis
- Authentication Investigation
- Security Dashboard Creation
- SOC Analyst Investigation Workflow

---

# MITRE ATT&CK Mapping

| Technique | ID | Description |
|---|---|---|
| Valid Accounts | T1078 | Monitoring legitimate account usage |
| Brute Force | T1110 | Detecting repeated failed login attempts |
| Account Discovery | T1087 | Reviewing account activity |

---

# Conclusion

This project demonstrates practical SIEM investigation skills by using Splunk Enterprise to collect, analyze, and visualize Windows security events.

The investigation workflow reflects common SOC analyst responsibilities, including authentication monitoring, threat detection, event analysis, and dashboard reporting.
