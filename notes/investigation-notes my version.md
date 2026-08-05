# Investigation Notes

## Lab Summary

In this lab, we performed some configuration changes-we created a new firewall rule, installed a new app(7-Zip) and compared configuration with the established baseline. We validated these changes using Event Viewer and PowerShell and checked if the event was recorded in Wazuh Discover. 

---

## Analyst Methodology

The investigation followed a structured DFIR workflow:

1. Verify Wazuh Agent is Active.
2. Establish a system baseline.
3. Review Windows configuration.
4. Perform controlled configuration changes.
5. Validate the updated configuration.
6. Investigate Wazuh Discover.

---

## Investigation Scenario

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
An attacker gained administrative acce

---

## Evidence Collected

### Evidence 1 

Collected:

- Network profile
- Firewall configuration
- Hosts file
- Installed applications
- Local users

Finding:

Established the initial system state before testing.

---

### Evidence 2 

Performed:

- Modification of Hosts file by adding a new entry.
- Firewall rule creation
- Safe software installation(7-Zip)
- Temporary local user creation and removal using Command Prompt as Administrator.

Finding:

Generated controlled configuration drift for investigation.

---

### Evidence 3

Commands Used

```powershell
Get-NetFirewallProfile

Get-Content C:\Windows\System32\drivers\etc\hosts

net user
```

Finding:

Confirmed configuration changes directly from the endpoint.

---

### Evidence 4 – Wazuh Discover

Collected:

- Related Windows events
- Available administrative activity

Finding:

Validated centralized collection of supporting endpoint evidence.

---


## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Impair Defenses (Contextual) | T1562 |
| Persistence | Create or Modify System Process (Contextual) | T1543 |

---

