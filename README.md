# 🛡️ Windows Detection & Monitoring Lab with Splunk

A Security Operations Center (SOC) lab built using **Splunk Enterprise** to collect, monitor, and analyze Windows Security Event Logs. This project demonstrates Windows log collection, authentication monitoring, process monitoring, dashboard creation, and basic threat hunting using Splunk Search Processing Language (SPL).

---

## 📌 Project Overview

The objective of this project was to build a basic Windows SOC monitoring environment capable of collecting Windows Security Event Logs and visualizing them through interactive Splunk dashboards.

The project covers:

- Windows Security Log Collection
- Authentication Monitoring
- Process Monitoring
- Security Event Analysis
- Dashboard Development
- SPL Query Development
- Basic Threat Hunting

---

# 🏗️ Lab Architecture

```
                   Windows 11
                        │
          Windows Security Event Logs
                        │
                        ▼
         Splunk Universal Forwarder
                        │
                        ▼
              Splunk Enterprise
                        │
        ┌───────────────┼───────────────┐
        │               │               │
        ▼               ▼               ▼
Windows Security   Authentication   Process
Operations Center   Monitoring      Monitoring
```

---

# 🛠️ Technologies Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Windows 11
- Windows Security Event Logs
- Search Processing Language (SPL)

---

# 📂 Project Structure

```
Windows-Detection-Monitoring-Lab/
│
├── README.md
├── Screenshots/
│   ├── Windows-Security-Operations-Center.png
│   ├── Authentication-Monitoring.png
│   └── Process-Monitoring.png
│
├── SPL-Queries/
│
├── Config/
│
├── Diagrams/

```

---

# 📊 Dashboards

## 🛡️ Windows Security Operations Center

Provides a high-level overview of Windows Security events and overall system activity.

### Dashboard Panels

- Total Security Events
- Successful Logins
- Failed Logins
- Process Creation Events
- Events Over Time
- Top Event IDs
- Top Users
- Top Executed Processes
- Logon Types
- Events by Source
- Events by Sourcetype
- Top Creator Processes
- Recent Process Activity

---

## 🔐 Authentication Monitoring

Monitors authentication-related activity and login behavior.

### Dashboard Panels

- Successful Login Count
- Failed Login Count
- Successful Logins Over Time
- Failed Logins Over Time
- Top Successful Users
- Top Failed Users
- Logon Type Distribution
- Failed Login Attempts by Computer
- Authentication Event IDs
- Latest Authentication Events

---

## ⚙️ Process Monitoring

Tracks Windows process creation events and parent-child process relationships.

### Dashboard Panels

- Total Processes Created
- Process Creation Timeline
- Top Executed Processes
- Top Parent Processes
- PowerShell Executions
- Command Prompt Executions
- PowerShell Spawned by CMD
- CMD Spawned by PowerShell
- Most Active Users Creating Processes
- Latest Process Activity

---

# 📋 Windows Event IDs Used

| Event ID | Description |
|----------|-------------|
| **4624** | Successful Logon |
| **4625** | Failed Logon |
| **4688** | Process Creation |

---

# 🔎 Example SPL Queries

## Successful Logins

```spl
index=main EventCode=4624
| stats count
```

## Failed Logins

```spl
index=main EventCode=4625
| stats count
```

## Process Creation Events

```spl
index=main EventCode=4688
| stats count
```

## Top Executed Processes

```spl
index=main EventCode=4688
| top limit=10 New_Process_Name
```

## Latest Process Activity

```spl
index=main EventCode=4688
| table _time Account_Name New_Process_Name Creator_Process_Name Process_Command_Line
| sort -_time
```

---

# 🎯 Skills Demonstrated

- Windows Security Monitoring
- Splunk Administration
- Windows Event Log Analysis
- Authentication Monitoring
- Process Monitoring
- SPL Query Development
- Dashboard Design
- Security Event Analysis
- Threat Hunting Fundamentals

---

# 🚀 Future Improvements

- Integrate Microsoft Sysmon
- Create custom Splunk alerts
- Build advanced detection rules
- Add MITRE ATT&CK mapping
- Email alerting
- Additional threat hunting dashboards

---

# 📚 Learning Outcomes

Through this project I gained practical experience in:

- Configuring Splunk Enterprise
- Forwarding Windows Event Logs
- Writing SPL queries
- Building interactive security dashboards
- Monitoring authentication events
- Monitoring Windows process creation
- Investigating Windows Security Events
- Performing basic threat hunting

---

# 👨‍💻 Author

**Shaurya**

B.Tech Computer Science Engineering Student  
Cybersecurity Enthusiast

## ⭐ If you found this project helpful, consider giving the repository a star!
