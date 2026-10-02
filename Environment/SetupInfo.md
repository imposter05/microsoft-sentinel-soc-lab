# Microsoft Sentinel Lab Environment Setup

## Overview
This lab environment was designed to simulate a realistic Microsoft Sentinel SOC setup with a Windows endpoint, an attacker machine, and a security operations environment used for monitoring and analysis.

The purpose of the setup was to onboard a real corporate workstation into Azure Arc, collect Windows security events through the Azure Monitor Agent (AMA), and send that telemetry to a Log Analytics workspace so it could be analyzed in Microsoft Sentinel.

## Lab Components

### 1. Windows Endpoint (Corporate Employee Device)
A HP notebook with an AMD processor and 4 GB RAM was used as the regular employee workstation in the organization.

This machine represented a typical company endpoint that needed to be monitored and protected.

### 2. Attacker Machine
A separate machine was used to simulate malicious activity. It was running Debian Kali Linux 12.x 64-bit inside a VMware Fusion virtual machine.

This environment allowed testing of attack behavior from a security perspective without affecting the production environment.

### 3. SOC Monitoring Device
A MacBook Pro with 16 GB RAM was used as the analyst workstation. Microsoft Sentinel was used from this device to monitor and investigate security activity.

This reflects a real-world SOC scenario where analysts work from a central monitoring platform to detect threats and investigate suspicious activity.

## Setup Process

The Windows endpoint was enrolled into Azure Arc by running the onboarding script in PowerShell as an administrator. Once the script executed successfully, the device was connected to Azure and became available for monitoring.

Before the endpoint was monitored in Microsoft Sentinel, Windows security events were collected through the Azure Monitor Agent (AMA). This allowed the system to send operating system security telemetry such as login events, process activity, and related audit data to Azure Monitor and Log Analytics.

The next step was to configure a Data Collection Rule (DCR) so that the endpoint’s Windows security logs were sent to the correct Log Analytics workspace. This is the key connection between the endpoint and the SIEM environment.

## Screenshot References

### Screenshot 1: Azure Arc Connection
See [Device connected EP](screenshots/Device%20connected%20EP.webp).

This screenshot shows the Azure Arc machine page with the endpoint connected successfully. The status confirms that the Windows machine was properly onboarded and is reporting as connected.

### Screenshot 2: PowerShell Onboarding Script
See [Script Runs and connects on HP endpoint](screenshots/Script%20Runs%20and%20connects%20on%20HP%20endpoint.webp).

This screenshot demonstrates the Azure Arc onboarding script running in PowerShell. It shows the script executing and the endpoint being registered into Azure Arc. This is the step that established the secure connection between the workstation and the cloud monitoring environment.

### Screenshot 3: Data Collection Rule
See [Data Collection Rule](data%20Collection%20Rule.png).

This screenshot highlights the Data Collection Rule configuration. It shows the flow from the Windows machine to the Microsoft Sentinel/Log Analytics destination. In simple terms, the configuration shows:

- Resource: Windows Machines
- Data collected: SecurityEvent
- Destination: Log Analytics Workspace

This confirms that security events from the endpoint are being collected and sent to the reporting and analysis workspace used by Microsoft Sentinel.

## Final Outcome
The end result of this setup was a working SOC lab where a Windows endpoint could be monitored through Azure Arc, security telemetry could be captured through AMA, and the events could be ingested into Microsoft Sentinel for analysis.

This provides the foundation for threat hunting, detection engineering, incident investigation, and SOC analysis activities.

---

This setup is a practical example of how a modern security environment connects endpoint visibility to cloud-based monitoring and detection workflows.
