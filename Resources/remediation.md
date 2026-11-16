# Disk Analysis & Autopsy — Defensive Observations and Recommendations

This case study includes evidence of endpoint activity associated with PowerShell file modification, password-focused tools, an exploit archive, and user-specific network-monitoring configuration. The artifacts do not establish successful credential dumping or exploitation. Recommendations below focus on preventive controls and detection opportunities.

---

## 1. Account Management

**Observation:** The image contains eight human user accounts, plus built-in and service identities.

**Recommendations:**
- Review local account inventory and remove accounts that are no longer required.
- Enforce unique credentials and strong authentication.
- Apply least privilege to local groups and administrative membership.
- Correlate account artifacts with Security event logs before asserting logon activity.

## 2. PowerShell Visibility

**Observation:** PSReadLine history records commands that modify a Desktop file, and a recovered PowerShell script contains a conditional check and a file-write operation.

**Recommendations:**
- Enable PowerShell Script Block Logging and Module Logging through appropriate policy.
- Forward PowerShell operational logs to centralized monitoring.
- Monitor suspicious file modifications in user profile paths.
- Correlate history with process-creation and PowerShell event logs.
- Treat history as one artifact source; it can be incomplete or altered.

## 3. Credential-Theft Tool Indicators

**Observation:** A Mimikatz archive appears in a user's Downloads directory. Windows Defender detection history references `lazagne.exe`.

**Recommendations:**
- Apply endpoint protection and application control.
- Alert on unauthorized tools commonly associated with credential access.
- Monitor access to LSASS and credential stores using endpoint telemetry.
- Investigate downloads, process execution, Defender detections, and persistence artifacts together.
- Do not infer successful credential extraction solely from a download or detection record.

## 4. Exploit Archive Handling

**Observation:** A keyword search identifies a Zerologon-named archive in a user's download path, with source notes indicating that the file appeared deleted.

**Recommendations:**
- Preserve deleted-file metadata and relevant filesystem structures before recovery attempts.
- Search for associated execution evidence, such as process records, command history, Prefetch, Amcache, and event logs where available.
- Restrict unauthorized tooling and downloads on managed endpoints.
- Treat archive names as leads, not conclusive proof of exploitation.

## 5. Network Configuration Governance

**Observation:** The registry network-interface view displays a DHCP address of `0.0.0.0`, while Look@LAN's INI contains a LAN IP and interface value.

**Recommendations:**
- Correlate application-stored network values with DHCP server logs, network inventory, and endpoint management records.
- Inventory and approve network-monitoring software.
- Protect configuration files that contain network identity details.
- Review stale or inconsistent configuration values during incident response.

## 6. Forensic Process Improvements

- Record acquisition and verification hashes at evidence intake.
- Preserve original evidence in read-only storage.
- Maintain an examination log with timezone normalization.
- Correlate multiple independent sources before attributing user activity.
- Separate observed artifact facts, parser interpretations, and analyst hypotheses in reporting.
- Preserve screenshots and extracted files with their source paths and case identifiers.

## Detection Opportunities

| Artifact / activity | Defensive data source |
| --- | --- |
| PowerShell commands and scripts | PowerShell Operational logs, Script Block Logging |
| File creation or replacement in user Desktop | File-system auditing, EDR telemetry |
| Credential tool download or detection | Defender/EDR alerts, browser/download records |
| Suspicious process access to credential stores | EDR process and memory-access telemetry |
| Exploit archive presence | Download records, file-system metadata, endpoint telemetry |
| Account activity | Security event logs and identity audit records |
