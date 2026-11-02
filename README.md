# Awesome File Integrity Monitoring (FIM) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of top File Integrity Monitoring (FIM) tools and systems — comparing commercial enterprise SaaS platforms and self-hosted open-source software for real-time change detection, tamper detection, system auditing, and compliance enforcement (PCI DSS, HIPAA, SOC 2, NIST).  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📈 Sector Overview & Market Dynamics

The global File Integrity Monitoring (FIM) market is estimated at approximately **$1.2B to $1.4B** and is projected to expand to **$3.5B – $4.8B by 2033–2034** at an estimated CAGR of **14% to 16.9%**. Market dynamics reflect a **moderately fragmented sector** transitioning toward consolidation: standalone niche FIM vendors compete with integrated enterprise security conglomerates (EDR/XDR, SIEM, and vulnerability management platforms like CrowdStrike, Qualys, and Trend Micro) that incorporate FIM as an add-on module to satisfy stringent regulatory compliance mandates (PCI DSS 4.0, HIPAA, SOX, and CIS benchmarks).

---

## 📋 Table of Contents

- [Sector Overview & Market Dynamics](#-sector-overview--market-dynamics)
- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
- [Open-Source Software](#-open-source-software)
- [Feature Matrix & Comparison at a Glance](#-feature-matrix--comparison-at-a-glance)
- [Selection Guide: SaaS vs. Open Source](#-selection-guide-saas-vs-open-source)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🟦 SaaS / Hosted Platforms

Commercial, enterprise-grade cloud-hosted File Integrity Monitoring platforms. Sorted in descending order by company size (market valuation / parent annual revenue).

| Platform | Company Valuation / Revenue | Starting Pricing Tier | Free Tier / Trial Limit | Key Capabilities & Highlights |
| :--- | :--- | :--- | :--- | :--- |
| **CrowdStrike Falcon FileVantage** | ~$75B+ Market Cap ($4.81B+ ARR) | Base Falcon bundles start at $59.99/device/yr ($4.99/mo); FileVantage enterprise module starts ~$600–$850/endpoint/yr via custom quote | 15-day free trial (full-featured access across Falcon cloud platform modules) | Real-time visibility into file modifications with adversary threat intelligence correlation, reducing alert fatigue and accelerating PCI DSS reporting. |
| **Trend Micro File Security (Vision One)** | ~$4.4B Market Cap (~$1.9B USD ARR) | Pay-as-you-go consumption model starting at $0.013/scan or ~$1.15/storage bucket/hr | 30-day free trial (Trend Vision One / Cloud One platform with 500 cloud scan credits) | Cloud storage (AWS S3, Azure Blob) and CI/CD pipeline file scanning with automated quarantine and malware protection. |
| **Qualys FIM** | ~$6.3B Market Cap ($669M+ ARR) | Enterprise subscription starting at ~$199/asset/yr via Qualys Cloud Platform | 30-day free trial (covers Qualys Cloud Platform apps including VMDR and FIM sensors) | Unified cloud-agent monitoring for files, directories, registries, and database structures with built-in PCI DSS, HIPAA, and GDPR audit templates. |
| **SolarWinds Security Event Manager (SEM)** | ~$3.2B Market Cap ($797M ARR) | Subscription licenses starting at $1,789 (or ~$15/monitored node/month) | 30-day free trial (fully functional SEM evaluation for up to 30 nodes) | Correlates real-time file audit events with Active Directory logs and system security events to determine who altered critical files. |
| **ManageEngine EventLog Analyzer** | ~$1B+ Revenue (Zoho Corp Division) | Premium licenses start at $795/year for up to 10–50 monitored log sources/devices | Free-Forever Edition (up to 5 log sources with search, basic compliance reporting, and archival) | FIM alerts integrated into SIEM log management with automated incident playbooks to restore tampered configuration files. |
| **Tripwire Enterprise (Fortra)** | ~$800M Revenue (Fortra PE Group) | Enterprise quote-based model; industry benchmarks start at ~$2.50–$10/node/month | 14-day assisted proof-of-concept / evaluation upon sales qualification | Industry standard enterprise FIM combining file integrity with Security Configuration Management (SCM) and hardening checks. |
| **Netwrix Change Tracker** | ~$245M ARR (PE Backed) | Subscription starting at $600/year per 10 devices (~$60/device/year) | 14-day free trial (full-featured evaluation for Windows, Linux, and network devices) | Hybrid agent-based and agentless FIM for servers, workstations, and network appliances (switches, firewalls, routers). |
| **CimTrak (Cimcor)** | ~$10M Revenue (Privately Held) | Custom quote-based per endpoint; typically benchmarked 25–40% lower than legacy FIM suites | 14-day to 30-day free trial (full software evaluation upon request) | Next-generation FIM with automated rollback, trusted baseline repositories, and self-healing mechanisms that reverse unauthorized file tampering. |

---

## 🟩 Open-Source Software

Self-hosted, community-driven File Integrity Monitoring tools. Sorted in descending order by GitHub stargazer count.

| Project & Repository | GitHub Stars | Stack / Language | License | Primary Architectural Focus |
| :--- | :--- | :--- | :--- | :--- |
| [**osquery**](https://github.com/osquery/osquery) | [![GitHub stars](https://img.shields.io/github/stars/osquery/osquery?style=social&color=white)](https://github.com/osquery/osquery/stargazers) | C++ / C / Python | Apache-2.0 | Exposes the operating system as a high-performance relational database; performs real-time FIM via `file_events` tables backed by OS-native APIs (`inotify`, `FSEvents`, Windows ReadDirectoryChangesW). |
| [**Wazuh**](https://github.com/wazuh/wazuh) | [![GitHub stars](https://img.shields.io/github/stars/wazuh/wazuh?style=social&color=white)](https://github.com/wazuh/wazuh/stargazers) | C / Python / OpenSearch | GPL-2.0 | Enterprise open-source SIEM & XDR with built-in real-time FIM `syscheck` module; monitors file modifications, file hashes, permissions, and registry keys across Linux, Windows, and macOS. |
| [**OSSEC**](https://github.com/ossec/ossec-hids) | [![GitHub stars](https://img.shields.io/github/stars/ossec/ossec-hids?style=social&color=white)](https://github.com/ossec/ossec-hids/stargazers) | C | GPL-2.0 | Battle-tested host-based intrusion detection system (HIDS) providing periodic and real-time checksum monitoring, rootkit detection, and active automated threat response. |
| [**Tripwire Open Source**](https://github.com/Tripwire/tripwire-open-source) | [![GitHub stars](https://img.shields.io/github/stars/Tripwire/tripwire-open-source?style=social&color=white)](https://github.com/Tripwire/tripwire-open-source/stargazers) | C++ | GPL-2.0 | The open-source Linux/UNIX baseline engine of Tripwire; scans system objects, compares cryptographic hash signatures against a signed baseline, and detects unauthorized drift. |
| [**AIDE (Advanced Intrusion Detection Environment)**](https://github.com/aide/aide) | [![GitHub stars](https://img.shields.io/github/stars/aide/aide?style=social&color=white)](https://github.com/aide/aide/stargazers) | C | GPL-2.0 | Lightweight, dependency-free command-line FIM for UNIX/Linux distributions; creates a cryptographic database baseline to verify permissions, timestamps, and message digests. |
| [**Achiefs/fim**](https://github.com/Achiefs/fim) | [![GitHub stars](https://img.shields.io/github/stars/Achiefs/fim?style=social&color=white)](https://github.com/Achiefs/fim/stargazers) | Rust | MIT | High-performance, low-overhead host-based file integrity monitor written in Rust; performs real-time file system analysis, change auditing, and kernel audit daemon telemetry. |
| [**binsnitch**](https://github.com/NVISOsecurity/binsnitch) | [![GitHub stars](https://img.shields.io/github/stars/NVISOsecurity/binsnitch?style=social&color=white)](https://github.com/NVISOsecurity/binsnitch/stargazers) | Python | GPL-3.0 | Specialized endpoint integrity checker that hashes executable binaries at execution or on schedule, detecting stealthy binary modification and malicious persistence. |
| [**vigilant-scanner**](https://github.com/ivpel/vigilant-scanner) | [![GitHub stars](https://img.shields.io/github/stars/ivpel/vigilant-scanner?style=social&color=white)](https://github.com/ivpel/vigilant-scanner/stargazers) | Python | GPL-3.0 | Scriptable Python CLI tool that captures SQLite snapshot baselines of directories (permissions, hashes, file metadata) and alerts on changes or anomalies. |
| [**Samhain**](https://www.la-samhna.de/samhain/) | *Independent Project* | C | GPL-2.0 | Tamper-resistant centralized client/server HIDS & FIM running as an ongoing daemon; features cryptographic baseline signing, stealth rootkit detection, and minimal network overhead. |

---

## 📊 Feature Matrix & Comparison at a Glance

| Solution | Deployment Model | Real-time FIM | Registry / DB Monitoring | Automated Remediation / Rollback | Compliance Mappings (PCI DSS, HIPAA) | Best For |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| **CrowdStrike Falcon FileVantage** | Cloud SaaS | ✅ | ✅ | ❌ (Alert/Kill) | ✅ Full | Large enterprises with Falcon EDR |
| **Trend Micro File Security** | Cloud SaaS | ✅ | ❌ (File/Object) | ✅ (Quarantine) | ✅ Partial | AWS S3, Azure Blob & CI/CD build artifacts |
| **Qualys FIM** | Cloud SaaS | ✅ | ✅ (incl. DBs) | ❌ (Alert) | ✅ Full | Qualys VMDR customers & hybrid estates |
| **SolarWinds SEM** | Self-Hosted / SaaS | ✅ | ✅ | ✅ (Playbooks) | ✅ Full | Centralized SIEM & log-driven FIM |
| **ManageEngine EventLog Analyzer** | On-Prem / SaaS | ✅ | ✅ | ✅ (Config Restore) | ✅ Full | SMBs needing cost-effective log + FIM |
| **Tripwire Enterprise** | Hybrid Cloud | ✅ | ✅ | ✅ (Policy Actions) | ✅ Full | Strict compliance & Configuration Hardening |
| **Netwrix Change Tracker** | Hybrid Cloud | ✅ | ✅ | ❌ (Alert) | ✅ Full | Agentless network switches & mixed fleets |
| **CimTrak** | Hybrid Cloud | ✅ | ✅ | ✅ (Auto Self-Healing) | ✅ Full | Zero-trust integrity with automatic rollbacks |
| **osquery** | Self-Hosted OSS | ✅ | ✅ | ❌ (Query layer) | ⚠️ Custom queries | SQL-based fleet observability & endpoint telemetry |
| **Wazuh** | Self-Hosted OSS | ✅ | ✅ | ✅ (Active Response) | ✅ Full | Complete open-source SIEM + XDR stack |
| **OSSEC** | Self-Hosted OSS | ⚠️ (Atomic has RT) | ❌ | ✅ (Active Response) | ⚠️ Basic rules | Battle-tested, lightweight host intrusion defense |
| **Tripwire Open Source** | Self-Hosted OSS | ❌ (Snapshot) | ❌ | ❌ | ⚠️ Scriptable | Standalone Linux servers needing integrity baselines |
| **AIDE** | Self-Hosted OSS | ❌ (Snapshot) | ❌ | ❌ | ⚠️ Scriptable | Standard Linux cron-based integrity verification |
| **Achiefs/fim** | Self-Hosted OSS | ✅ | ❌ | ❌ | ⚠️ Scriptable | Low-footprint, modern Rust file watching |
| **binsnitch** | Self-Hosted OSS | ❌ (On-demand) | ❌ | ❌ | ❌ | Binary file validation & stealth tampering checks |
| **vigilant-scanner** | Self-Hosted OSS | ❌ (Snapshot) | ❌ | ❌ | ❌ | Python-friendly scriptable directory auditing |
| **Samhain** | Self-Hosted OSS | ✅ (Daemon) | ❌ | ❌ | ⚠️ Manual | High-security, tamper-resistant UNIX server fleets |

---

## 🎯 Selection Guide: SaaS vs. Open Source

- **Choose SaaS / Commercial Platforms when:**
  - You must satisfy strict annual **PCI DSS 4.0 (Requirement 11.5)** or **HIPAA Security Rule** audits with certified out-of-the-box reports.
  - You require automated alert-noise reduction, auto-remediation (like CimTrak’s rollback or ManageEngine’s file restores), and cross-asset correlation.
  - Your security team wants unified management across endpoints, servers, cloud storage buckets (S3/GCS), and network devices without maintaining backend infrastructure.

- **Choose Open-Source Solutions when:**
  - You require total privacy and data sovereignty where file metadata or audit trails cannot leave air-gapped or on-premises networks.
  - You run Linux-heavy infrastructure and want deep scriptability via SQL ([osquery](https://github.com/osquery/osquery)) or comprehensive open-source SIEM capabilities ([Wazuh](https://github.com/wazuh/wazuh)).
  - You prefer zero software licensing overhead and can integrate baseline scans into existing CI/CD or log monitoring workflows.

---

## 🤝 Contributing

Contributions are welcome! If you know of an active open-source File Integrity Monitoring tool or have suggestions to enhance this list:

1. Fork this repository.
2. Create a descriptive branch (`git checkout -b add-tool-name`).
3. Commit your additions (`git commit -m "Add tool-name"`).
4. Push to your branch and open a Pull Request.

Please ensure open-source submissions are actively maintained and licensed under recognized OSI-compliant licenses.

---

## 📄 License

This repository is curated and made available under the [CC0 1.0 Universal](LICENSE) (Public Domain Dedication). Listed software products and trademarks are property of their respective owners.
