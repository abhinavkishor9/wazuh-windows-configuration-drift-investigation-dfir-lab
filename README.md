# wazuh-windows-configuration-drift-investigation-dfir-lab

## Overview

This Digital Forensics and Incident Response (DFIR) lab demonstrates how to investigate unauthorized Windows configuration drift using native Windows tools and Wazuh Discover.

Unlike single Event ID investigations, this lab focuses on identifying and validating multiple system configuration changes by comparing a baseline system state with the post-change state.

The investigation uses Windows PowerShell, Event Viewer, Windows configuration utilities, and Wazuh Discover to correlate endpoint evidence and reconstruct configuration changes.

---

# Executive Summary

This investigation focused on identifying Windows configuration drift through controlled administrative changes and validating the resulting artifacts using Windows and Wazuh.

The investigation included:

- Establishing a baseline configuration
- Reviewing Windows network settings
- Reviewing Windows Firewall configuration
- Reviewing the Hosts file
- Reviewing installed software
- Reviewing local user accounts
- Performing controlled configuration changes
- Validating changes using PowerShell
- Investigating Wazuh Discover
- Correlating endpoint evidence

The investigation demonstrates how DFIR analysts identify unauthorized configuration changes by comparing baseline and post-change system states.

---

# Learning Objectives

- Understand Windows configuration drift.
- Establish a system baseline.
- Investigate Windows configuration changes.
- Validate configuration using PowerShell.
- Investigate endpoint activity using Wazuh Discover.
- Correlate multiple evidence sources.
- Reconstruct a configuration drift timeline.

---

# Skills Demonstrated

- Windows DFIR Investigation
- Configuration Drift Analysis
- Baseline Comparison
- Windows PowerShell Investigation
- Windows Firewall Investigation
- Hosts File Analysis
- Local User Investigation
- Software Inventory Validation
- Wazuh Discover Investigation
- Timeline Reconstruction
- Digital Evidence Documentation
- DFIR Troubleshooting
- MITRE ATT&CK Mapping

---

# Tools Used

- Wazuh Dashboard (Discover)
- Windows PowerShell
- Windows Event Viewer
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

A Windows workstation was suspected of having unauthorized configuration changes following an administrative session.

The investigation aimed to determine:

- Which system settings changed
- Whether the changes could be validated
- Whether Wazuh collected supporting evidence
- Whether the endpoint configuration differed from the established baseline

---

# Investigation Workflow

1. Verify Wazuh agent connectivity.
2. Establish the system baseline.
3. Review network configuration.
4. Review Windows Firewall configuration.
5. Review the Hosts file.
6. Review installed software.
7. Review local users.
8. Perform controlled configuration changes.
9. Validate the updated configuration.
10. Investigate Wazuh Discover.
11. Correlate evidence.
12. Document findings.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Impair Defenses (Contextual) | T1562 |
| Persistence | Create or Modify System Process (Contextual) | T1543 |

### Why Configuration Drift Investigations Matter

Unauthorized configuration changes often indicate administrative misuse, insider activity, malware persistence, or unauthorized maintenance. Comparing system baselines against current configurations helps analysts quickly identify unexpected changes during DFIR investigations.

---

# Evidence Collected

- Windows Firewall configuration
- Hosts file
- Installed applications
- Local user accounts
- PowerShell validation
- Wazuh Discover results

---

# Evidence Correlation

| Evidence Source | Information Obtained | Investigation Value |
|-----------------|---------------------|--------------------|
| PowerShell | Current configuration | Primary validation |
| Event Viewer | Administrative events | Supporting evidence |
| Wazuh Discover | SIEM visibility | Centralized correlation |
| Windows Settings | Configuration state | Baseline comparison |

---

# Investigation Findings

- A baseline configuration was established before testing.
- Controlled configuration changes were performed safely.
- Endpoint configuration was validated using PowerShell.
- Wazuh Discover was used to investigate available supporting events.
- Multiple evidence sources were correlated to reconstruct configuration drift.

---

# Key Takeaways

- Configuration drift investigations begin with establishing a baseline.
- Multiple system components should be validated during DFIR investigations.
- Endpoint validation should always precede SIEM analysis.
- Wazuh complements native Windows evidence.
- Correlating multiple artifacts improves investigation reliability.

---
