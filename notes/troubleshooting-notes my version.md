# Troubleshooting Notes

## Issue 1 — Network Profile is public already.

### Cause

The endpoint was already configured with a Public network profile.

### Resolution

Skipped the network profile modification 

---

## Issue 2 — Unable to Modify Hosts File

### Cause

Notepad was not running with Administrator privileges.

### Resolution

Open Notepad as Administrator.

```text
C:\Windows\System32\drivers\etc\hosts
```

---

## Issue 3 — Unable to Save Hosts File

### Cause

Windows protected system file permissions.

### Resolution

Verify that Notepad is opened as Administrator.

---

## Issue 4 — Firewall Rule Not Visible

### Cause

The new rule was created under a different category or filtering was applied.

### Resolution

Review all Inbound Rules and verify the rule name used during creation.

---

