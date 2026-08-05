# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 09:00 | Verified Wazuh agent connectivity | agent_control |
| 09:03 | Established system baseline | PowerShell |
| 09:08 | Reviewed Firewall configuration | PowerShell |
| 09:10 | Reviewed Hosts file | Hosts File |
| 09:12 | Reviewed installed software | Windows Settings |
| 09:15 | Reviewed local user accounts | net user |
| 09:18 | Modified Hosts file | Hosts File |
| 09:22 | Created firewall rule | Windows Firewall |
| 09:25 | Installed safe software | Installed Apps |
| 09:30 | Created and removed test user | net user |
| 09:35 | Validated configuration changes | PowerShell |
| 09:40 | Investigated Wazuh Discover | Discover |
| 09:45 | Correlated findings | Documentation |

---

# Investigation Flow

Investigation Started

↓

Verified Agent Health

↓

Established Baseline

↓

Reviewed Windows Configuration

↓

Performed Controlled Configuration Changes

↓

Validated Endpoint Configuration

↓

Investigated Wazuh Discover

↓

Correlated Evidence

↓

Investigation Completed

---

# Summary

This investigation reconstructed Windows configuration drift by comparing baseline and post-change system states. Multiple configuration artifacts were validated using native Windows tools and correlated with Wazuh Discover to produce a structured DFIR investigation documenting unauthorized or unexpected system configuration changes.
