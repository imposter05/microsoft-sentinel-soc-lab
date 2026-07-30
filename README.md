# Microsoft Sentinel SOC Lab

A hands-on Microsoft Sentinel portfolio project focused on KQL threat hunting, detection engineering, analytics rules, watchlists, workbooks, threat intelligence, incident investigation, MITRE ATT&CK mapping, and security automation.

This repository documents my practical learning process as I build a beginner-to-intermediate Microsoft Sentinel lab using current Azure and Microsoft Sentinel functionality.

---

## Project Objectives

The objectives of this lab are to:

- Learn how Microsoft Sentinel functions as a cloud-native SIEM and SOAR platform.
- Develop practical Kusto Query Language skills.
- Write and document threat-hunting queries.
- Build scheduled analytics rules that generate incidents.
- Create and query watchlists.
- Build security monitoring workbooks.
- Work with threat intelligence indicators.
- Investigate incidents, entities, and security events.
- Map detections to MITRE ATT&CK.
- Implement basic incident-response automation.
- Produce evidence that can be discussed during SOC analyst interviews.

---

## Lab Environment

| Component | Configuration |
|---|---|
| SIEM platform | Microsoft Sentinel |
| Log platform | Azure Monitor Log Analytics |
| Sentinel workspace | `sentinelLabGithub` |
| Practice environment | Microsoft public Log Analytics demo workspace |
| Query language | Kusto Query Language |
| Cloud platform | Microsoft Azure |
| Documentation platform | GitHub |
| Primary learning focus | SOC analysis and detection engineering |

The public Log Analytics demo workspace is used where my personal Sentinel workspace does not contain enough telemetry.

The demo environment provides pre-existing sample data, allowing KQL queries to be developed without deploying a virtual machine or generating artificial endpoint events.

Available tables may change over time. Queries are therefore tested only against tables currently populated in the selected workspace.

---

## Repository Structure

```text
microsoft-sentinel-soc-lab/
│
├── README.md
├── LICENSE
│
├── 00-environment/
│   ├── README.md
│   └── screenshots/
│
├── 01-kql-hunting/
│   ├── README.md
│   ├── queries/
│   ├── reports/
│   └── screenshots/
│
├── 02-analytics-rules/
│   ├── README.md
│   ├── rules/
│   └── screenshots/
│
├── 03-watchlists/
│   ├── README.md
│   ├── csv/
│   ├── queries/
│   └── screenshots/
│
├── 04-workbooks/
│   ├── README.md
│   ├── templates/
│   └── screenshots/
│
├── 05-threat-intelligence/
│   ├── README.md
│   ├── indicators/
│   ├── queries/
│   └── screenshots/
│
├── 06-incident-investigation/
│   ├── README.md
│   ├── reports/
│   └── screenshots/
│
├── 07-automation-playbooks/
│   ├── README.md
│   ├── templates/
│   └── screenshots/
│
└── 08-mitre-mapping/
    ├── README.md
    └── mitre-mapping.csv