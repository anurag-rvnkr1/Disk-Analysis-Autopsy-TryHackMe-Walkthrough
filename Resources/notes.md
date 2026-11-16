# Disk Analysis & Autopsy — Investigation Notes

> Case notes derived from the supplied Autopsy screenshots and source walkthrough.

## Evidence Image

- Evidence file: `HASAN2.E01`
- Format: E01
- Image size: 65.43 GB
- Sector size: 512 bytes
- Acquisition timestamp shown: 8 February 2021, 12:40:23
- Time zone: America/New_York
- MD5 shown in Container Summary: `3f08c518adb3b5c1359849657a9b2079`
- Forensic application: Autopsy 4.18.0

The hash is transcribed from the screenshot; it was not independently recomputed in this documentation task.

## Host and User Context

- Host: `DESKTOP-0R59DJ3`
- Operating system: Windows 10 20H1
- Human users (alphabetical): `H4S4N`, `joshwa`, `keshav`, `sandhya`, `shreya`, `sivapriya`, `srini`, `suba`
- Last user in the Autopsy Date Accessed sort: `sivapriya`

The account table also includes service and built-in identities. They are not included in the requested human-user list.

## Network Artifacts

The SYSTEM hive interface view displays `DhcpIPAddress = 0.0.0.0`. The investigation then uses Look@LAN's `irunin.ini` as a separate configuration artifact.

Observed values:

```text
%LANHOST%=DESKTOP-0R59DJ3
%LANDOMAIN%=DESKTOP-0R59DJ3
%LANUSER%=H4S4N
%LANIP%=192.168.130.216
%LANNIC%=0800272cc4b9
```

The SOFTWARE hive path `Microsoft\Windows NT\CurrentVersion\NetworkCards` shows:

`Intel(R) PRO/1000 MT Desktop Adapter`

## Application and Browser Artifacts

- Installed network monitoring program: `Look@LAN`
- Related folder: `Program Files (x86)\Look@LAN`
- Configuration file: `irunin.ini`
- Web Bookmarks contains a Google Maps bookmark with coordinates `12°52'23.0"N 80°13'25.0"E`

## Wallpaper Evidence

- H4S4N profile wallpaper did not show the requested name.
- Joshwa profile's `NTUSER.DAT` Desktop Wallpaper value references an image that visibly displays `Anto Joshwa`.

This links the profile's wallpaper setting to the referenced image, but is not independent identity proof.

## Shreya Desktop and PowerShell Activity

The shreya Desktop contains `shreya.txt` and `exploit.ps1`.

The PowerShell PSReadLine history path is:

`AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt`

The displayed history includes commands to change directories, list files, append content to `shreya.txt`, read the file, then replace its contents. Public screenshots redact both flag strings.

The script excerpt shows a group-membership condition, a comment that the payload will run as Administrator, a write to `C:\Users\H4S4N\Desktop\hacked.txt`, and a message string. The screenshot does not establish successful script execution.

## Password-Tool Artifacts

- `mimikatz_trunk.zip` appears in H4S4N's Downloads.
- Windows Defender DetectionHistory contains a record referencing `C:\Users\H4S4N\Downloads\lazagne.exe`.

Artifact presence/detection does not prove successful execution or credential dumping.

## YARA and Zerologon

- Attribute search for `.yar` returns a YARA file named `kiwi_passwords.yar`.
- Its visible comment identifies author `Benjamin DELPY (gentilkiwi)`.
- Keyword search for `zerologon` finds `2.2.0 20200918 Zerologon encrypted.zip` in a Sandhya download path; the source notes describe the artifact as deleted.

The archive name is an investigative lead, not proof the exploit was run or succeeded.

## Flags

Both challenge flags are excluded from public documentation and redacted in the evidence screenshots.
