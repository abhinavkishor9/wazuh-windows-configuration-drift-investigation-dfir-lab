# wazuh-windows-configuration-drift-investigation-dfir-lab

## Overview

In this DFIR lab we see how to investigate unauthorized Windows configuration drift using native Wazuh Discover, PowerShell, Command Prompt, Settings and Windows Defender Firewall.

Unlike single Event ID investigations, this lab focuses on identifying and validating multiple system configuration changes by comparing a baseline system state with the post-change state.


---

# Executive Summary

Imagine your company has a standard Windows build.

Every computer should have:

Windows Firewall enabled
Private Network Profile
Default Hosts file
No unauthorized local users
Approved software only
Default Windows services

One day, a SOC analyst investigates a workstation and discovers:

Firewall rule added
Hosts file modified
Network changed to Public
Unknown software installed
New local user created

None of these changes alone prove malicious activity.

Together, however, they indicate the system has drifted away from its approved configuration.

That is called Configuration Drift.

Most attackers don't immediately encrypt files or delete data.

Instead, they quietly modify system settings to make future access easier.

Examples include:

Adding firewall exceptions
Creating local administrator accounts
Installing remote access software
Changing Windows services
Editing the Hosts file
Changing security policies

These changes may remain long after the attacker has left.

Imagine the IT manager says:

"Nobody was supposed to change this workstation."

But during investigation you discover:

Firewall modified
Hosts file edited
Software installed
Network profile changed

Now you need to determine whether:

IT performed maintenance
A user made the changes
Malware modified the system
An attacker gained administrative access

---

# Learning Objectives

Which configuration settings changed?
Which user-related changes occurred?
Which network changes occurred?
Was the firewall modified?
Was the Hosts file modified?
Was new software installed?
Can the entire change timeline be reconstructed?

---


# Tools Used

- Wazuh Dashboard (Discover)
- PowerShell
- Event Viewer
- Windows Defender Firewall
- Windows Hosts File
- Windows Settings
- Wazuh Agent

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Wazuh 4.12 |
| Endpoint | Windows 11 Pro |
| Server | Oracle Linux 9 |
| Investigation Type | Windows DFIR |
| Artifact Sources | Windows Configuration |
| Sysmon | Not Used |

---

# Investigation Scenario

Imagine the IT manager says:

"Nobody was supposed to change this workstation."

But during investigation you discover:

Firewall modified
Hosts file edited
Software installed
Network profile changed

Now you need to determine whether:

IT performed maintenance
A user made the changes
Malware modified the system
An attacker gained administrative access

---

# Investigation Workflow

1. Verify Wazuh agent is active
2. Establish the system baseline.
3. Review network configuration.
4. Review Windows Firewall configuration.
5. Review the Hosts file.
6. Review installed software(7-Zip)
7. Review local users.
8. Perform controlled configuration changes.
9. Investigate Wazuh Discover.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Impair Defenses (Contextual) | T1562 |
| Persistence | Create or Modify System Process (Contextual) | T1543 |


# Evidence Collected

- Windows Firewall configuration
- Hosts file
- Installed applications
- Local user accounts
- PowerShell validation
- Wazuh Discover results

---



