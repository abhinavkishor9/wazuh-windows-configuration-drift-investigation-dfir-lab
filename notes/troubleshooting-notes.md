# Troubleshooting Notes

## Issue 1 — Network Profile Already Public

### Cause

The endpoint was already configured with a Public network profile.

### Resolution

Skipped the network profile modification and focused on other configuration changes such as the Hosts file, firewall rule creation, software installation, and local user management.

---

## Issue 2 — Unable to Modify Hosts File

### Cause

Notepad was not running with Administrator privileges.

### Resolution

Launch Notepad as Administrator before opening:

```text
C:\Windows\System32\drivers\etc\hosts
```

---

## Issue 3 — Unable to Save Hosts File

### Cause

Windows protected system file permissions.

### Resolution

Verify administrative privileges and ensure the file was opened from an elevated Notepad session.

---

## Issue 4 — Firewall Rule Not Visible

### Cause

The new rule was created under a different category or filtering was applied.

### Resolution

Review all Inbound Rules and verify the rule name used during creation.

---

## Issue 5 — No Related Events in Wazuh Discover

### Cause

Not every Windows configuration change generates searchable Windows events, or indexing may take time.

### Resolution

Validate configuration locally using PowerShell first, then use Wazuh Discover to correlate available supporting evidence.

---

## Issue 6 — Verify Wazuh Agent Health

### Cause

Potential communication interruption.

### Resolution

Verify the agent status using:

```bash
sudo /var/ossec/bin/agent_control -i 001
```

---

# Lessons Learned

- Always establish a baseline before making configuration changes.
- Native Windows tools provide the primary evidence during configuration drift investigations.
- Some configuration changes may not generate Windows Event Log entries.
- Wazuh should be used to correlate available evidence rather than replace endpoint validation.
- Comparing multiple artifacts provides a more complete DFIR investigation.
