# Investigation Notes

## Lab Summary

This investigation focused on identifying unauthorized Windows configuration drift using native Windows tools and Wazuh Discover.

Rather than investigating a single event, the investigation compared the system configuration before and after controlled administrative changes to identify differences and validate endpoint evidence.

---

## Analyst Methodology

The investigation followed a structured DFIR workflow:

1. Verify Wazuh agent connectivity.
2. Establish a system baseline.
3. Review Windows configuration.
4. Perform controlled configuration changes.
5. Validate the updated configuration.
6. Investigate Wazuh Discover.
7. Correlate evidence.
8. Document findings.

---

## Investigation Scenario

A Windows workstation was suspected of unauthorized configuration changes following administrative activity.

The investigation aimed to determine:

- Which configuration settings changed.
- Whether the changes could be validated.
- Whether Wazuh collected supporting evidence.
- Whether the endpoint differed from the original baseline.

---

## Evidence Collected

### Evidence 1 – Baseline Collection

Collected:

- Network profile
- Firewall configuration
- Hosts file
- Installed applications
- Local users

Finding:

Established the initial system state before testing.

---

### Evidence 2 – Configuration Changes

Performed:

- Hosts file modification
- Firewall rule creation
- Safe software installation
- Temporary local user creation and removal

Finding:

Generated controlled configuration drift for investigation.

---

### Evidence 3 – PowerShell Validation

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

## DFIR Analysis

The investigation demonstrated that configuration drift investigations rely on comparing baseline and current system states rather than analyzing isolated Windows events. Native Windows tools provided authoritative evidence, while Wazuh Discover supplied centralized event correlation.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Impair Defenses (Contextual) | T1562 |
| Persistence | Create or Modify System Process (Contextual) | T1543 |

---

## Analyst Observations

- Establishing a baseline is essential before investigating drift.
- Endpoint validation should always precede SIEM analysis.
- Multiple configuration artifacts improve investigative confidence.
- PowerShell provides rapid validation of Windows configuration.
- Wazuh complements endpoint investigations through centralized log collection.

---

## Conclusion

This investigation demonstrated how Windows configuration drift can be identified by comparing baseline and post-change system states while correlating native Windows evidence with Wazuh Discover.
