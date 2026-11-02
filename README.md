# Awesome-File-Integrity-Monitoring-FIM

# Awesome File Integrity Monitoring (FIM)

> A curated list of top File Integrity Monitoring (FIM) tools — both SaaS/Hosted commercial platforms and open-source alternatives for self-hosted file integrity and change detection.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [CrowdStrike Falcon FileVantage](#crowdstrike-falcon-filevantage)
  - [Tripwire Enterprise](#tripwire-enterprise)
  - [Qualys FIM](#qualys-fim)
  - [CimTrak](#cimtrak)
  - [SolarWinds Security Event Manager](#solarwinds-security-event-manager)
  - [ManageEngine EventLog Analyzer](#manageengine-eventlog-analyzer)
  - [Trend Micro File Security (Vision One)](#trend-micro-file-security-vision-one)
  - [Netwrix Change Tracker](#netwrix-change-tracker)
- [Open-Source Software](#-open-source-software)
  - [Wazuh](#wazuh)
  - [OSSEC](#ossec)
  - [Samhain](#samhain)
  - [AIDE](#aide)
  - [Vigilant Scanner](#vigilant-scanner)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted File Integrity Monitoring platforms. These are not open-source but are included as reference points for feature comparison.

### CrowdStrike Falcon FileVantage
**Type:** Cloud-native FIM  
Delivers real-time visibility into critical file changes, showing what changed, who did it, and how. Integrates threat intelligence to prioritize risky changes and correlate file modifications with adversary activity. Automated reporting supports PCI, NIST, and other compliance standards. Dashboards provide both macro and micro views of file integrity to reduce alert fatigue [citation:1][citation:14].  
**Best for:** Organizations already in the CrowdStrike Falcon ecosystem seeking integrated FIM with threat intelligence.

### Tripwire Enterprise
**Type:** Enterprise FIM + SCM  
Combines file integrity monitoring with security configuration management (SCM) for real-time change detection across physical, virtual, and cloud environments. Automated compliance reporting for PCI DSS, HIPAA, and other standards. Integrates with Splunk and ServiceNow. Reviewers note strong integrity control and compliance enforcement, but cite a complex interface and high cost for large deployments [citation:2][citation:15].  
**Best for:** Large enterprises requiring mature FIM plus configuration hardening in one platform.

### Qualys FIM
**Type:** Cloud-based FIM  
Detects changes to files, directories, and now databases (Release 4.8). Database monitoring logs structural, setting, or access changes as events. Maintains compliance with PCI DSS, HIPAA, and GDPR. Event reports now include incident name and status columns for correlation [citation:3].  
**Best for:** Qualys customers wanting FIM integrated with vulnerability management and compliance workflows.

### CimTrak
**Type:** Next-gen FIM  
Combines allowlisting, denylisting, and a trusted file registry to reduce change noise by up to 95%. Known bad changes are blocked or rolled back automatically; alerts fire only on unknown changes. Automatic baseline updates handle legitimate changes without human intervention. Integrates with SIEMs, helpdesk, and ticketing systems. Encryption of communications and audit logs included [citation:4].  
**Best for:** Organizations needing automated integrity enforcement and self-healing beyond basic monitoring.

### SolarWinds Security Event Manager
**Type:** FIM within SIEM  
Detects and alerts on changes to critical files, folders, and registry settings. Correlates file audit events with system logs and Active Directory to identify who accessed or modified files and what else happened around the change. Built-in FIM templates and reports support PCI DSS, SOX, HIPAA, NERC CIP, FISMA, and SANS Critical Security Controls [citation:5].  
**Best for:** Teams already using SolarWinds SEM for log management wanting FIM without a separate tool.

### ManageEngine EventLog Analyzer
**Type:** FIM within log management  
Provides FIM alerts to flag critical changes in sensitive files or folders. Playbooks can automate response—for example, restoring the last clean version of a tampered configuration file, logging the incident, and notifying the security team [citation:6].  
**Best for:** Small to mid-sized organizations using ManageEngine for log analysis and SIEM.

### Trend Micro File Security (Vision One)
**Type:** Cloud storage FIM / malware scanning  
Scans files uploaded to or modified in cloud storage (e.g., AWS S3). Can be embedded in CI/CD pipelines to detect malware before distribution. Uses machine learning to detect novel threats. Deploys via CloudFormation, SDK, CLI, or service gateway. Supports quarantine and clean bucket promotion [citation:7].  
**Best for:** Cloud-native teams needing file scanning for storage buckets and CI/CD pipelines.

### Netwrix Change Tracker
**Type:** FIM + change auditing  
Monitors and reports on changes to system and configuration files to detect potential malware infection. Policy templates configure which files are monitored. Supports both agent-based and agentless FIM for network devices (firewalls, routers, switches) and Windows/Linux endpoints. Events tab handles large estates with filtering and masking [citation:8].  
**Best for:** Enterprises needing FIM across both servers and network infrastructure with agentless options.

---

## 🟩 Open-Source Software

Self-hosted, community-driven FIM tools. All listed projects offer source code you can deploy on your own infrastructure.

### Wazuh
**Stack:** C / Python / ELK Stack | **License:** GPL-2.0  
An open-source SIEM and HIDS platform with a robust FIM module. Detects file changes in real-time using inotify (Linux) or equivalent mechanisms on other platforms. Integrates with the ELK Stack for visualization. Research demonstrates Wazuh's effectiveness for real-time FIM and intrusion detection at a fraction of commercial SIEM cost, with active response capabilities [citation:11].  
**Best for:** Teams wanting a full SIEM + HIDS + FIM stack from a single open-source platform.

### OSSEC
**Stack:** C | **License:** GPL-2.0  
The foundational open-source host-based intrusion detection system, used by security teams for decades. Core FIM capabilities include log-based intrusion detection, file integrity monitoring, malware detection, active response, and compliance auditing. The free version provides a basic out-of-the-box ruleset. A commercial "Atomic OSSEC" edition adds real-time FIM, ML-based false positive reduction, and a dashboard [citation:10].  
**Best for:** Individuals, developers, and small teams wanting proven, battle-tested FIM without licensing costs.

### Samhain
**Stack:** C | **License:** GPL-2.0  
A free, open-source FIM/HIDS with a client/server architecture that scales to hundreds or thousands of monitored hosts. Clients pull baseline databases and configuration from the server at startup, perform integrity verification locally, and report only policy violations—minimizing network traffic and server load. Connections are encrypted and authenticated. OpenPGP-signed baselines prevent tampering. Logs to email, syslog, signed log files, SQL databases, and Prelude. Modules check for open ports, hidden processes, mounts, and rogue SUID/SGID files [citation:12].  
**Best for:** Organizations needing scalable, tamper-resistant FIM across many servers.

### AIDE
**Stack:** C | **License:** GPL-2.0  
Advanced Intrusion Detection Environment creates a database from rules defined in a configuration file, then uses it to verify file integrity. Supports multiple message digest algorithms (md5, sha1, rmd160, tiger, haval) and checks all usual file attributes for inconsistencies. A classic, lightweight Unix FIM tool available in Debian and other repositories [citation:13].  
**Best for:** Unix/Linux administrators wanting a simple, dependency-free file integrity checker.

### Vigilant Scanner
**Stack:** Python | **License:** GPL-3.0  
A Python-based CLI tool for monitoring file integrity. Initializes a snapshot of a directory's state (path, hash, size, permissions) in a SQLite database, then scans and compares against that snapshot to detect new, modified, or deleted files. Also includes log analysis capabilities (in progress). Installable via `pip install vigilant-scanner` [citation:9].  
**Best for:** Developers and small teams wanting a lightweight, scriptable FIM tool in Python.

---

## 📊 Comparison at a Glance

| Software | License | Type | Real-time FIM | Best For |
|----------|---------|------|---------------|----------|
| **Falcon FileVantage** | Proprietary | Cloud FIM | ✅ | CrowdStrike ecosystem |
| **Tripwire Enterprise** | Proprietary | FIM + SCM | ✅ | Enterprise compliance |
| **Qualys FIM** | Proprietary | Cloud FIM | ✅ | Qualys integration |
| **CimTrak** | Proprietary | Next-gen FIM | ✅ | Auto-remediation |
| **SolarWinds SEM** | Proprietary | SIEM + FIM | ✅ | Existing SEM users |
| **EventLog Analyzer** | Proprietary | Log + FIM | ✅ | ManageEngine users |
| **Trend Micro File Security** | Proprietary | Cloud storage FIM | ✅ | S3 / CI-CD scanning |
| **Netwrix Change Tracker** | Proprietary | FIM + audit | ✅ | Agentless network devices |
| **Wazuh** | GPL-2.0 | SIEM + HIDS + FIM | ✅ | Full OSS stack |
| **OSSEC** | GPL-2.0 | HIDS + FIM | ✅ (Atomic) | Proven free FIM |
| **Samhain** | GPL-2.0 | FIM / HIDS | ✅ | Scalable tamper-resistant |
| **AIDE** | GPL-2.0 | File integrity checker | ❌ (snapshot) | Simple Unix checking |
| **Vigilant Scanner** | GPL-3.0 | CLI FIM | ❌ (snapshot) | Python scripting |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source File Integrity Monitoring tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
