# Disk Analysis & Autopsy — Artifact Reference

This document summarizes the primary artifact types reviewed in the case study.

| Artifact | Typical location / source | Investigative value in this case |
| --- | --- | --- |
| E01 Container Summary | Autopsy data source Summary → Container | Image metadata, acquisition details, hashes |
| Operating System Information | Autopsy Extracted Content | Host name and Windows identification |
| Operating System User Account | SAM / SOFTWARE-derived results | Human and built-in account enumeration; Date Accessed |
| Network interface registry values | SYSTEM hive, Tcpip Parameters Interfaces | DHCP and interface configuration |
| NetworkCards registry key | SOFTWARE hive, Microsoft\Windows NT\CurrentVersion\NetworkCards | Network adapter description |
| Look@LAN INI | Program Files (x86)\Look@LAN\irunin.ini | LANIP and LANNIC application configuration |
| Installed Programs | Autopsy Extracted Content | Installed application inventory |
| Web Bookmarks | Browser places.sqlite artifacts | Saved URLs and bookmark location |
| NTUSER.DAT Desktop values | User profile registry hive | Wallpaper path configured for a profile |
| Desktop files | User profile Desktop folders | User-generated files and scripts |
| PSReadLine history | AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt | Interactive PowerShell command history |
| Downloads directory | User profile Downloads | Downloaded archive and executable artifacts |
| Windows Defender DetectionHistory | ProgramData\Microsoft\Windows Defender\Scans\History | Endpoint detection records and referenced file paths |
| YARA rule | Recovered `.yar` file | Rule content and author metadata |
| Keyword search hits | Autopsy indexed content | Strings associated with current or deleted artifacts |

## Interpretive Cautions

- A registry value may represent stored configuration rather than live network state.
- User account Date Accessed values are parser-derived metadata and should not replace event-log timeline analysis.
- A wallpaper reference supports profile configuration; it does not prove a user's legal identity.
- A command in PowerShell history shows recorded input, not necessarily successful execution.
- A downloaded archive or Defender detection does not independently establish successful execution.
- A keyword-search hit for a deleted archive does not prove that the exploit was run.
