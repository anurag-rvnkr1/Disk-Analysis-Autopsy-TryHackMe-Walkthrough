# Disk Analysis & Autopsy — References and Attribution

## Primary Training Platform

- TryHackMe — **Disk Analysis & Autopsy**, Medium-difficulty Windows forensics room.

## Source Material

Sean Dixon, “TryHackMe: Disk Analysis & Autopsy,” Medium, 13 June 2023. The source write-up and the twenty screenshots supplied with this task informed the investigation sequence and recorded answers. The report explanations and documentation are independently written.

## Forensic Application

- Autopsy 4.18.0 — shown in the supplied screenshots as the forensic application used to examine the E01 data source and parsed artifacts.

## Artifact Families Referenced

- E01 evidence container metadata.
- Windows SYSTEM and SOFTWARE registry hives.
- Per-user NTUSER.DAT registry hives.
- Windows user-account artifacts parsed by Autopsy.
- Look@LAN `irunin.ini`.
- Browser bookmark database artifacts.
- PowerShell PSReadLine `ConsoleHost_history.txt`.
- Windows Defender DetectionHistory.
- YARA rule file `kiwi_passwords.yar`.

## Attribution and Reporting Integrity

- Values are reproduced from the supplied source write-up and visible screenshots.
- The MD5 value was transcribed from Autopsy's Container Summary; it was not independently recalculated in this task.
- The PowerShell script's partial screenshot is described only to the extent visible.
- Tool indicators are not presented as proof of execution or successful credential extraction.
- Both challenge flags are redacted from public-facing text and the screenshot copies.
